---
title: "DeepSeek 开源昇腾基础组件：国模×国算深度耦合，软件生态墙出现系统性裂缝"
date: 2026-10-02
draft: false
tags: ["DeepSeek", "昇腾", "华为", "TileLang", "国产算力", "开源"]
description: "DeepSeek 9月30日官宣开源面向华为昇腾的六大基础设施组件，与 NVIDIA 版 API 一一对应，配套昇腾950 128卡超节点。国产大模型第一次以自用验证过的软件栈，反向定义国产算力的软件生态。"
slug: "deepseek-ascend-opensource-2026"
summary: "六个组件、一天之内、API 与 NVIDIA 版对齐——DeepSeek 把训练验证过的整套基础设施搬上昇腾950。'软件生态墙'第一次出现系统性裂缝。"
ShowToc: true
TocOpen: false
---

## 一句话结论

> **DeepSeek 把自家训练验证过的整套基础设施——从编程语言 TileLang，到 GEMM、分布式通信、注意力算子——一次性搬上了昇腾 950，API 与 NVIDIA 版对齐，性能宣称逼近硬件极限。这是国产大模型第一次以"自用验证过的软件栈"反向定义国产算力的软件生态，"软件生态墙"第一次出现了系统性的裂缝。**

---

## 1. 事件：9 月 30 日发生了什么

2026 年 9 月 30 日上午，DeepSeek 通过官方微信公众号宣布：正式开源面向华为昇腾算力平台的基础设施组件，涵盖 TileLang 高级语言编译工具、计算库、分布式通信库。路透、IT之家、CNMO 等多家媒体一致确认了时间和渠道。

关键时间线（仓库创建时间均为 GitHub 一手核验）：

| 日期 | 事件 |
|---|---|
| 2025-01-20 | TileLang 开源（北大团队主导，tile-ai/tilelang） |
| 2025-02-13 / 17 / 21 | DeepGEMM、DeepEP、FlashMLA 面向 NVIDIA 开源 |
| 2026-04-22 | TileKernels 开源（先行支持 CUDA） |
| 2026-09-09 / 10 | DeepSelect 建仓 / v1.0.0（先行支持 CUDA） |
| 2026-09-29 15:49 UTC | deepseek-ai/DeepGEMM-Ascend 仓库创建 |
| 2026-09-30 00:44 UTC | deepseek-ai/DeepEP-Ascend 仓库创建 |
| **2026-09-30 上午** | **DeepSeek 官方微信公众号发布公告** |
| 2026-09-30（同日） | 六个组件全部获得昇腾版本/后端；华为计算官微、麒麟公众号发文呼应 |

注意一个细节：DeepGEMM-Ascend 和 DeepEP-Ascend 两个仓库是在公告前 1 天和当天凌晨建仓的——这是有备而来的"同日发布"，不是临时起意。

---

## 2. 开源了什么：六个组件，一套完整软件栈

这次不是开源一个算子，而是一套从语言到通信的完整栈：

| 组件 | 仓库 | 协议 | 昇腾版关键数据（项目方自测） |
|---|---|---|---|
| **TileLang**（高级语言编译工具） | tile-ai/tilelang（同一仓库新增 Ascend 950 后端） | 未明确（GitHub 显示 Other） | 原生代码生成、自动调度/同步、SIMD/SIMT 向量编程 |
| **DeepGEMM-Ascend**（通用矩阵运算） | deepseek-ai/DeepGEMM-Ascend（独立仓库） | MIT | Dense GEMM 达硬件极限 98.3%–99.8%（950DT 实测） |
| **DeepEP-Ascend**（大规模跨设备通信） | deepseek-ai/DeepEP-Ascend（独立仓库） | ⚠️ 未声明（无 LICENSE 文件） | 公开 buffer API 与 NVIDIA 版对齐；EP≤32 时 dispatch 达物理带宽上限 90–95% |
| **TileKernels**（向量计算/访存算子） | deepseek-ai/TileKernels（同仓库第二后端） | MIT | 同一 Python API，运行时自动选择 NVIDIA/Huawei 后端 |
| **FlashMLA**（稀疏注意力） | deepseek-ai/FlashMLA（同仓库发布） | MIT | 昇腾 prefill 410 TFlops（95% 硬件峰值）、decode 360 TFlops（83%） |
| **DeepSelect**（高效数据筛选） | deepseek-ai/DeepSelect（同仓库发布） | MIT | 昇腾 TopK 较原生 torch.topk 快 2–20 倍 |

