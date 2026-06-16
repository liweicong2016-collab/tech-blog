---
title: "三个 coding 模型接力跑同一份代码：GLM-5.2 / Sonnet 4.6 / Opus 4.7 实战对比"
date: 2026-06-15
draft: false
description: "同 harness、同 TDD、同项目——把 GLM-5.2、Sonnet 4.6、Opus 4.7 拉到一份代码基线上跑真实任务，结论先放这儿：GLM-5.2 ≈ Opus 4.7，Sonnet 4.6 低半档但快省。"
tags: ["AI", "Coding 模型", "LLM 评测", "Agent", "方法学", "SWE-bench"]
slug: "four-coding-models-comparison-2026"
cover:
  image: "https://images.unsplash.com/photo-1555949963-aa79dcee981c?w=1200&q=80"
  alt: "代码编辑器与多模型协作"
  caption: "把四个 coding 模型拉到同一份代码、同一份 TDD 流程里跑真实任务"
ShowToc: true
---

## 结论先放这儿

把 **GLM-5.2**、**Sonnet 4.6**、**Opus 4.7** 拉到同一份代码、同一份 TDD 流程、同一套 ZCode agent harness 上跑真实任务（再加一节里把 **DeepSeek v4-pro** 也拉进来做了浏览器交互和 8 步 rollback）。结论一句话：

- **GLM-5.2 ≈ Opus 4.7** —— 深度调试、TDD 纪律、角色边界三家都第一梯队。
- **Sonnet 4.6** 低半档 —— 但快、省，效率型执行者。
- **DeepSeek v4-pro** 也是第一档 —— 延迟四家最快（平均 11.4 秒），但风格完全不同：寡言、边跑边调、靠密集工具调用推进。

这次测试最有价值的不是给模型排名，而是**反思方法学本身**。为什么这么说，下面展开。

---

## 一、测试背景：为什么这次不是又一个 benchmark

