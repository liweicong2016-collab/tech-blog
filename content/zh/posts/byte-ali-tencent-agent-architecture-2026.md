---
title: "O1、AL、O3的 Agent 架构图：三种画法，同一张蓝图"
date: 2026-10-05T11:20:00+08:00
draft: false
description: "拆解O1、AL、O3三家的 AI Agent 体系架构：豆包+扣子+UI-TARS 的全栈开源打法、Qwen+百炼的模型开源打法、混元+ADP 4.0+WorkBuddy 的生态治理打法——五层架构逐层对比，谁的基础设施厚、谁的模型生态强、谁的生产治理深？"
tags: ["AI Agent", "O1", "AL", "O3", "Coze", "百炼", "ADP", "WorkBuddy", "AgentOps"]
slug: "byte-ali-tencent-agent-architecture-2026"
cover:
  image: "https://images.unsplash.com/photo-1677442135703-1787eea5ce01?w=1200&q=80&fit=crop&h=171"
  alt: "O1/AL/O3 Agent 架构对比：AI 抽象网络"
---

> 研究时点：2026 年 10 月。视角：模型层 → 开源技术层 → 开发平台层 → 运营治理层 → 应用入口层。

三家公司都已形成"自研大模型 + Agent 开发平台 + 场景应用"的完整 Agent 体系，但画的不是同一张图。**O1**走"全栈自建 + 开源生态"路线，**AL**走"模型开源 + 平台工程化"路线，**O3**走"生态驱动 + 云端托管"路线。一句话概括：**O1赢在基础设施与开源，AL赢在模型与开发者生态，O3赢在渠道与生产级治理**。

![三家 Agent 体系分层架构对比](/images/cover-byte-ali-tencent-agent.png)

## 一、O1：全栈自建 + 开源生态