依赖关系（一手）：DeepGEMM-Ascend 依赖 tilelang 与 DeepJIT（运行时 JIT 编译）；DeepEP-Ascend 的 Ascend C 内核使用 HCCL/HCOMM、UBMEM、URMA，经 DeepJIT 运行时编译。目标硬件统一为昇腾 950（950DT）+ CANN 9.2/9.20。

**两个提醒**：以上性能数字均为项目方自测，无独立第三方复测；DeepEP-Ascend 仓库目前没有 LICENSE 文件，引用时注意——可能是疏漏，待后续提交观察。

---

## 3. "与 NVIDIA 版一一对应"：是真的，但有个细微差别

核验结论：**基本成立**。

NVIDIA 原版六个组件（DeepGEMM 2025-02-13、DeepEP 2025-02-17、FlashMLA 2025-02-21、TileKernels 2026-04-22、DeepSelect 2026-09-09、TileLang 2025-01-20）**全部在 2026-09-30 同日获得了昇腾版本或后端**。更有信号意义的是：NVIDIA 版 DeepGEMM 和 DeepEP 的 README 在 9 月 30 日当天**主动添加了指向 Ascend 版本的 News 条目**——DeepSeek 自己在 NVIDIA 的地盘上给昇腾版引流。

细微差别在于组织形式：只有 DeepGEMM 和 DeepEP 开了独立的 `-Ascend` 仓库，FlashMLA、TileKernels、DeepSelect 是在同一仓库内新增昇腾后端。所以"一一对应"是**功能/API 层面**的对应——DeepGEMM-Ascend 声明"fully API-compatible with DeepGEMM"，TileKernels 声明"the same Python APIs run on both NVIDIA GPUs and Huawei NPUs"——而不是仓库数量的一一对应。

---

## 4. 为什么 TileLang 是关键：这次开源的"题眼"

TileLang 是什么？一句话：**一个基于 TVM 编译器基础设施、采用 Python 式语法的面向高性能 AI 算子的领域专用语言（DSL），主打"编程简单 + 触达硬件性能上限"，定位是可跨芯片的 CUDA 替代编程层**。由北大团队主导开发，2025 年 1 月开源，路线先在英伟达成熟平台上验证——如今已承载 DeepSeek V4 系列模型训练中大部分算子的实现。

它在昇腾落地的意义有三层：

1. **降门槛**：对昇腾 Ascend C 底层指令做封装，提供高级语言编程方式而"不损失硬件性能"（公告原话）。国产芯片最缺的不是峰值算力，是能让普通开发者写出高性能算子的工具。
2. **解耦合**：同一套 Python API 跑 NVIDIA GPU 和华为 NPU，运行时自动选后端（TileKernels 已实现）。这就是"一次编写，多架构运行"——把 CUDA 生态的迁移成本问题，转化为中立语言层的复用问题。
3. **定标准**：华为侧以开放 Ascend C API 与 PTO ISA 底层指令体系支撑对接，并配套 ASC-COMM 自定义通信编程库。语言—算子库—通信库—超节点组网，一条完整软件栈就此成形。

公告里最有分量的一句话是："**目前，DeepSeek 训练中用到的每一个 TileLang 算子，在昇腾上都有对应的高性能实现。**"注意证据等级：这是一手单方说法，旁证均为 DeepSeek/tile-ai 自述，无独立第三方验证；且 DeepEP-Ascend README 自己承认"更大规模与 combine 仍在优化"。绝对化表述之下有自我保留，读的时候打个折。