我以前写过几篇行业 benchmark 速读（[SWE-bench Leaderboards](https://swebench.com/)、[Aider polyglot](https://aider.chat/docs/leaderboards/)、[LMArena Chatbot Arena](https://lmarena.ai/)、[Artificial Analysis](https://artificialanalysis.ai/)），它们都有同一个盲点：

> **benchmark 数字只能告诉你"够不够格"，不能告诉你"够不够好用"。**

一个 SWE-bench Verified 60% 通过率的模型，可能在真实项目里被一个 review finding 卡住 30 分钟爬不出来；一个 SWE-bench 40% 的模型，可能在 review 面前一抓一个准、还顺手把测试时序的隐性 bug 修了。

所以这次我换了一个**实战对实战**的 setup：

| 维度 | 设定 |
|---|---|
| 项目 | 一个完整的前后端项目（包含 Playwright 拖拽、SortableJS 集成、V9.4.3 index rollback） |
| Harness | ZCode agent（自主编码 agent framework） |
| 流程 | TDD：RED → GREEN → REFACTOR；reviewer 抓 finding |
| 模型接的段落 | GLM-5.2 跑主体（190 turn）；Sonnet 4.6 清 E4（25 turn）；Opus 4.7 调 3 个 medium finding（26 turn）；DeepSeek v4-pro 跑浏览器交互 + 8 步 rollback（120 turn） |
| 最终结果 | pytest 全绿 / vitest 全绿 / build 通过 / 零回归 |

**关键约束**：这不是 head-to-head benchmark。四家接的是**不同阶段、不同类型的任务**，难度不可比。但**harness、流程、代码基线完全一样**，这给了我们一个观察"模型风格差异"的机会。

---

## 二、关键数字三张表

### 2.1 延迟（平均单 turn 秒数）

| 模型 | 平均 | 最慢单 turn |
|---|---|---|
| **DeepSeek v4-pro** | **11.4s** | 44.8s |
| GLM-5.2 | 16.4s | 52.4s |
| Sonnet 4.6 | 17.0s | 52.4s |
| Opus 4.7 | 17.9s | 33.7s |

**最反直觉的数字**：平均延迟最慢的反而是 Opus 4.7（17.9s），但**它最稳**——最慢单 turn 33.7s，是四家里最低的。GLM 和 Sonnet 都飙到过 52.4s。

也就是说：**"慢 turn 数量"比"平均延迟"更能反映模型的稳定性**。Opus 慢得均匀，GLM / Sonnet 偶尔一两个长 Read / Edit 把平均拉高。

DeepSeek 是另一个极端——**平均最快 + 也很稳**（11.4s / 44.8s）。

### 2.2 输出密度（平均每文本 turn 字数）

| 模型 | 字数 |
|---|---|
| **DeepSeek v4-pro** | **157** |
| Sonnet 4.6 | 322 |
| Opus 4.7 | 442 |
| GLM-5.2 | 452 |

**这才是四家真正的"风格签名"**。

- GLM / Opus：平均每 turn 442-452 字，喜欢"先解释，再动手"。
- Sonnet：322 字，中等密度。
- DeepSeek v4-pro：157 字，**是其他三家的不到一半**。

**v4-pro** 的典型输出长这样：

> Good progress — dragstart triggered DndController! But dragover needs to hit the Sortable container. Let me check the DOM structure.

一句话，然后直接调工具。不铺垫、不写长篇计划、不"我先复盘一下刚才做了什么"。

### 2.3 prompt cache 命中率

四家都在 **47%-50%**。这个数字完全是 harness 决定的，跟模型本身无关——列出它只是为了**避免读者误以为是模型差异**。

---

## 三、深度调试：三家各自的"绝活"

benchmark 数字最难看出来的就是这一项。三个 case 拼起来看。

### 3.1 Opus 4.7：定位 overlay 克隆节点

M1 测试改了之后还是失败。Opus 没有急着换方案，而是逐层诊断：

- querySelector 命中的节点实际属性是什么？
- 节点是来自源 DOM 还是被 SortableJS 克隆出来放到 overlay 的？
- 真的是源节点吗？

定位到根因：**querySelector 命中的其实是 overlay 里的克隆节点，而不是原始行**。这是一个真正的 DOM 结构陷阱。

后面还撞上 test-ordering bleed：测试之间 window listener 没清干净，跨测试污染。Opus 的判断是 `afterEach` 要按名字清掉所有 window listener。

整条链路：**症状 → 逐层排除 → 定位根因 → 验证修复**。这是高水平表现。

### 3.2 GLM-5.2：被 reviewer 抓 is_connected 是 Node API

GLM 在另一个 session 里写了一段 Playwright Python 代码。Reviewer 一抓：is_connected 是 **Playwright 的 Node.js API，Python 里根本不存在**。

GLM 的反应链：

1. 承认错误（不狡辩、不重新生成试试）
2. 查文档确认（是 Python 真的没这个 API，还是我用错了？）
3. 换成 page.wait_for_function（验证替代方案）
4. 顺手检查 time 模块是不是变成 dead import
5. 编译、重读 helper 确认接线一致
6. 全量回归

这条链路和 Opus 的"逐层诊断"是**同一个档次**的深度调试。两家在"测试反复失败 / 钻进 DOM 或 API 误用的深层"时都能自己爬出来。

**更关键的是角色边界**：GLM 守授权边界极严。实现完成后主动停下等放行，**不抢 commit**。Reviewer 甩 finding 它逐条确认、改、再用 Self-check 表格回报。Reviewer 不说话，它不跑下一步。

**还会思辨规则**：tdd skill 说"一次一个测试"，GLM 看了几个 round-trip case 走的是同一条 attrEsc 路径，主动判断**这几个可以合并成参数化测试**——并且**把理由说出来**。这是"理解规则的意图"，不是"机械执行规则的字面"。

### 3.3 Sonnet 4.6：4 个 carry-forward bug 一口气清完

E4 段落 reviewer 一次性甩了 4 个 carry-forward bug。Sonnet 的反应：

- 第一反应**不盲信 reviewer**（25 turn 里前 4-5 个 Read + Bash 都是核 4 条事实）
- 然后逐条改
- 25 turn / 7 分钟全清完
- 收尾给一张 Bug | Fix | Evidence 三列表

**风格**：目标明确 → 核对事实 → 批量执行 → 干净收尾。没有大段铺垫，也没有长篇复盘。

**但**：这段 Sonnet 走得很顺，没遇到 Opus 那种反复失败的困境。所以**深度调试这一档在这段里没机会展示**。Sonnet 是效率型执行者——快速清账段落最划算，深度调试这一档不好说和 GLM / Opus 同档。**所以定位上更像是低半档但快、省**。

---

## 四、四家定位（加 DeepSeek v4-pro）

把 DeepSeek v4-pro 也加进来后，定位更清晰：

### 4.1 GLM-5.2

- **档次**：第一档
- **延迟**：16.4s（第二快）
- **风格**：均衡型，Read / Edit / Bash 比例健康
- **强项**：深度调试、TDD 纪律、角色边界、review 互动、思辨规则
- **弱项**：无明显短板，偶尔慢 turn（52.4s 那种）
- **适合**：主体阶段（190 turn 这种长阶段）、多轮 review

### 4.2 Opus 4.7

- **档次**：第一档
- **延迟**：17.9s（最慢平均但最稳）
- **风格**：Read 最少 / Bash 最多，倾向于"直接跑起来看"
- **强项**：深度调试、逐层诊断、RED 先行、改之前先写回归测试
- **弱项**：最慢平均（17.9s），对快节奏段落不划算
- **适合**：调最难的问题、需要多轮诊断的段落

### 4.3 DeepSeek v4-pro

- **档次**：第一档
- **延迟**：11.4s（**四家最快**，比 Opus 快 36%）
- **风格**：寡言型执行者，惜字如金，靠密集工具调用推进
- **强项**：浏览器交互调试、步骤密集的执行任务、明确的失败陈述
- **弱项**：不擅长长篇计划 / 多轮 review 回报（输出密度太低）
- **适合**：浏览器交互调试（用 chrome-devtools + playwright 这种）、明确的步骤清单

**它的深度调试也是第一档**——但走的是不同路径。它这段接的是用 chrome-devtools 和 playwright 两个 MCP 在真实浏览器里调拖拽，120 turn 死磕 SortableJS 不响应合成事件。路径：

> pointer events → HTML5 DragEvent → 发现 SortableJS 检查 isTrusted 拒绝合成事件 → 钻进源码发现要在绑定方法之前注册监听器所以 monkey-patch 不生效 → 改用重注册监听器

每一步失败都明确说："SortableJS didn't respond to programmatic pointer events"、"The issue is that SortableJS registers the event listener BEFORE binding methods"。

工具调用结构：43 个 Bash + 27 个 chrome-devtools 脚本 + 大量 playwright 操作，典型的"边跑边调"。前三家更偏 Read + Edit。

### 4.4 Sonnet 4.6

- **档次**：低半档（深度调试这一档没机会展示）
- **延迟**：17.0s
- **风格**：效率型执行者
- **强项**：快速清账、目标明确、收尾干净
- **弱项**：深度调试未验证
- **适合**：收尾清账、明确目标的段落

---

## 五、方法学反思：benchmark 数字 ≠ 实战表现

这次测试最有价值的是**它挑战了主流 benchmark 的方法学假设**。

### 5.1 主流 benchmark 测的是什么

| Benchmark | 测的什么 | 测不到的 |
|---|---|---|
| SWE-bench | 真实 GitHub issue 修复 | 多轮 review / 角色边界 |
| Aider polyglot | 6 语言 225 题 edit format | 长项目记忆 / review 互动 |
| LiveCodeBench | 持续更新的新题 | 错误恢复 / 自诊断 |
| Chatbot Arena | 真实人类盲测投票 | 任务粒度太粗 |
| Terminal-Bench | 接近 agent 真实场景 | 仍是 fresh task，没 follow-up |

**共同盲点**：benchmark 都是"看模型一次能不能做对"，看不到"模型犯错后能不能爬出来"。

### 5.2 这次实战补上的维度

| 维度 | 传统 benchmark | 这次实战 |
|---|---|---|
| 任务类型 | 独立问题 | 同一项目的不同阶段 |
| 评估方式 | 通过 / 不通过 | 通过率 + review 抓 finding 数 + 自我承认错误的速度 |
| 失败处理 | 任务算失败 | 模型自己诊断根因、换路径、再回归 |
| 角色边界 | 不测 | 测（自主停等放行 vs 抢 commit） |
| 工具调用 | 计数 | 计数 + 倾向（Read vs Bash 比例） |
| 输出风格 | 不测 | 测（每 turn 字数 / 失败陈述明确性） |

**结论**：benchmark 是"够格"门槛，**真实项目的"实战表现"才是"好用"门槛**。两者关系类似高考分 vs 工作后表现。

### 5.3 这次的反常识发现

1. **延迟最慢 ≠ 质量最低**：Opus 平均 17.9s 反而比 GLM 16.4s 慢，但深度调试稳定性是四家最高。
2. **输出越短 ≠ 越浅**：DeepSeek v4-pro 157 字 / turn 是四家最少，但深度调试和 GLM / Opus 同档。
3. **守边界 ≠ 弱**：GLM 实现完主动停下等放行 = 高水平（不是"没能自己跑完"），Sonnet 不盲信 reviewer 先核 4 个事实 = 高水平（不是"没主见"）。
4. **不同模型擅长不同任务**：不能用单一 score rank 模型。
5. **prompt cache 命中率与模型无关**：这个数字只能反映 harness 设计。

### 5.4 "分阶段接力"本身就是一个新方法

把一个项目按阶段切给不同模型，每家扬长避短——这是"模型异构计算"的实践雏形（类似 GPU 集群里 CPU / GPU / NPU 各管一段）。未来这个思路可能延伸成"agent 编排层 = 模型路由器"。

| 段落类型 | 适合的模型 | 理由 |
|---|---|---|
| 主体（190 turn） | GLM-5.2 / Opus 4.7 | 深度、TDD、边界 |
| 清 E4（25 turn） | Sonnet 4.6 | 效率、收尾、核对 |
| 调 medium finding（26 turn） | Opus 4.7 | 深度诊断 |
| 浏览器交互 + 8 步 rollback（120 turn） | DeepSeek v4-pro | 寡言执行、密集工具调用 |

---

## 六、务实的接法（给做 agent 的同行）

> **长阶段 / 多轮 review / 自觉守边界的主体 → GLM 或 Opus**
> **浏览器交互调试 / 步骤密集的执行 → DeepSeek v4-pro**
> **收尾清账 → Sonnet**

这次四家各管一段，**最终 pytest 和 vitest 全绿，build 通过，零回归**。这就是"模型异构计算"在编码 agent 里的最小可用形态。

---

## 七、局限

- **样本量**：一个 session（GLM 的 190 turn 是主样本，其他三家各 25-120 turn 不等）
- **不是 head-to-head**：四家接的是不同阶段、任务难度不可比
- **benchmark 基准未做**：这次只测了实战表现，没有同 session 跑 SWE-bench / Aider 数字做 cross-check
- **人为切段**：模型切换是人工切的，可能引入"段落难度差异"的混杂变量

更严谨的版本需要：四家同 session 跑同一份 SWE-bench Verified 子集 + 同一份 Aider polyglot 子集 + 同一份真实项目段落。但那种测试我还没做——留给下一篇文章。

---

## 八、延伸阅读

- [SWE-bench Leaderboards](https://swebench.com/)
- [Aider LLM Leaderboards](https://aider.chat/docs/leaderboards/)
- [LMArena Chatbot Arena](https://lmarena.ai/)
- [Artificial Analysis](https://artificialanalysis.ai/)
- [Vellum LLM Leaderboard](https://www.vellum.ai/llm-leaderboard)

---

## 附录：脱敏说明

本文按公开报告惯例使用代号：模型版本号（GLM-5.2 / Sonnet 4.6 / Opus 4.7 / DeepSeek v4-pro）按用户原话保留作为技术事实，**母公司主体**（头部 Coding 创业公司 X / 头部 MoE 厂商 / 海外某 AI 公司）按公开报告惯例使用代号。代号指代对象的完整对照表存于私有 source.md，不在公开版本展开。读者无需关心具体公司名也能完整理解方法学结论。

---

*作者：Livius · 2026-06-15 · 编辑型技术博客*
