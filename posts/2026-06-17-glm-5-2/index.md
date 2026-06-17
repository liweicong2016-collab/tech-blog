---
title: "智谱 Z.ai 正式开源 GLM-5.2 权重并上线 API:100 万上下文 + IndexShare + MIT 许可"
date: 2026-06-17
author: Livius
tags: [AI, GLM, Z.ai, Zhipu, open-source, MIT, long-context, agentic-coding, MoE, DeepSeek-sparse-attention, IndexShare]
description: "GLM-5.2 正式开源(MIT)+ 上线官方 API,1M 上下文 + IndexShare(每 4 层共享 indexer,2.9× 计算降低)+ High/Max 双思考档;Z.ai 公告中提及 FrontierSWE 长程编码 benchmark 但具体分数未公开。"
canonical: https://liweicong2016-collab.github.io/tech-blog/posts/2026-06-17-glm-5-2/
---

# 智谱 Z.ai 正式开源 GLM-5.2 权重并上线 API:100 万上下文 + IndexShare + MIT 许可

> 报告日期:2026-06-17 (Asia/Saigon)
> 任务日期:2026-06-17
> 报告语言:简体中文
> 状态:已发布(基于 Z.ai 官方公告 + 多个独立二手源交叉核验,已二次更新纳入官方一手原文)

## Executive Summary

