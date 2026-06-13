---
title: "How many tokens can 1MW of electricity run? NVIDIA GPU energy efficiency analysis"
date: 2026-06-04T16:00:00+08:00
draft: false
tags: ["AI chip", "NVIDIA", "energy efficiency", "Compute", "Token", "H100", "B200"]
description: "Using 1MW of power as a baseline, compare the token generation efficiency of NVIDIA H100, H200, and B200, analyzing energy efficiency gaps and constraints."
summary: "英伟达H100每MW可部署约1400张卡，生成约18-22T Token/MWh；B200性能大幅领先，Token效率可达36T/MWh，是下一代AI推理的顶配选择。"
ShowToc: true
TocOpen: false
---

## Background: Why Measure in "Token / MW"?

In the AI compute race, **power is the ultimate constraint**. No matter how powerful the chips are, ultimately it comes down to "how many tokens can be generated per unit of electricity cost."

This metric combines:
- GPU power consumption (TDP)
- GPU compute capability (TFLOPS)
- Number of GPUs (limited by power envelope)
- Actual inference efficiency (affected by memory bandwidth and interconnect bandwidth)

---

## Core Data Comparison

### GPU Specifications Table

| Chip | TDP (W) | FP16 Compute (TFLOPS) | Memory Bandwidth | Memory | Architecture |
|---|---|---|---|---|---|
| **H100 SXM5** | 700 | 3,956 | 3,350 GB/s | 80GB HBM3 | Hopper |
| **H200 SXM** | 700 | 3,956 | 4.8 TB/s | 141GB HBM3e | Hopper |
| **B100** | 700 | 14,400 | ~3.2 TB/s | 192GB HBM3e | Blackwell |
| **B200 SXM** | 1,000 | 20,000 | ~8 TB/s | 192GB HBM3e | Blackwell |

> Data source: NVIDIA official whitepapers

---

## Theoretical Compute: How Many Cards per MW?

$$N_{cards} = \frac{1{,}000{,}000 \text{ W}}{TDP_{per\_card}}$$

| Chip | Single Card Power Consumption | Cards per MW |
|---|---|---|
| H100 / H200 | 700W | ~1,428 cards |
| B100 | 700W | ~1,428 cards |
| B200 | 1,000W | 1,000 cards |

---

## FP16 Compute: Total Compute per MW

$$P_{MW} = N_{cards} \times FP16_{per\_card}$$

| Chip | FP16 per Card | Cards per MW | Total Compute per MW |
|---|---|---|---|
| H100 | 3,956 TFLOPS | 1,428 | **5.65 PFLOPS** |
| H200 | 3,956 TFLOPS | 1,428 | **5.65 PFLOPS** |
| B100 | 14,400 TFLOPS | 1,428 | **20.6 PFLOPS** |
| B200 | 20,000 TFLOPS | 1,000 | **20 PFLOPS** |

**Conclusion**: The B100, leveraging the Blackwell architecture, achieves **3.6x** the total compute of the H100 at the same power.

---

## Token Generation Efficiency Estimate

### Estimation Method

FP16 compute ≠ Token generation amount. Actual efficiency depends on:
1. **Memory Bandwidth**: Determines data supply speed
2. **Interconnect Bandwidth**: Determines multi-card collaboration efficiency
3. **Model Size**: Larger models bottleneck on memory bandwidth
4. **Batch size**: Batching can improve utilization

**Estimation Baseline**: Using Llama-70B model as an example

| Chip | Token/s per Card (Estimated) | Reference |
|---|---|---|
| H100 SXM | 2,500 – 4,000 tok/s | Llama-70B @ FP16 |
| H200 | 3,000 – 5,000 tok/s | Same, boosted by HBM3e |
| B100 | 7,000 – 10,000 tok/s | Blackwell architecture improvement |
| B200 | 8,000 – 12,000 tok/s | Boosted by NVLink 5.0 |

---

## Token / MWh Comparison

$$\text{Token per MWh} = \text{Token/s per card} \times N_{cards} \times 3600$$

### Static Deployment (No Downtime Considered)

| Chip | Token/s per Card | Cards per MW | **Token / MWh (Static)** |
|---|---|---|---|
| H100 | 3,500 | 1,428 | **17.9 T** |
| H200 | 4,200 | 1,428 | **21.6 T** |
| B100 | 8,500 | 1,428 | **43.7 T** |
| B200 | 10,000 | 1,000 | **36.0 T** |

> T = trillion (10¹²)

### Dynamic Utilization (Considering Real Deployment Efficiency)

In real inference, GPUs cannot run at 100%. Accounting for peak utilization rate:

| Chip | Static Token/MWh | Utilization @70% |
|---|---|---|
| H100 | 17.9 T | **12.5 T** |
| H200 | 21.6 T | **15.1 T** |
| B100 | 43.7 T | **30.6 T** |
| B200 | 36.0 T | **25.2 T** |

---

## Core Conclusions

### 1. The B200 is the GPU with the Highest Token Efficiency

The B200’s token efficiency per MW is approximately **2x** that of the H100, and total compute is **3.6x** that of the H100.

Key advantages of the Blackwell architecture:
- **NVLink 5.0**: 1.8 TB/s bidirectional interconnect, completely eliminating multi-card communication bottlenecks
- **192GB HBM3e**: Fits a 70B+ model on a single card, enabling larger batch sizes
- **20 PFLOPS FP16**: Dramatically improves compute per unit of power

### 2. The H200 is the Most Balanced Choice Currently

The H200 uses the same power consumption as the H100 (700W), but with 141GB HBM3e memory:
- Memory capacity increased by 76%
- Memory bandwidth increased by 43%
- Token efficiency ~**20%** higher than H100

For enterprises with existing H100 clusters, upgrading to H200 is the most cost-effective choice.

### 3. Interconnect Bandwidth is the Core Bottleneck

For large model inference, NVLink is the lifeline:
- A 70B model does not fit on a single card, requiring multi-card parallelism
- HCCS/PCIe bandwidth is far lower than NVLink, significantly reducing multi-card utilization
- The B200’s NVLink 5.0 (1.8 TB/s) is **2x** faster than the H100’s NVLink 4.0 (900 GB/s)

### 4. Power vs. Compute Trade-off

The B200’s power consumption is 43% higher than the H100 (1000W vs 700W), but total compute is 3.6x that of the H100.

This means:
- Data center cooling design needs upgrading
- Fewer racks per MW, but total compute greatly increases
- **Actual power cost per token drops by 50%+**

---

## Quick Reference

| Metric | H100 | H200 | B100 | B200 |
|---|---|---|---|---|
| Cards per MW | 1,428 | 1,428 | 1,428 | 1,000 |
| FP16 per MW | 5.65 PFLOPS | 5.65 PFLOPS | 20.6 PFLOPS | 20 PFLOPS |
| Token/MWh (Static) | 17.9 T | 21.6 T | 43.7 T | 36.0 T |
| Token/MWh (@70%) | ~12.5 T | ~15 T | ~30.6 T | ~25 T |
| Primary Advantage | Mature and stable | Large memory | High compute | Interconnect bandwidth |

---

*Data sources: NVIDIA official whitepapers, AnandTech, Semianalysis, and other analysis reports; estimates based on 2024-2025 measured data.*
