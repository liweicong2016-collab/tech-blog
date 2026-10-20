---
cover:
  image: "/tech-blog/images/covers/deepinfer-opensource-2026.jpg"
  alt: "DeepInfer 开源：离线推理核已交付，线上全家桶还没交出来"
title: "DeepInfer 开源：降本军备赛进到引擎层，线上全家桶还没交出来"
date: 2026-10-21T00:00:00+08:00
draft: false
tags: ["DeepSeek", "DeepInfer", "昇腾", "Blackwell", "开源", "推理", "API"]
description: "DeepSeek 开源离线推理核 DeepInfer（Apache-2.0）与协议层 deepseek-recipe（MIT）。README 写明 KV cache、Prefill/Decode 分离、多副本负载均衡未开源；硬件白名单仅 NVIDIA SM100 与昇腾 950。$0.15 / $0.60 是闲时 cache miss 价。"
slug: "deepinfer-opensource-2026"
summary: "降本军备赛进入开源引擎阶段；缺的三块基建才是完整线上形态。"
ShowToc: true
TocOpen: false
---

> 基于 2026-10-20 公开仓库与官方定价核验。名称以正式名 **DeepInfer** 为准。

## 结论

DeepSeek 把支撑 V4.1-Flash 线上服务的**离线推理核** DeepInfer（Apache-2.0）和协议层 deepseek-recipe（MIT）开源了出来——对私有化最值钱的是「和官方 API 同款的编解码对齐」。但 README 写得很实在：KV cache 系统、Prefill/Decode 分离、多副本负载均衡**没放**；硬件白名单只有 **NVIDIA SM100** 与 **华为昇腾 950**。$0.15 / $0.6 是**闲时 cache miss** 价，不是全日统一价；真正杀招是 cache hit。一句话：**降本军备赛进入开源引擎阶段；缺的三块基建才是完整线上形态。**

---

## 1. 发生了什么

全网还在猜 V4.1 Flash 如何把每百万 token 输入压到约 **$0.15**、输出约 **$0.6** 时，DeepSeek 自己掀了底牌：用开源仓库交出生产推理路径里可复用的那一层。

| 仓库 | 协议 | 角色 |
|---|---|---|
| [deepseek-ai/DeepInfer](https://github.com/deepseek-ai/DeepInfer) | Apache-2.0 | 离线推理引擎（优化算子、分布式推理、投机解码、SWA Bounded Replay、结构化输出等） |
| [deepseek-ai/deepseek-recipe](https://github.com/deepseek-ai/deepseek-recipe) | **MIT**（不是 Apache） | 协议转换 + prompt/tokenizer；**不跑推理**，对齐官方 API 行为 |

定位诚实：README 写它 powers production services，但开源交付物明确是 **offline inference**。媒体转述「后续新模型推理代码会持续合入」——**README 无此句**，当软承诺，勿当 SLA。

---

## 2. 定价：别把闲时价当成牌面

官方 [API Pricing](https://api-docs.deepseek.com/quick_start/pricing/)（`deepseek-flash` / V4.1-Flash）：

| 口径 | 输入 | 输出 |
|---|---|---|
| **闲时 · cache miss** | **$0.15 / 1M** | **$0.60 / 1M** |
| 高峰 | $0.30 | $1.20 |
| **闲时 · cache hit** | **~$0.003** | — |

传播层常把「$0.15 / $0.6」说成统一价；工程上 Agent 账单真正吃的是 **cache-hit 率 × 峰谷窗口 × 工具调用轮次**。

---

## 3. README 里最该看的边界

已开源（功能属实）：高性能算子、Attention DP/CP、MoE EP+EPLB、DSpark 投机解码、SWA bounded replay、异步调度、batch-invariant、结构化输出等。

**明确未开源：**

1. KV cache 系统
2. Prefill / Decode **分离部署**
3. DP 多副本负载均衡

![DeepInfer 开源边界：离线推理核与协议层已交付，KV cache 系统、Prefill/Decode 分离部署、多副本负载均衡未开源；硬件白名单仅 NVIDIA SM100 与昇腾 950](/tech-blog/images/deepinfer/fig-deepinfer-missing-pieces.jpg)

**硬门槛：** 仅认 NVIDIA **Blackwell SM100** 与华为 **Ascend 950**（CUDA 13 / CANN 9.2）；模型仅限 **DeepSeek-V4.1-Flash**。消费级卡免谈。

对私有化团队：recipe 抹平「本地服务 vs 官方 API」的格式与工具调用温差——这比再吹一遍开源口号更值钱。对单卡开发者：继续调几毛钱 API，比自己搭集群划算。

---

## 4. 产业信号：推理先于预训练，再一次被写进白名单

硬件白名单把 **SM100 与昇腾 950** 并列进第一梯队生产路径，和此前野村专家纪要、Bloomberg 等公开口径同向：国产加速器在**推理 / Serving** 渗透快于大规模预训练；大训仍偏 Nvidia 的叙事未被推翻，但适配订单应跟 **Serving、算子、recipe**，别写「已替代预训练」。

这与 2026-09-30 DeepSeek 开源昇腾六大基础组件（TileLang / DeepGEMM-Ascend 等）是同一条「亲写底层」曲线：模型厂向下定义算力软件栈，芯片厂跟着工程现实走。

---

## 5. 给三类人的动作清单

| 角色 | 动作 |
|---|---|
| 企业私有化 / 国产算力适配架构师 | 优先吃透 **deepseek-recipe** 编解码对齐 + DeepInfer 内核算子；对照 SM100 / 950 环境与 CANN/CUDA 版本 |
| Agent / API 选型 | 先算 cache-hit × 峰谷 × Harness，再比榜单；别只盯名义 token 价 |
| 单卡个人开发者 | 不必凑部署热闹；用官方 API |

---

## 6. 证据边界

| 等级 | 内容 |
|---|---|
| 一手已核验 | 两仓库存在、协议、README 硬件/模型白名单、未开源三组件、官方闲时/高峰/cache 价 |
| 媒体转述 | 「新模型推理代码持续合入」——README 无 |
| 观点 | 「让行业生产线长成它的形状」——传播修辞，非官方声明 |

---

## 信源

- https://github.com/deepseek-ai/DeepInfer
- https://github.com/deepseek-ai/deepseek-recipe
- https://api-docs.deepseek.com/quick_start/pricing/
- DeepSeek V4.1 Flash 官方发布说明（HBM/SSD KV 压缩、峰谷机制）