2026 年 6 月 13 日,北京智谱 AI 的国际品牌 **Z.ai** 正式将旗舰大模型 **GLM-5.2** 的权重以 **MIT 协议** 开源,并同步上线官方 API。这是继 GLM-5(2 月 11 日)、GLM-5-Turbo(3 月 15 日)、GLM-5.1(4 月 7 日)之后四个月内的第四次旗舰级发布 ([marktechpost 报道](https://www.marktechpost.com/2026/06/14/z-ai-launches-glm-5-2-with-a-usable-1m-token-context-two-thinking-effort-levels-and-no-benchmarks-at-launch))。

按 Z.ai 官方公告原文([Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2),[X 公告](https://x.com/Zai_org/status/2065704919299235870))的定义,GLM-5.2 的"四大新能力"是:

1. **Solid 1M Context** — "A solid 1M-token context that stably sustains long-horizon work"
2. **Advanced Coding with Flexible Effort** — "Stronger coding capabilities with multiple thinking effort levels to balance performance and latency"
3. **Improved Architecture** — IndexShare 复用 indexer,MTP 接受长度 +20%
4. **Pure Open** — "An MIT open-source license — no regional limits, technical access without borders"

GLM-5.2 的 1,000,000 token 上下文窗口(`glm-5.2[1m]`),相较 GLM-5.1 的 200K 窗口提升了 5 倍 ([docs.z.ai/.../latest-model](https://docs.z.ai/devpack/latest-model))。为支撑该窗口,智谱在底层的稀疏注意力中引入了 **IndexShare(索引共享)** 技术,官方原文是 **"reuses the same indexer across every four sparse attention layers, reducing per-token FLOPs by 2.9× at a 1M context length"**——比 GLM-5.1 时代每个 indexer 独立计算有 2.9× 的单 token FLOPs 下降([OpenLM 模型页](https://openlm.ai/glm-5.2/))。MTP 改进后,**接受长度在推测解码场景下提升 up to 20%**。

模型继续采用 **GLM-5 系列的 MoE 架构:744B 总参 / 40B 激活参数**,与上游 GLM-5(arxiv 2602.15763 描述)及 DeepSeek V3 / Kimi K2 等同档位模型保持同代 ([arxiv 2602.15763](https://arxiv.org/abs/2602.15763))。GLM-5.2 暴露 **High** 与 **Max** 两档思考模式;Max 模式专供长链推理与复杂调试。官方 API 定价与 GLM-5.1 一致:**输入 $1.40 / 输出 $4.40 per 1M tokens** ([docs.z.ai/.../pricing](https://docs.z.ai/guides/overview/pricing),[KuCoin 报道](https://www.kucoin.com/news/flash/z-ai-launches-glm-5-2-with-1m-token-context-window-on-hugging-face))。

值得注意的"留白":Z.ai **没有在公告原文中同步发布传统 SWE-bench / Terminal-Bench / HLE 分数**;公告中提到 **"FrontierSWE measures whether an agent..."** 的一个新基准,但所提供原文片段被截断,具体分数未在公告摘录中给出。对 1M 长上下文在长程任务上的实际稳定性,市场仍依赖后续第三方评测验证。

## Research Questions

1. GLM-5.2 的发布主体、时间线与许可证是什么?
2. GLM-5.2 的 MoE 架构(总参 / 激活参 / 专家数 / 注意力机制)与 GLM-5 基础模型有何关系?
3. 1,000,000 token 上下文窗口的工程实现(IndexShare / MTP / DSA)如何工作?
4. High / Max 两档思考模式的定位与推荐场景?
5. 官方 API 定价、订阅档位,以及与 OpenRouter 的对接状态?
6. Z.ai 是否在发布时同步公开任何基准测试数据?
7. 第三方(媒体 / 社区)对 GLM-5.2 的早期反馈与争议点?

## Method

| 阶段 | 工具 | 输出 |
|---|---|---|
| Plan | `scripts/init_research_run.py` | `tmp/research_plan.json` |
| Scout | Tavily(`scripts/tavily.py`)+ `web_search` | `tmp/query_log.json` (≥4 query families:baseline / source-seeking / recency / benchmark-spec / contradiction) |
| Harvest | `web_fetch` 抓取 Z.ai 官方 / OpenLM / HF / arxiv 摘要 / 媒体长文 + Z.ai 公告原文 | `tmp/source_registry.json` (90 sources, 9 primary fetched + 3 secondary fetched) |
| Verify | `claim_ledger.json` 14 claims / `coverage_report.json` | 14 claims,11 verified + 3 partially_verified,coverage_score 1.0 |
| Synthesize | `report_lint.py` → `validate_research_report.py` → `finalize_research_run.py` | 本报告 |

完整方法学见仓库 `SOUL.md` 的 5 步流程。本次研究的关键升级是 **第二次迭代纳入了 Z.ai 官方公告原文(用户提供)**——这将原本依赖二手源转述的 IndexShare、1M 训练场景、MIT 范围三项主张,提升为**官方一手 verified 状态**。

## Findings

### 1. 发布主体、时间线与许可证

GLM-5.2 由 **Z.ai**(智谱 AI 的国际品牌)于 **2026-06-13** 正式发布。Z.ai 官方公告将其定位为:

> *"We're introducing GLM-5.2, our latest flagship model for long-horizon tasks. It marks a substantial leap in long-horizon task capability over its predecessor GLM-5.1 and, for the first time, delivers that capability on a solid 1M-token context."*
> — [Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2)

模型权重同步上传至 Hugging Face,仓库为 [`zai-org/GLM-5.2`](https://huggingface.co/zai-org/GLM-5.2)。许可证为 **MIT**,官方原文用了更直白的措辞:

> *"Pure Open: An MIT open-source license — no regional limits, technical access without borders"*
> — [Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2)

注意"**no regional limits, technical access without borders**"——这是对 DeepSeek 等竞品在某些司法管辖区使用限制的明确对照。MIT 协议在该领域对开发者最友好,这一表述也意味着 Z.ai 不会像某些美国厂商那样对 EU/中国大陆/俄罗斯等地做地理封锁。

GLM-5 系列的发布节奏:

| 版本 | 发布日期 | 关键变化 |
|---|---|---|
| GLM-5 | 2026-02-11 | 744B MoE,DSA 注意力,异步 RL |
| GLM-5-Turbo | 2026-03-15 | 推理优化,价格 $1.20 / $4.00 per 1M |
| GLM-5.1 | 2026-04-07 | 200K 上下文,聚焦"agentic coding" |
| **GLM-5.2** | **2026-06-13** | **1M 上下文,IndexShare,High/Max 双思考档,MIT 权重,Frontend 训练 4 大场景** |

四次旗舰级发布压缩在四个月内,显示出 Z.ai 在智谱 2026-01-08 港股 IPO(募资约 43.5 亿港元 ≈ 5.58 亿美元)之后正以高强度节奏推进 ([KuCoin 报道](https://www.kucoin.com/news/flash/z-ai-launches-glm-5-2-with-1m-token-context-window-on-hugging-face))。

### 2. MoE 架构与训练背景

GLM-5.2 沿用 GLM-5 的基础架构:

- **总参 / 激活参:744B / 40B** (256 专家 / 8 激活)
- **稀疏注意力:DeepSeek Sparse Attention (DSA)** —— 一种基于 indexer 的 top-k 注意力选择,可将 attention 的二次开销降至接近线性 ([arxiv 2602.15763 摘要](https://arxiv.org/abs/2602.15763))
- **训练规模:28.5T tokens**
- **训练硬件:华为昇腾 + MindSpore** —— 与依赖 NVIDIA H100/H200 的西方前沿模型形成代差对照
- **异步 RL**:post-training 阶段使用异步 RL 基础设施,将 generation 与 training 解耦,提升后训练效率

> **参数数量说明**:本文最初描述的"7530 亿 / 400 亿"(对应 753B / 40B)与官方"744B / 40B"存在 9B 的差异;官方权威数字来自 [OpenLM](https://openlm.ai/glm-5.2)、[HF 模型卡](https://huggingface.co/zai-org/GLM-5.2)、[arxiv 2602.15763 摘要](https://arxiv.org/abs/2602.15763) — **744B / 40B / 256 专家 / 8 激活**。本报告以官方数字为准。

GLM-5 的整篇 arxiv 技术报告([2602.15763 v2](https://arxiv.org/abs/2602.15763),"from Vibe Coding to Agentic Engineering")将 GLM-5 定位为"从 vibe coding 转向 agentic engineering"的过渡模型——这是 Z.ai 在 2026 年最强的产品叙事:模型不再只是补全代码片段,而是要在长程 agent loop 中承担"规划 → 执行 → 测试 → 修复"的完整工程任务。

### 3. 1M token 上下文与 IndexShare(官方一手描述)

GLM-5.2 的差异化卖点是 **1,000,000 token 的可用上下文窗口**,而不仅是"理论支持"。Z.ai 内部的模型标识为 `glm-5.2[1m]`,单次响应最多输出 **131,072 tokens** ([OpenLM](https://openlm.ai/glm-5.2/))。这一数字是 GLM-5.1 的 **5 倍**(200K → 1M)。

官方公告对 1M 的描述是:

> *"Solid 1M Context: A solid 1M-token context that stably sustains long-horizon work."*
> *"Supporting long-horizon tasks starts with making long context engineering-usable: the model must maintain quality across long, messy coding-agent trajectories, not just accept more tokens. A 1M context is easy to claim, but much harder to keep reliable under real engineering pressure."*
> — [Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2)

**关键认知**:Z.ai 明确说"a 1M context is easy to claim, but much harder to keep reliable"——这是直接对同业"挂羊头卖狗肉"式 1M 营销的隐性攻击。Z.ai 把"engineering-usable"作为评估 1M 真正可用性的标准,而非"在 Needle-in-a-Haystack 找得着"。

为此,公告明确披露了 **1M 训练专门覆盖的四大 coding-agent 场景**:

1. **Large-scale implementation** — 大规模代码实现
2. **Automated research** — 自动化研究
3. **Performance optimization** — 性能优化
4. **Complex debugging** — 复杂调试

这四个场景的共同特征是:长程、多步、跨文件、需要维护 deep context。这也是 GLM-5.1 时代用户最常遇到能力瓶颈的场景。

#### IndexShare 工程实现(官方描述)

官方公告对 IndexShare 的描述是:

> *"Improved Architecture: We propose IndexShare, which reuses the same indexer across every four sparse attention layers, reducing per-token FLOPs by 2.9× at a 1M context length. We also improve GLM-5.2's MTP layer for speculative decoding, increasing the acceptance length by up to 20%."*
> — [Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2)

这段话比 OpenLM 等二手转述更精准:

- **IndexShare** 的定义是 "reuses the same indexer across every four sparse attention layers"——每 4 层共享一个 indexer,而非每层独立计算
- **效果**:"reducing per-token FLOPs by 2.9× at a 1M context length"——1M 上下文下,单 token FLOPs 降低 2.9 倍
- **MTP 改进**:"increasing the acceptance length by up to 20%"——MTP 在推测解码下接受长度最高提升 20%

IndexShare 的思想与 DeepSeek DSA 的"主注意力层 + 共享 indexer"思路类似,但 GLM-5.2 进一步将 indexer 在 4 个连续层之间共享——这是 Z.ai 对 DSA 的工程化优化。VentureBeat 同期报道了 IndexCache 等独立稀疏注意力优化器,显示该方向是 2026 年推理栈的活跃优化点 ([VentureBeat](https://venturebeat.com/technology/indexcache-a-new-sparse-attention-optimizer-delivers-1-82x-faster-inference))。

**应用场景**:官方文档列出的典型用例包括整库重构(40 文件 Python 数据管道单会话完成)、超长 agent loop、Claude Code drop-in 替代、超长文档分析(法规、论文、合规文档等)。这些场景在 GLM-5.1 时代需要 chunking / RAG,现在可以"一锅端"。

### 4. 思考模式:High 与 Max

官方公告描述:

> *"Advanced Coding with Flexible Effort: Stronger coding capabilities with multiple thinking effort levels to balance performance and latency."*
> — [Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2)

公告原文只说"multiple thinking effort levels",但 Z.ai 官方模型门户和第三方资料命名了两档:**High** 和 **Max**。

| 模式 | 定位 | 推荐场景 |
|---|---|---|
| **High** | 速度 / 质量平衡 | 短 Q&A、对话、单元测试补全 |
| **Max** | 深度 CoT 推理 | 自动编程、复杂调试、agent loop |

在 Claude Code 中,`/effort` 命令将 `xhigh` / `max` / `ultracode` 全部映射到 GLM-5.2 的 Max effort ([marktechpost 实战配置](https://www.marktechpost.com/2026/06/14/z-ai-launches-glm-5-2-with-a-usable-1m-token-context-two-thinking-effort-levels-and-no-benchmarks-at-launch))。这是 Z.ai 对长程任务"开 Max"的明确推荐。

"balance performance and latency"这句措辞意味着 Z.ai 明确把"延迟可控"作为产品 KPI——这与某些模型"无论什么 query 都跑最重 CoT"的策略形成对比。

### 5. 官方 API 与 OpenRouter

**官方 API 定价**与 GLM-5.1 保持一致([docs.z.ai/.../pricing](https://docs.z.ai/guides/overview/pricing),[KuCoin 报道](https://www.kucoin.com/news/flash/z-ai-launches-glm-5-2-with-1m-token-context-window-on-hugging-face)):

| 模型 | Input ($/M tok) | Output ($/M tok) |
|---|---|---|
| GLM-5 | 1.00 | 3.20 |
| GLM-5-Turbo | 1.20 | 4.00 |
| GLM-5.1 | 1.40 | 4.40 |
| **GLM-5.2** | **1.40** | **4.40** |

基础 URL 同样为 Anthropic 兼容 (`https://api.z.ai/api/anthropic`) 和 OpenAI 兼容 (`https://api.z.ai/api/coding/paas/v4`) 双端点。GLM Coding Plan 订阅(Lite / Pro / Max / Team,$18/月起)在发布当天即向所有档位用户开放([marktechpost](https://www.marktechpost.com/2026/06/14/z-ai-launches-glm-5-2-with-a-usable-1m-token-context-two-thinking-effort-levels-and-no-benchmarks-at-launch))。

**Claude Code 典型配置**(`~/.claude/settings.json`):

```json
{
  "env": {
    "CLAUDE_CODE_AUTO_COMPACT_WINDOW": "1000000",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-4.5-air",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2[1m]",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.2[1m]"
  }
}
```

或将 Anthropic 兼容端点直接 export 到环境变量,然后 `claude` 启动即可([marktechpost 实战配置](https://www.marktechpost.com/2026/06/14/z-ai-launches-glm-5-2-with-a-usable-1m-token-context-two-thinking-effort-levels-and-no-benchmarks-at-launch))。

**OpenRouter**:用户最初描述中提到 GLM-5.2 已"接入"OpenRouter。OpenRouter 列表页 [openrouter.ai/z-ai/glm-5.2](https://openrouter.ai/z-ai/glm-5.2) 存在,同厂模型 `z-ai/glm-5-turbo` 同步上架;然而在 2026-06-17 的快照中,GLM-5.2 的路由状态显示为"not available"或类似提示([OpenRouter 列表](https://openrouter.ai/z-ai/glm-5.2))。`/compare/z-ai/glm-5.2` 页面也已存在,说明 OpenRouter 已为其留位,但**实际可路由的 billing 状态需要后续验证**——海外开发者目前主要还是通过 Z.ai 官方 API 或自部署权重的方式使用。

### 6. 基准测试:有 FrontierSWE,但传统 benchmark 留白

值得特别关注的是:**Z.ai 在 GLM-5.2 公告原文中未直接公开传统 SWE-bench Pro、Terminal-Bench、HLE、GPQA 等标准 benchmark 分数**。但公告**提及了一个名为 **FrontierSWE** 的长程编码基准**:

> *"This capability is reflected in GLM-5.2's performance on three long-horizon coding benchmarks. FrontierSWE measures whether an agent…"*
> — [Z.ai Blog GLM-5.2](https://z.ai/blog/glm-5.2) (节选截断)

公告明确说 GLM-5.2 在 **"three long-horizon coding benchmarks"** 上有表现,且 FrontierSWE 是其中第一个。**但所提供的公告原文片段在此处被截断**,实际分数未在摘录中给出——这意味着:

- (i) Z.ai 官方**确实在内部测了三个长程 benchmark**,并将其作为 GLM-5.2 的核心证据;
- (ii) 但这些数字尚未在公开摘录中披露;
- (iii) FrontierSWE 对 agent 长程任务能力的测量是否会成为新行业标准,值得后续追踪。

第三方早期反馈参考:
- **AICodeKing(YouTube)**:实测自建 coding bench 得分 ~81.4,较 Opus 4.8 / Fable 落后约 6% ([YouTube](https://www.youtube.com/watch?v=MkFThJWJgg8))
- **Hacker News 讨论串(48518684)**:对 MIT 许可证 + 1M 上下文 + 开源权重表达正面评价;但对"无传统 benchmark"和"过密的 700B+ MoE 发布节奏"提出批评([HN 讨论](https://news.ycombinator.com/item?id=48518684))

**观察性推论**:Z.ai 选择"少传统 benchmark、多 FrontierSWE 长程场景",可能源于:
- (i) 1M 长上下文是新维度,缺乏公认评测协议(无 1M 级别的 SWE-bench);FrontierSWE 是 Z.ai 自己的"在长程任务上的标准"——可以重新定义赛道。
- (ii) Z.ai 想避免"在 GLM-5.1 时代被 Opus 4.8 / Fable 反超"——GLM-5.1 SWE-bench Pro 58.4,Opus 4.8 在 SWE-bench Pro 上是 70+,差距明显。
- (iii) 智谱正在将叙事从"benchmark 排名"转向"agentic 实际工程能力"——公告通篇强调"agentic engineering"而非"benchmark leaderboard"。

无论原因为何,这一决定在 2026 年 6 月各家(Anthropic、OpenAI、Google、Kimi、DeepSeek)都在出分的当下显得突出。

## Conflicts / Unverified

1. **参数描述差异**:本文最初描述的"7530 亿"与官方"744B"存在 9B 的差异;GLM-5.2 的实际架构完全继承自 GLM-5,**官方权威数字是 744B / 40B / 256 专家 / 8 激活**。
2. **OpenRouter 实际路由状态**:OpenRouter 列表页(`/z-ai/glm-5.2`)已存在,但 2026-06-17 快照显示 "not available"——目前仅能确认"已上架",无法确认"已可计费路由"。
3. **API 定价来源**:官方 `docs.z.ai/.../pricing` 页面在本次抓取中**未直接列出 GLM-5.2 的定价行**,只列出 GLM-5、GLM-5-Turbo、GLM-5.1。KuCoin 报道(二手)确认 GLM-5.2 与 GLM-5.1 定价一致($1.40 / $4.40)。该数字视为 **partially_verified**——可信度高,但缺一手直接确认。
4. **FrontierSWE 完整描述与分数**:Z.ai 公告原文片段在描述 FrontierSWE 时被截断,**实际分数、benchmark 协议、对比模型**尚未在公开摘录中给出。后续需要从完整公告页/技术报告获取。
5. **1M 稳定性训练细节**:Z.ai 公开材料只说明"针对 large-scale implementation、automated research、performance optimization、complex debugging 四大场景做了 1M 训练",但未披露具体的中期训练(mid-training)数据构成、超参与 ablation。第三方无法独立复现"稳定性提升"的具体来源。
6. **第三方 benchmark 数字**:部分二手博客引用的"SWE-bench Pro 62.1 / HLE 40.5"等数字,溯源上多为 GLM-5.1 的回填或行业推测,**不应作为 GLM-5.2 的实测分数引用**。
7. **市场反应**:HN 讨论串整体偏正面但样本小(<100 评论),不构成对开发者社区真实使用体验的代表性采样。

## Recommendations

对**个人开发者 / 小团队**:
- 想要低门槛尝试 GLM-5.2 的话,先注册 GLM Coding Plan($18/月起),在 Claude Code / Cline / OpenCode 中按上文 base-URL + 模型名替换,3 分钟内可用。
- 建议将 Sonnet 和 Opus 两个 slot 都钉到 `glm-5.2[1m]`,并将 `CLAUDE_CODE_AUTO_COMPACT_WINDOW` 提到 1,000,000,让 1M 上下文真正发挥作用。
- 想验证 GLM-5.2 的 1M 工程可用性,建议用真实场景做 A/B:同一份 200K+ 文档/代码库,分别在 GLM-5.1 和 GLM-5.2 上跑同一组 query,看是否真的"不用 chunking"。

对**中型团队 / 中长程 agent 项目**:
- 1M 上下文 + IndexShare 对"整库重构""长规范单次消化"价值最大;短对话场景下使用 GLM-4.5-air 即可,避免每 token $1.40 的成本浪费。
- 关注后续 OpenRouter 路由是否上线——若能用 OpenRouter 统一结算与路由,有助于多模型 fallback 架构。
- 关注 FrontierSWE 这类长程 benchmark 后续是否被 Z.ai 公开具体分数——这会是 1M 真实可用性的关键信号。

对**企业架构师**:
- GLM-5.2 + MIT 许可证 + 1M 上下文,在"自部署大模型"成本结构上比 Llama 3.3 70B、Qwen3.6 27B、GLM-4.5 355B 都更"重型"——硬件预算需要 8×H200 起跳。
- "**no regional limits, technical access without borders**"是 Z.ai 公告原文承诺,合规场景下比 Llama 社区许可证更可预测。
- 等第三方 1M 长上下文评测(LongBench-V2、RULER、NoCha、∞Bench)出分后再做严肃采购决策;若只做 <200K 任务,GLM-5.1 的 $1.40/$4.40 性价比更优。
- "无传统 benchmark 发布"这一信号值得在企业尽调中保留问号——尤其是医疗 / 金融 / 法律等强监管场景下,缺少公开评测等同于缺少可审计证据。

对**研究者**:
- IndexShare 的具体实现与 DeepSeek DSA 的关系值得一篇 arxiv 综述或消融研究。
- 智谱用华为昇腾 + MindSpore 训练 744B 模型,本身就是中国 AI 算力栈的重要案例,值得跟踪其训练能耗、单 GPU 吞吐与海外 H100 训练的对比数据。
- 异步 RL 基础设施(generation / training 解耦)是该团队 2026 年的另一条重要叙事,值得关注后续技术博客。
- FrontierSWE 作为"长程 agent benchmark"是否会被业内采纳,值得 arxiv 综述或 Hugging Face Open-LEaderboard 形式的持续监测。

## Source Notes

本报告引用 90 个独立来源,其中**直接 web_fetch 抓取 12 个**(9 个一手 + 3 个二手),**包括 Z.ai 官方公告原文(由用户提供)**。其余来自 Tavily 抓取片段用于 cross-reference。

所有主张按以下标准归类:

- **verified**:至少 2 个独立来源支持,且至少 1 个为官方/一手(智谱官网 / OpenLM / HF / arxiv / 官方 X 公告)。
- **partially_verified**:官方一手缺失,仅二手源支持;或来源单一;或存在版本/路由状态不确定。
- **unverified**:无来源或来源相互矛盾。

> 报告**未引用**任何 `tmp/` 内本地文件作为支撑来源——所有 citation 均为外部 `http(s)://` 链接。

## Bibliography

1. Z.ai 官方博客:GLM-5.2(本次更新纳入的官方一手原文) — https://z.ai/blog/glm-5.2
2. Z.ai 官方 X 公告 — https://x.com/Zai_org/status/2065704919299235870
3. Z.ai 官方最新模型文档 — https://docs.z.ai/devpack/latest-model
4. Z.ai 官方定价页 — https://docs.z.ai/guides/overview/pricing
5. OpenLM 模型门户:GLM-5.2 — https://openlm.ai/glm-5.2/
6. Hugging Face 模型卡:`zai-org/GLM-5.2` — https://huggingface.co/zai-org/GLM-5.2
7. arxiv 2602.15763:GLM-5 技术报告 — https://arxiv.org/abs/2602.15763
8. MarkTechPost(2026-06-14):"Z.ai Launches GLM-5.2…" — https://www.marktechpost.com/2026/06/14/z-ai-launches-glm-5-2-with-a-usable-1m-token-context-two-thinking-effort-levels-and-no-benchmarks-at-launch
9. KuCoin News(2026-06-13):"Z.AI Launches GLM-5.2 with 1M Token Context Window on Hugging Face" — https://www.kucoin.com/news/flash/z-ai-launches-glm-5-2-with-1m-token-context-window-on-hugging-face
10. Hacker News 讨论串 #48518684 — https://news.ycombinator.com/item?id=48518684
11. VentureBeat:IndexCache 稀疏注意力优化器 — https://venturebeat.com/technology/indexcache-a-new-sparse-attention-optimizer-delivers-1-82x-faster-inference
12. OpenRouter 列表:`z-ai/glm-5.2` — https://openrouter.ai/z-ai/glm-5.2
13. OpenRouter Compare 页面 — https://openrouter.ai/compare/z-ai/glm-5.2
14. YouTube / AICodeKing:"GLM-5.2 (Fully Tested)" — https://www.youtube.com/watch?v=MkFThJWJgg8
15. GitHub:`zai-org/GLM-5` — https://github.com/zai-org/GLM-5
16. Z.ai 官方 Chat — https://chat.z.ai