---

## 5. 昇腾 950 的 128 卡超节点：不止是开源，更是联合定义硬件用法

公告确认了一件事（一手）："双方紧密合作，共同推进基于昇腾 950 的 128 卡超节点方案，共同对计算与通信进行深度优化。"

技术细节来自华为计算官微（经媒体转述，二手，未独立复核）：联合定义的 SuperPoD Flex / UBL128 组网方案，128 卡 3.2Tbps 单层交换 Scale-up、256K 卡两层交换 Scale-out，目标是"超低时延推理和前沿基座模型的大规模训练"。

配套动作（均为二手转述）：华为把联合创新成果在 CANN 社区开源（覆盖低延迟推理部署、单卡/单机部署、大规模训练）；DeepEP-Ascend README（一手）披露完整带宽需要 Atlas 850E 的 Q3 商用固件，计划 2026 年 10 月 15 日前后公开。

解读：DeepSeek 不只是在"适配"昇腾，而是在和华为**联合定义超节点这个形态的硬件应该怎么用**。超节点是 2026 年大模型基础设施竞争的主战场——谁定义了超节点的软件栈，谁就定义了下一代训练/推理的入场券。

---

## 6. 生态意义：系统性拆除"软件生态墙"

此前昇腾的困境众所周知：硬件具备竞争力，但受制于 CUDA 生态的迁移成本，大量开发者难以把训练任务迁过来。芯片厂商自己建生态，缺的是**真实 workload 的验证**——没有头部模型在上面跑通，工具链再全也是纸面繁荣。

这次不一样的三点：

1. **从工具链和核心库层面铺"软件高速公路"**：开源的不是 demo，是 DeepSeek 自己训练推理在用的算子库。开发者迁过来的不是"兼容层"，是"生产环境验证过的代码"。
2. **模型厂商向下定义算力**：历史上是芯片厂商求模型厂商适配；这次是头部模型厂商带着验证过的软件栈，反向定义算力平台的软件生态。议价权易手了。
3. **中立语言层替代 CUDA 绑定**：TileLang 的"一次编写，多架构运行"如果跑通，CUDA 的护城河就从"语言绑定"退化成"先发生态"——护城河还在，但变窄了。

一句话：国产 AI 芯片竞争的焦点，正在从硬件性能转向"编程工具与算子体系"。

---

## 7. 产业链视角：超节点放量，电源/DrMOS 环节直接受益（市场观点）

> ⚠️ 本节为**卖方研报与市场观点口径**，未经独立核实，不构成投资建议。

逻辑链很直接：128 卡超节点放量 → 单卡功率密度和整机功耗墙抬升 → 电源管理（DrMOS/多相供电）单机价值量上升。国产替代叙事下，本土电源链厂商的份额弹性最大。

以杰华特为例（研报口径）：26H1 DrMOS 已在大算力客户率先放量，在其加单催化下，多项电源和 DrMOS 产品加速放量，国产化份额有望持续提升；研报预期国产化需求 + 客户放量带动 26H2 及 27 年营收强势增长。市场将其视为"Drmos 国产化大趋势"的核心标的之一。

提醒：以上为券商/市场传言口径，"放量""加单"等说法无上市公司公告或独立数据支撑。超节点主题的兑现节奏取决于昇腾 950 超节点的实际出货，而非开源本身——开源是必要非充分条件。

---

## 8. 证据等级说明（本文的方法论）

