---
title: "Middle Eastern Capital, Southeast Asian Computing Power: An Ongoing Industrial Migration"
date: 2026-05-23
draft: false
description: "When Saudi money started looking for outlets beyond Singapore, Thailand quietly became the answer. This isn’t a conventional market analysis—it’s more of a field observation about an ‘opportunity window’."
tags: ["Southeast Asia", "IDC", "Data Center", "AI Compute", "Middle East capital", "Thailand"]
slug: "middle-east-southeast-asia-ai-computing"
cover:
  image: "https://images.unsplash.com/photo-1512453979798-5ea266f8880c?w=1200&q=80"
  alt: "Dubai Skyline and Southeast Asian City Aerial Views"
  caption: "When capital starts looking for a new outlet, Southeast Asia becomes the answer."
ShowToc: true
---

![Data Center and AI Compute Cluster](https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=1200&q=80)
*Compute Infrastructure: The New Darling of Capital, a New Story for Southeast Asia*

---

## 1. Introduction

In March this year, I flipped through a research report on Southeast Asian data centers. The report was long and the conclusions were clear, but what made me pause was not the numbers—it was a seemingly unrelated fact:

**Middle Eastern sovereign wealth funds are reallocating assets on a massive scale.**

Saudi Public Investment Fund (PIF), Kuwait Investment Authority (KIA), Qatar Investment Authority (QIA), the Abu Dhabi Investment Authority (ADIA) — these names rarely appeared in the Southeast Asian tech real estate context before, but now, they are beginning to show up at negotiation tables in Bangkok.

What does this mean?

---

## 2. Why Middle Eastern Capital Is Moving