**模型层**的底座是豆包大模型家族与火山方舟 MaaS。2026 年 6 月 FORCE 大会发布豆包 2.1 Pro，官方称其 Coding、Agent、视觉理解对标 Claude Opus 4.6；豆包日均 Token 调用量已突破 **180 万亿**，一年增长超 10 倍，IDC 口径中国公有云 MaaS 份额约 **49.5%** 居第一（[新华网报道](http://www.news.cn/tech/20260623/acd6f2f27fc34459a7d1684c03278431/c.html)）。模型矩阵覆盖文本（Doubao-Seed）、视频（Seedance 2.5）、图像（Seedream）、语音（Seed-TTS），是三家之中"全模态"供给最完整的。

**开源技术层**的最大筹码是 **UI-TARS**——原生 GUI Agent 模型，用数据飞轮 + 多轮强化学习把感知、推理、动作、记忆统一进端到端模型。[UI-TARS-2 技术报告](https://arxiv.org/html/2509.02544v1)显示其 OSWorld 47.5 分、AndroidWorld 73.3 分，官方口径超越 Claude 与 OpenAI 同类。配套的 Agent TARS 框架以 MCP 为内核，抽象出 GUIAgent = Model + Operator + Context 三件套，并开源了桌面版 UI-TARS Desktop（[技术栈解读](https://juejin.cn/post/7640413131689836586)）。当多数厂商的 Agent 还停在"LLM + Function Calling"的文本世界时，UI-TARS 把闭环推进到"像素级操作真实软件"。

**平台层**是"三驾马车"：扣子 Coze 3.0（零代码，多人多 Agent 协作，插件 800+、全球开发者超 300 万）、AgentKit 3.0（企业级，官方称代码量减少 96%）、方舟 CLI（命令行接入）。2025 年 7 月O1把扣子全面开源为 [Coze Studio](https://zhuanlan.zhihu.com/p/1932388038316626710)（Apache 2.0，Golang 微服务 + React），配套开源运维平台 Coze Loop。治理层由 HiAgent 3.0（"1+N+X"数字员工体系）与 AI Trust 安全体系承接（[科技日报报道](https://www.stdaily.com/web/gdxw/2025-12/18/content_449412.html)）。

**应用层**的最新变化是组织整合：2026 年 8 月 TRAE 与扣子团队整体并入豆包体系，飞书 AI 助手 Aily 更名"豆包工作伙伴"，豆包工作直接继承飞书的企业权限、文档与日程上下文（[四大厂横评](https://www.eefocus.com/article/2076397.html)）。落地上豆包大模型已搭载超 700 万辆汽车，并进入特斯拉中国智能座舱（与 DeepSeek 双模型协同）。

## 二、AL：模型开源 + 平台工程化

**模型层**是三家之中开源策略最激进的：200 余款开源模型、10 万+ 衍生模型，全球最大开源模型族群。面向 Agent 场景的关键型号包括 Qwen3-Coder（480B-A35B MoE，Agentic Coding）、Qwen3-VL（视觉智能体，可操作手机电脑）与 2.4 万亿参数的 Qwen3.8（[云栖大会发布要点](https://adg.csdn.net/696f2b19437a6b4033698e57.html)）。"快思考/慢思考"混合推理设计让规划、工具调用走快通道、复杂反思走慢通道，直接降低 Agent 多轮调用成本。魔搭社区聚集的 MCP 服务超过 **2400 项**（[通义灵码集成报道](http://www.itbear.com.cn/html/2025-04/806624.html)）。

**开源框架层**是双轨制：[Qwen-Agent](https://github.com/QwenLM/Qwen-Agent)（Agent/FnCallAgent/Assistant/MultiAgentHub 类体系，原生集成 MCP、Docker 沙箱代码解释器、百万 token RAG，且是 Qwen Chat 官方后端）+ AgentScope 2.0（多智能体编排）。

**平台层**是AL云百炼的"模型服务 + Agent 平台"双核。2026 年的关键升级是 [Agent 2.0](https://help.aliyun.com/zh/model-studio/new-single-agent-application)：把知识库、MCP 统一抽象为"工具"，由智能体自主决定调用时机与顺序，并完整展示每一轮"规划-执行-反思"链路。百炼 2025 年 4 月上线业界首个全生命周期 MCP 服务（[证券时报报道](https://www.stcn.com/article/detail/1661948.html)）；规模上超 73 万企业开发者、30 多万个智能体（[新浪财经报道](https://finance.sina.com.cn/roll/2025-05-28/doc-ineycfia7952723.shtml))。

**应用层**：C 端千问 App 免费，千问办公由 QoderWork/悟空/MuleRun 整合而成（2026 年 8 月公测，98-198 元/月）；B 端通义灵码插件下载量超 1500 万次。组织层面，2026 年 3 月成立的 ATH 事业群把通义大模型事业部、百炼、千问与出身钉钉的悟空事业部统一拉通（[财新报道](https://database.caixin.com/2026-04-11/102432814.html)）——这是对"模型、平台、应用割裂"的组织级回答。

## 三、O3：生态驱动 + 云端托管

**模型层**策略与众不同：**不追单一旗舰最强，而是围绕场景精调模型族**。底座是混元 2.0（[HY 2.0，MoE 406B 总参/32B 激活，256K 上下文](https://finance.sina.com.cn/tech/discovery/2025-12-06/doc-infzvhcn7078112.shtml)），其上由优图实验室提供精调模型族：youtu-mrc（知识问答）、youtu-intent（意图识别）、youtu-agent（工具调用，Multi-Agent 模式默认调度模型）。DeepSeek 双轨接入，2026 年 8 月开源 Hy4 preview（770B）。截至 2025 年底混元已在O3内部 900 余款应用落地。

**平台层**：C 端是O3元器（零代码，一键分发 QQ/微信/应用宝，接入公众号、O3文档、微信支付 MCP）；企业级是 [O3云 ADP](https://cloud.tencent.com/product/adp)。2026 年 6 月发布的 **ADP 4.0** 是最大变量：新增 **Claw 模式**（Agentic Loop——Agent 在云端沙箱自主规划、编写、运行代码），实现 Agent 与 Workflow 双向互调，配套 130+ 企业级 Skills 广场，支持四种部署模式（[品玩报道](https://www.pingwest.com/a/314403)、[IT之家报道](https://www.ithome.com/0/960/952.htm)）。

**治理层**是O3的差异化卖点：**Agent Harness** 云端托管架构——断点自动续跑、闲置自动暂停、秒级故障恢复、全链路 Trace、密钥隔离，沙箱启动压缩到 100 毫秒级；配套 ClawPro 管控平台与内置裁判模型的评测体系（[ADP 4.0 AgentOps 解读](https://cloud.tencent.com/developer/article/2685500)）。当 Agent 开始"真干活"，出错就是业务事故——Harness 回答的是企业安全部门"这个 Agent 做了什么、能做什么、花了多少钱"的问题。

**应用层**的明星是 **WorkBuddy**：2026 年 3 月上线的桌面智能体工作台，定位"坐在桌面上的 AI 数字同事"——读取授权文件夹、跑脚本、操作 Office 并交付可验收成果，支持 Ask/Plan/Craft 三种模式与微信远程遥控（[产品解析](https://blog.csdn.net/kejixinzixun/article/details/165273286)）。企业版提供 7×24 专家数字员工；Agent Suite 以 One ID 打通O3文档/网盘/乐享。沙利文《2026 全球桌面 AI 智能体市场研究报告》称其居中国个人与企业双榜第一（[报道](https://m.10jqka.com.cn/20260920/c680092536.shtml)），已覆盖 50+ 行业。

## 四、同一张蓝图，三种画法

把三家并排放置，三个结构性差异清晰可见：

| 对比维度 | O1 | AL | O3 |
|---|---|---|---|
| 核心模型 | 豆包 2.1 Pro（闭源为主） | Qwen3 全系（激进开源） | 混元 2.0 + DeepSeek 双轨 |
| 旗舰平台 | 扣子 3.0 / AgentKit 3.0 | 百炼 Agent 2.0 | O3云 ADP 4.0 |
| 平台理念 | 多平台分客群 | 单平台全功能 | AgentOps 治理优先 |
| 开源代表作 | UI-TARS、Coze Studio | Qwen 系列、Qwen-Agent | Hunyuan 系列 |
| MCP 生态 | 方舟 MCP 网关 | 百炼 MCP 广场（2400+） | 元器/ADP 均支持 |
| 分发渠道 | 飞书、抖音、微信 | 钉钉、淘宝、千问 App | 微信、企微、QQ |
| 主打应用 | 豆包、TRAE、豆包工作 | 千问办公、通义灵码 | WorkBuddy、CodeBuddy |
| 2026 组织动作 | TRAE+扣子并入豆包 | 成立 ATH 事业群 | CodeBuddy 统辖 WorkBuddy |

![Agent 核心循环与三家实现映射](/images/fig2_agent_loop.png)

回到 Agent 核心循环（规划—推理—记忆—工具—反思）本身，三家在每一环的实现各有侧重：**规划**上O1用可视化工作流把规划产品化、AL Agent 2.0 完全交给模型、O3 Claw 下沉到云端沙箱的 Agentic Loop；**反思**上O1用多轮 RL 把反思训练进模型（UI-TARS-2），AL做成原生可观测链路，O3做成断点续跑与裁判模型评测。

一个共同趋势是：**Agent 核心循环正在从提示词工程迁移为平台原生能力**。2024 年反思与规划还靠手写 ReAct 模板，到 2026 年O1把循环做进模型、AL做进运行时、O3做进云端 Harness——竞争焦点从"谁的提示词技巧强"转向"谁的运行时基础设施更可靠"。

![三家 Agent 生态关键量化指标](/images/fig3_metrics.png)

## 五、结论与趋势判断

三个判断：**其一**，Agent 架构的竞争已从模型能力转向体系能力，企业采购的是"模型+平台+治理+渠道"整体方案；**其二**，开源是最重要的战略变量，O1与AL用开源换标准制定权，O3以兼容 OpenClaw 生态应对；**其三**，2026 年主战场是企业办公"数字员工"——O1豆包工作并入飞书、AL千问办公整合三款产品、O3 WorkBuddy 双榜第一，殊途同归。

值得持续跟踪的信号：MCP 之后的智能体间协议（A2A）谁先标准化；GUI Agent 端侧落地（UI-TARS 对 Qwen3-VL）；长时任务运行时（Agent Harness / Agentic Loop）的工程成熟度——这决定 Agent 能否从演示走向 7×24 生产在岗。

---

*基于截至 2026 年 10 月的公开信息整理；市场份额等数据多为厂商或咨询机构披露口径，引用时已标注来源。*