| 等级 | 内容 |
|---|---|
| ✅ 一手已核验 | 公告真实发生（路透确认渠道）；六个仓库的存在、创建时间、README 内容（2026-10-02 直接抓取 GitHub）；"一一对应"的功能/API 对应关系 |
| ⚠️ 一手单方说法 | "每个 TileLang 算子都有昇腾高性能实现"；各仓库性能数据（项目方自测）；128 卡超节点的存在性（公告原文） |
| ⚠️ 二手转述 | 华为官微的超节点组网细节、CANN 社区开源、Atlas 850E 固件时间表 |
| ❌ 已排除传言 | "寒武纪/海光同日适配""梁文锋闭门会表态""TileLang 替代 Triton 的 ICLR 数据""内蒙古 16 万卡"——均无可靠信源，不引用 |

---

## 附录：DeepSeek 原始公告全文（复原）

> **说明**：WeChat 原文无法直接抓取。以下段落在 CNMO、IT之家/凤凰网、多家网易号报道中**逐字一致**，可视为接近原文的复原。CNMO（2026-10-02）引用最完整。媒体导语中"所有组件与此前面向英伟达平台的开源组件一一对应"为转述措辞，非公告原文，但"一一对应"为公告核心要点之一。

建立新一代自主可控的GPU软件生态，首要任务是建立一个通用、编程简单且能达到硬件性能上限的高级语言。TileLang正是在这一背景下诞生。相对于英伟达的CUDA语言，TileLang编程更简单，能显著提高开发效率、简化代码逻辑；相对于其他同类高级语言，TileLang的编程模型可以充分发挥芯片特性，达到硬件性能上限。TileLang路线首先在英伟达成熟平台上得到验证，如今已承载DeepSeek V4系列模型训练中大部分算子的实现，是探索AGI新范式、开发高性能算子的核心工具。

本次开源的TileLang昇腾版本，对昇腾Ascend C底层指令进行封装，提供高级语言的编程方式，同时不损失硬件性能。目前，DeepSeek训练中用到的每一个TileLang算子，在昇腾上都有对应的高性能实现。DeepSeek希望TileLang昇腾版本作为开源工作，能对更多AI芯片建立高可用软件生态起到示范作用。

本次开源还包括昇腾平台核心计算与通信组件，为不同使用场景提供可复用的基础能力。其中，DeepGEMM加速通用矩阵运算；DeepEP提供高效的大规模跨设备通信；TileKernels提供数据处理所需的常规向量计算和访存算子；FlashMLA提供稀疏注意力算子，提升长上下文处理效率；DeepSelect实现高效的数据筛选。在多项关键测试用例中，上述组件的计算与通信性能已接近硬件上限。

在面向昇腾平台的研发过程中，华为团队给予了毫无保留的大力支持。双方紧密合作，共同推进基于昇腾950的128卡超节点方案，共同对计算与通信进行深度优化。DeepSeek表示，将持续推进技术创新，与社区共同建设开放的软件生态、共同进步。

---

## 信源

**一手（2026-10-02 直接抓取 GitHub）**：
- tile-ai/tilelang：https://github.com/tile-ai/tilelang
- deepseek-ai/DeepGEMM-Ascend：https://github.com/deepseek-ai/DeepGEMM-Ascend
- deepseek-ai/DeepEP-Ascend：https://github.com/deepseek-ai/DeepEP-Ascend
- deepseek-ai/TileKernels：https://github.com/deepseek-ai/TileKernels
- deepseek-ai/FlashMLA：https://github.com/deepseek-ai/FlashMLA
- deepseek-ai/DeepSelect：https://github.com/deepseek-ai/DeepSelect

**二手**：
- 路透（2026-09-30）：https://www.reuters.com/world/asia-pacific/deepseek-partners-with-huawei-develop-chip-programming-tools-reducing-reliance-2026-09-30/
- CNMO 公告转述：https://ai.cnmo.com/news/819700.html
- IT之家/凤凰网：https://tech.ifeng.com/c/8wpwu6MVfRV
- 华为回应（新浪财经转述）：https://finance.sina.com.cn/stock/t/2026-09-30/doc-initqvax6962991.shtml
- 量子位报道转引：https://abmedia.io/deepseek-ascend-open-source-components