![Dubai Financial Centre](https://images.unsplash.com/photo-1512453979798-5ea266f8880c?w=800&q=80)
*Dubai Financial Centre, the Departure Point for Middle Eastern Sovereign Wealth Funds*

By early 2026, the geopolitical situation in the Middle East was keeping many people awake at night. Tensions between Iran and multiple countries continued to escalate, and regional security visibly declined. This is not the first large-scale outflow of Middle Eastern capital—historically, every regional conflict has been accompanied by a wave of capital flight to safety.

But this time, there is a new variable:

**Southeast Asia is no longer just a “receiving” role; it is becoming a destination with its own active appeal.**

Why? Several reasons stack up:

- Political relative stability: Thailand, Vietnam, and Indonesia are not embroiled in major geopolitical conflicts
- Solid economic growth: Southeast Asia’s GDP growth is maintained at 4%–6% during 2024–2026
- Friendly digital economy policies: Thailand’s BOI tax exemptions, Malaysia’s Multimedia Super Corridor, Singapore’s Smart Nation initiative
- Labor cost advantages: Compared with the Middle East (excluding energy subsidies) and Singapore, Southeast Asia’s comprehensive operating costs are markedly lower
- Chinese business networks: The Chinese business communities in Bangkok, Jakarta, and Ho Chi Minh City provide a natural cultural bridge for Middle Eastern Arab capital

A friend working in Middle Eastern family office investments told me: “Right now, what Middle Eastern UHNWIs (ultra-high-net-worth individuals) are most anxious about is not yield, but ‘where my assets sleep most safely at night.’ ”

The answer is shifting from London and Singapore to Bangkok and Jakarta.

---

## 3. Southeast Asia IDC: Three Numbers That Clarify the Market

Many ask: How big is the Southeast Asian data center market really?

A few key numbers:

| Indicator | Data |
|------|------|
| Thailand IDC Market 2025E | $1.45B–1.89B USD |
| Thailand IDC Market 2030E | $3.19B–6.29B USD |
| CAGR | 12%–28% |
| Thailand’s cost advantage vs. Singapore | 40%–55% lower |

Behind these numbers lies a more important trend: AI workloads are reshaping the business logic of Southeast Asian data centers.

The traditional IDC model is “rack rental”—charge by kilowatt-hour, customers install their own servers.

But now, a new paradigm is emerging: the Token Factory.

Jensen Huang proposed this concept in 2025. In essence, it means that a data center is no longer just a “place to put servers” but a factory producing AI inference results.

Every inference request of an LLM—input plus output tokens—is the factory’s product.

The core efficiency metrics shift from “rack occupancy rate” to “tokens per watt” and “revenue per token.”

What does this shift mean for Southeast Asia?

---

## 4. Electricity Cost Arbitrage: Southeast Asia’s Real Advantage

When it comes to data center competitiveness, electricity pricing is a core variable.

A comparison of industrial electricity rates in key Southeast Asian markets:

- Thailand: approx. $0.12/kWh
- Singapore: approx. $0.28/kWh
- Indonesia: approx. $0.06–0.08/kWh
- Vietnam: approx. $0.07–0.09/kWh

Thailand’s electricity price is not the lowest, but taken together, its arbitrage space is the most solid.

On the surface, Middle Eastern electricity is cheaper (the UAE and Saudi Arabia around $0.05–0.08/kWh), but when you do the actual math, several factors must be considered:

**First: The PUE gap.**

The Middle East has a desert climate, with summers reaching up to 50°C. The PUE of a typical air-cooled data center falls between 1.8 and 2.2—in other words, for every 1 kWh spent on computing, you spend an extra 0.8–1.2 kWh on cooling.

Thailand’s tropical climate (annual average 28–32°C) is also hot, but with natural cooling assistance, PUE can be kept around 1.5. With liquid cooling, PUE can drop to 1.2–1.3.

Doing the math, **Thailand’s effective electricity cost could actually be lower than the Middle East’s**—provided you are willing to invest in liquid cooling retrofits.

**Second: Policy stability.**

Energy subsidies in the Middle East can be adjusted at any time; Saudi Arabia cut energy subsidies in 2023. For long-term assets that require 5- to 10-year planning, this kind of policy uncertainty is lethal.

Thailand’s BOI tax exemption (8-year corporate income tax) is in black and white, and far more stable.

**Conclusion: Thailand’s real advantage is not any single metric, but a comprehensive package—moderate but stable electricity prices, a climate suitable for cooling, generous BOI incentives, and a geographic location that radiates across Southeast Asia.**

---

## 5. The Economics of a Token Factory: Is It Really Profitable?

This is the question everyone cares about most, and also the one most prone to exaggeration.

I will try to run the numbers as objectively as possible:

**Baseline assumptions:**

- GPU model: H100 SXM (80GB HBM3)
- Thailand industrial electricity price: $0.12/kWh
- PUE: 1.5 (air cooling + natural cooling)
- GPU power draw: 700W TDP

**Daily per-card economic model (70% utilization):**

Revenue side:

- H100 inference throughput (optimized): approx. 1,000–2,000 tokens/second
- Daily token processing volume: 86.4 million–173 million tokens
- Pricing per million tokens: $0.40 (GPT-4-equivalent market quote)
- **Daily revenue: approx. $2,420**

Cost side:

- GPU cloud rental cost (70% utilization): $33.7/day
- Electricity cost: $3.0/day
- Bandwidth + storage + ops amortization: approx. $5–10/day
- **Total cost: approx. $42–50/day**

**Daily net profit per card: approx. $2,370–$2,380**

**Annualized net profit per card: approx. $860,000**

Of course, this is a highly idealized model. In actual operations, utilization will not stay at 70% all the time, GPU purchase prices will fluctuate, and you also need to amortize the investment in cooling retrofits.

But this figure shows the direction: the business logic of a Token Factory is valid; the keys are scale and management.

---

## 6. Who Is Entering

A few cases from the report are worth discussing, although I have withheld specific company names.

**First case: A compute platform that started from China’s IDC industry** — it began a proactive pivot in 2019, increasing its share of AI customers and designing data centers with reserved high power density (30kW+ per rack) to support GPU cluster deployment. By 2024, its AI-related revenue share had risen from 15% to 35%.

At its core, this kind of transformation boils down to two things: planning power density ahead of time, and building relationships with AI customers ahead of time.

**Second case: A Southeast Asian hyperscale IDC operator** — backed by top-tier PE and sovereign funds, focused on hyperscale clients. Its strategy is simple: acquire land at scale, standardize design, build fast. A single data center campus can be compressed to a 12–18 month construction cycle, with customer retention rates exceeding 95%.

Long-term hyperscale customer contracts (10–15 years) are a stable cash flow source, and standardization is the foundation for rapid expansion—combine these two logics, and the effect is amplified.

**Third case: An Indonesian data center operator** — in 2025, it formed a joint venture with the country’s largest telecom operator, planning a 500 MW AI data center campus, focused on building renewable-energy-driven, high-power-density, advanced liquid-cooled facilities.

Forming a JV with the top local operator is an effective path to quickly acquire local customer resources; it is not hard to understand, but in a relationship-driven market like Southeast Asia, its value is magnified.

---

## 7. What Are the Most Realistic Risks?

I have spoken a lot about the optimistic side, but several risks must be confronted head-on:

**First: U.S. chip export controls.**

This is the single most disruptive risk to Southeast Asia’s IDC transformation.

In October 2022, the A100/H100 were added to the export control list. In October 2023, the H800 (China-specific version) and L40S were included. In 2024, even the H20 (China-specific version of the H100) was brought under control.

High-end GPU procurement channels are narrowing, procurement costs are rising, and compliance risks are increasing. For any IDC planned to deploy GPU clusters in Southeast Asia, building an internal export compliance system is a must.

**Second: Thailand’s grid expansion speed.**

AI workloads are characterized by high density and continuous demand. A 2,000-rack data center could easily require 20–30 MW of power. Whether Thailand’s current grid expansion pace can keep up with this demand is a real question.

The substation construction cycle and the PEA/MEA interconnection process are variables that must be planned for in advance.

**Third: Intensifying competition.**

When everyone sees the opportunity in Southeast Asia, the Singaporean giants are also accelerating their layouts. Global players like Equinix and STT GDC have stronger capital, more mature operational systems, and more direct interconnection agreements with major public cloud providers.

The differentiation advantage of local Thai IDCs must be built on dimensions such as cost, localized relationships, and policy utilization; otherwise, they will fall into a passive position.

---

---

## Key Takeaways

- **Middle Eastern capital is reallocating assets** : Sovereign wealth funds such as Saudi PIF, Kuwait Investment Authority, and Qatar Investment Authority are shifting assets from traditional destinations (London, Singapore) to Bangkok and Jakarta, driven by geopolitical security anxiety
- **Southeast Asia’s comprehensive advantages are underestimated** : Moderate but stable electricity prices, a tropical climate suitable for cooling (liquid-cooled PUE can reach 1.2–1.3), strong BOI policies, and a geographic location radiating across Southeast Asia—this is a “comprehensive package” advantage, not a single-category champion
- **The business logic of a Token Factory is valid** : Based on H100 at 70% utilization in Thailand, annualized net profit per card is approximately $860,000; the keys are scale management and GPU resource lock-in
- **2026–2031 is a critical window period** : Three windows (Middle Eastern capital seeking safe havens + AI compute explosion + Southeast Asia electricity cost advantage) overlap; the window is expected to last 3–5 years
- **The core risk is U.S. chip export controls** : From A100/H100 to H20/L20, the scope of controls continues to expand; any GPU cluster deployment must first prioritize establishing an export compliance system

---

## 8. My Judgment

Looking back at this report, the single most important conclusion is:

The transformation of Southeast Asian IDCs into AI compute platforms is essentially an opportunity created by the overlap of three windows—Middle Eastern capital’s safe-haven demand, the explosion of AI inference compute, and Southeast Asia’s electricity cost advantage—and this window is expected to last 3–5 years.

But between “opportunity” and “success” lies execution.

Several conditions will determine whether this transformation succeeds:

1. **Power density design** : New builds or retrofits must consider a carrying capacity of 30kW+ per rack; otherwise, they will be constrained by infrastructure in the future

2. **GPU resource lock-in** : Establishing GPU procurement channels before supply tightens is the most underrated strategic move

3. **Early establishment of customer relationships** : AI customer contracts are typically longer-term (5–7 years), helping stabilize cash flow, but trust-building needs to start 6–12 months in advance

4. **Compliance system** : The risk of export controls is real, and dedicated personnel are required

5. **Liquid cooling retrofit** : This is not optional but mandatory—the PUE gap will directly affect the competitiveness of the unit economics

---

## 9. Conclusion

After writing this, my biggest takeaway is: The story of Southeast Asian IDCs is, at its heart, a calculus of “where is it most cost-effective to deploy compute.”

The flow of capital is changing, the core of competition is changing, and the yardstick for measuring a data center’s value is changing too.

Traditional IDCs look at rack occupancy rates.

Token Factories look at tokens per watt.

This is a brand-new game; whoever understands it first gets the entry ticket first.

---

*Data sources: Mordor Intelligence, GlobeNewsWire, Arizton, Wood Mackenzie, and public market data. Some figures are industry estimates and are for directional reference only.*
