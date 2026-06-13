---
title: "In-depth study on China's Token commercial closed-loop: 5 mechanisms that still operate at 1/10 price"
date: 2026-06-11
draft: false
description: "Is China’s token business loop viable? Is the MaaS sales paradigm worth learning? Why can China’s API prices be 1/10 of overseas levels yet continue to operate? Breaking down 5 underlying mechanisms + single token cost structure + loop viability criteria + ratings of 9 companies."
tags: ["Token Economy", "MaaS", "Business closed loop", "Domestic AI", "inference cost", "Large Model", "cloud computing", "virtuous cycle"]
slug: "china-token-business-closed-loop"
cover:
  image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=1200&q=80"
  alt: "Token Factory and Closed-Loop Business"
  caption: "Token 1/10 不是补贴战，是结构性低成本 + 量价齐升的双轮驱动"
ShowToc: true
---
![Token Factory](https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=1200&q=80)
*Closed loop is more important than ARR. The ability to sustain operations at 1/10 the price precisely proves that China's MaaS has completed its journey from 0 to 1*

---

## Conclusion in One Sentence

> **China's Token business closed loop partially holds — single-point leader models (video / Coding) have already closed the loop, while general LLMs are semi-closed. The MaaS sales paradigm can be emulated in form, but its spirit is unlearnable. Operating at 1/10 price relies on 5 mechanisms (long context tax / output inflation / scheduling discounts / budget internalization / compliance premium) + 3 Chinese characteristics (domestic GPUs / electricity subsidies / open-source flywheel).**

---

## 1. First, Clarify 3 Questions

This article does not repeat [Domestic MaaS Wars](/tech-blog/posts/domestic-maas-token-wars-2026/) (already covered "two fronts") or [China Token Going Global](/tech-blog/posts/china-token-going-global-2026/) (already covered "OpenRouter 61% share"). **This time we only answer 3 new questions:**

1. **Business Closed Loop** — Can token revenue cover computing power + R&D + sales costs? Which companies have succeeded?
2. **Positive Cycle** — Once the closed loop works, can the business self-reinforce (better models → more customers → data feedback → better models)?
3. **Operating at 1/10 Price** — China's API prices have long been 10x lower than overseas, yet the market hasn't collapsed. What are the 5 underlying mechanisms?

---

## 2. Closed Loop / Positive Cycle Hard Calculations

### 2.1 Single Token Cost Structure (Inference Side, Back-calculated as of 2026-06)

Back-calculated based on mainstream Chinese GPU servers + electricity costs:

| Cost Item | Value | Notes |
|---|---|---|
| GPU server procurement | ¥350,000/unit | 8-card H100 / 8-card H200 / 8-card domestic A-card |
| Server depreciation | 3-year straight-line | ¥9,720/month |
| Electricity cost | ¥0.65/kWh (incl. tax/subsidy) | Shanghai/Beijing/Shenzhen IDC |
| Full load power per unit | 5.6 kW | 8 cards + CPU + cooling |
| Monthly electricity per unit | ¥2,624 | |
| O&M + rack space | ¥3,000/unit/month | |
| Bandwidth + storage | ¥1,500/unit/month | |
| Personnel allocation | ¥4,000/unit/month | |
| **Total monthly cost per unit** | **¥20,844** | |
| Monthly inference token capacity per unit | 50B tokens | assuming 30% utilization |
| **Marginal cost per token** | **¥0.42 / million tokens** | |

**Comparison**:
- Overseas H100 inference cost approx **$0.60 / million tokens** (≈ ¥4.3)
- China inference cost = 10% of overseas, consistent with the "1/10 price" market phenomenon
- After domestic GPU substitution = 7% of overseas

### 2.2 Pricing vs. Cost: Gross Margin Distribution

| Model | Composite ASP (¥/million) | Marginal Cost (¥/million) | **Gross Margin** |
|---|---|---|---|
| Domestic open-source 7B (open-source leader R level) | 1.5 | 0.42 | **72%** |
| Domestic open-source 70B (Model B level) | 5.0 | 1.5 | **70%** |
| Model C (Coding leader) | 20 | 1.5 | **93%** ⭐ |
| Model A (video) | 500/second (video charged by second) | 50/second | **90%** |
| Overseas leader model A (overseas) | 60 | 30 | **50%** |
| GPT-4o (overseas) | 40 | 25 | **38%** |

**Key findings**:
- **Domestic general LLM**: gross margin ~70%, **already covering costs**
- **Domestic Coding leader**: gross margin 93%, **ultimate positive cycle**
- **Video model**: per-second billing, entirely different volume, yet gross margin still 90%
- **Overseas mainstream**: thinner gross margins (38-50%) due to 10x higher computing costs

### 2.3 Criteria for Closed Loop / Positive Cycle

**Three necessary conditions** (must be met simultaneously):

✅ **Condition 1**: The model is a leader (top 3) in a specific vertical scenario
✅ **Condition 2**: Customer business is deeply sticky (switching cost > benefit of switching)
✅ **Condition 3**: Token revenue > computing + R&D + sales costs (gross margin > 30% and ARR growth > 50%)

### 2.4 Ratings for 9 Companies (2026-06)

| Company / Product | Condition 1 | Condition 2 | Condition 3 | **Closed-loop Rating** |
|---|---|---|---|---|
| Leading video cloud A / Model A | ✅ #1 in short dramas | ✅ 95% short-drama users | ✅ >1B monthly, ARR target 15B | ⭐⭐⭐⭐⭐ |
| Leading Coding startup X / Model C | ✅ Coding leader | ✅ Code as product | ✅ 83% price hike + 400% volume increase | ⭐⭐⭐⭐⭐ |
| Leading comprehensive cloud B / Model B | ✅ Open-source #2 | ⚠️ Open-source, migratable | ⚠️ Fierce price war | ⭐⭐⭐⭐ |
| Domestic open-source leader R | ✅ Open-source #1 | ❌ Completely open-source free | ⚠️ Overseas closed loop / domestic semi-closed | ⭐⭐⭐⭐ |
| Leading comprehensive cloud C / Model D | ⚠️ WeChat ecosystem | ✅ Own fish pond | ⚠️ Limited scale | ⭐⭐⭐ |
| AI startup Z | ⚠️ Multimodal differentiator | ⚠️ Open-source + commercial | ⚠️ Video profitable separately | ⭐⭐⭐ |
| AI startup Y | ⚠️ Long-context leader | ⚠️ Many individual users | ❌ 2024 burn-rate mode | ⭐⭐ |
| Leading comprehensive cloud E / Model E | ❌ Generic track, no differentiation | ❌ Primarily internal use | ❌ Limited external revenue | ⭐⭐ |
| AI startup W | ⚠️ Some scenarios | ⚠️ Generic track | ❌ Slim margins | ⭐ |

**Conclusions**:
- **Closed loop achieved**: Single-point leader models (video / Coding)
- **Semi-closed loop**: General LLM leaders (relying on group subsidies or open-source flywheel)
- **Not closed**: Long-tail general LLMs + traffic-driven AI companies

**Does the positive cycle hold?**

- **Holds**: Better models → more customers → data feedback → even better models (video / Coding leaders)
- **Partially holds**: Open-source flywheel (leader R / Model B) — global inference feedback educates domestic users as well
- **Does not hold**: Capital-burning, user-acquisition AI companies — no stickiness, no model differentiation, exit is a matter of time

---

## 3. Is the MaaS Sales Paradigm Worth Learning?

### 3.1 The Core of China's MaaS Sales Paradigm

The MaaS sales paradigm upgrade pushed by a leading comprehensive cloud B in 2025–2026:

```
Traditional cloud sales (sell resources) 
    ↓ transformation
MaaS sales (sell Tokens) 
    ↓ advancement
Agent sales (sell capability / sell scenario / sell outcome)
```

**Core actions**:
1. Establish several new MaaS sales teams, cooperate with existing direct sales to win deals
2. **Core KPI**: uncover use cases + drive enterprises to use Agents + increase Token consumption
3. **Supporting products**: industry Agent templates (e-commerce customer service / financial risk control / government Q&A / industrial documents)
4. **Pricing model**: annual framework + Token packages + outcome-based sharing (tied to GMV / saved labor hours)

A variant from a leading video cloud A (more aggressive):
- Model A (video) directly uses **whitelist + annual framework** mode
- During Spring Festival peak, queues of 10 hours → forcibly select "highest bid + deepest business" customers
- "Full-blood version" steady supply → prioritize GPU resources for annual framework customers

### 3.2 Comparison with the American AI Sales Paradigm

| Dimension | China MaaS Sales | American AI Sales (OpenAI / Anthropic) |
|---|---|---|
| **Core KPI** | Scenarios + Token consumption + business outcomes | MAU + ARR + retention |
| **Customer segmentation** | Industry key accounts (finance / government / manufacturing) | Developers + enterprise PM + IT procurement |
| **Go-to-market path** | Sales-driven + senior BD | Product-led + self-serve docs + sales assist |
| **Pricing model** | Annual frame + Token packages + outcome sharing | Pay-per-use + Enterprise contracts + tier pricing |
| **Moat** | In-group scenario fish pond | Model capability + toolchain ecosystem |

### 3.3 Deconstructing "Form vs. Spirit"

**Learnable form** (sales organization / processes / tools):
- ✅ Set up dedicated MaaS sales teams, cooperate with existing direct sales
- ✅ KPI design: number of scenarios + Token consumption + business outcomes
- ✅ Library of industry Agent templates
- ✅ Annual framework + Token packages + outcome-sharing pricing
- ✅ Companion whitepapers + ROI calculation tools

**Unlearnable spirit** (foundational advantages):
- ❌ **In-group scenario fish pond** — Leading video cloud A has Douyin short dramas (annual 22–30B RMB); leading comprehensive cloud B has Taobao customer service (millions of merchants); leading comprehensive cloud C has official accounts. Overseas giants lack this "own fish pond"
- ❌ **In-group GPU / electricity scheduling** — Video cloud A / comprehensive cloud B / comprehensive cloud C can discount "their own idle GPU periods" for MaaS business
- ❌ **Domestic GPU substitution** — The "good enough" standard for domestic A-cards allows Chinese giants to retain inference capability even with H100/H200 banned
- ❌ **Data compliance advantage** — Large domestic customers (finance / government / SOEs) naturally choose domestic clouds

### 3.4 Who Should Learn What

| Company Type | Worth learning | Unlearnable |
|---|---|---|
| **Cloud vendors with industrial scenarios** | Full paradigm (form + adjust KPIs) | Own fish pond needs time to build |
| **Pure AI startups** | Form learnable (sales org / pricing model) | Fish pond / compute / data compliance unlearnable |
| **Traditional industry ISV / SI** | Learn MaaS sales KPI system | Lack self-developed models / compute |
| **Overseas giants** | Learn "annual frame + Token packages" pricing | Chinese giants' "in-group fish-pond" unlearnable |

---

## 4. Five Mechanisms for Operating at 1/10 Price

This is the most hardcore section of the article. **China's API prices have long been 10x lower than overseas, yet the market hasn’t collapsed. This isn’t due to subsidies; it’s 5 underlying mechanisms simultaneously driving volume, plus 3 Chinese characteristics superimposed.**

### Mechanism 1: Long Context Tax

**Phenomenon**: In 2025–2026, mainstream model context windows jumped from 8K to 128K / 1M / 10M.

- A single RAG request stuffs 500K–1M characters of context
- Tokens per API call rise from ~1K to ~500K (**500x**)
- Customers perceive "prices unchanged" (per-unit API price dropped 5–10x), but **actual spending per call** rises 50x

**Data**:
- 2024 average API call: ~2K tokens
- 2026 average API call: ~150K tokens
- Token unit price down 90%, but **amount per call up 75x** → customer total bills actually increase 7.5x

**Who benefits**: model vendors (more revenue per call) + downstream apps (better user experience) → win-win

### Mechanism 2: Output Inflation

**Phenomenon**: Models tend toward “safe, verbose output.” A sentence that could be 50 words becomes 500 words from AI.

- Early GPT-4: average output 200 tokens/request
- 2026 Q1 mainstream models: average output 800 tokens/request
- **Output tokens up 4x** (even with unchanged input)

**Economic implication**:
- Output token price usually 3–5x that of input (especially Coding / video generation)
- Customers pay more for “output tokens” → vendor revenue grows
- But actual GPU computation does not grow 4x (cache / speculative decoding / quantization) → marginal cost growth far slower than revenue growth

**For vendors**: gross margin expands

### Mechanism 3: Scheduling Discounts

**Phenomenon**: Marginal cost per token continuously declines through 4 technical means:

| Technique | Cost reduction per token |
|---|---|
| Caching | Cache hit → 90% reduction |
| Quantization | FP16 → INT8 / INT4 → 50-75% reduction |
| MoE architecture | Activated parameters compressed to 3–5% → cliff drop |
| Speculative decoding | Inference time down 30–50% |

**Data** (from open-source leader R's public technical report):
- Single token inference cost 2024 Q4: $0.0014
- Single token inference cost 2026 Q1: $0.0002 (**down 86%**)
- API selling price 2024 Q4: $0.27/million
- API selling price 2026 Q1: $0.014/million (**down 95%**)
- **Selling price drops faster than cost → gross margin actually expands**

### Mechanism 4: Budget Internalization

**Phenomenon**: AI spending shifts from “R&D project expense” to “operational recurring expense.”

- 2024: CFO perspective = “this is R&D’s new toy”
- 2026: CFO perspective = “this is electricity bill + SaaS subscription + cloud resources”

**Implications for vendors**:
- Internal approval paths shorten (IT department gains more decision power)
- Renewal rates improve (60–80% industry baseline)
- ARPU rises (CFO proactively raises budget caps)

**Data**:
- 2024 median enterprise AI budget: $50K/year
- 2026 median enterprise AI budget: $500K/year (**up 10x**)
- Main driver: pilot → scale → fixed expenditure triple jump

### Mechanism 5: Compliance Premium

**Phenomenon**: Auditable / source-tracked / privately deployed tokens still command a 30–100% premium.

- Financial industry: audit token price **1.3–2.0x** standard
- Government customers: private deployment token price **1.5–3.0x** standard
- Healthcare / legal: traceable token price **1.2–1.5x** standard

**Implications for vendors**:
- Standard API price war is fierce (gross margin 30–50%)
- Compliance / private / industry-customized tokens remain high-margin (gross margin 60–80%)
- **The core profit source of MaaS sales** is the compliance premium, not the standard API

### Three Chinese Characteristics Superimposed

| Chinese characteristic | Savings / markup | Mechanism |
|---|---|---|
| **Domestic GPU substitution** | Inference cost down 30–50% | Domestic A-card price only 50–70% of H100, TDP similar |
| **Electricity subsidies** | Inference cost down 15–25% | Inner Mongolia / Guizhou / Ningxia IDC electricity at 0.3–0.4 yuan/kWh, 30–50% lower than coastal regions |
| **Open-source ecosystem flywheel** | ARR amortizes domestic fixed costs | Leader R / Model B capture 50%+ share on OpenRouter → overseas inference feedback → domestic idle compute periods filled → domestic ASP drops but total gross profit rises |

**Net effect**:
- China inference cost = 10–15% of overseas (structural)
- China API selling price = 10–15% of overseas (following)
- **Gross margin per token matches or exceeds overseas** (structural cost low + strong compliance premium)

---

## 5. Three Unique Tactics of Chinese MaaS

### Tactic 1: Scenario Fish Pond → Token Harvesting

**Leading video cloud A path**:
1. Douyin short drama business validates → proves Model A capability
2. Model A penetration reaches 95% in the short drama industry
3. Short drama industry annual output 22–30B RMB → company captures 58% = **12.7–17.4B**
4. Model A opened externally (whitelist + annual framework) → external ARR 3–5B
5. **Single-point model ARR 15B+** (2026 target)

**Leading comprehensive cloud B path**:
1. Taobao/1688 merchant customer service scenarios → validate Model B capability
2. Model B open-sourced → spontaneous adoption by developers worldwide
3. On OpenRouter, Model B captures 19% share → overseas inference feedback
4. Alibaba Cloud MaaS platform sells to enterprises → domestic enterprise ARR
5. **MaaS business quarterly revenue ~3B** (estimated from quarterly AI revenue × 30%)

### Tactic 2: Open-Source Flywheel → Global Inference Amortizes Domestic Costs

**Open-source leader R path**:
1. V2/V3 all released under MIT license
2. Price set extremely low ($0.014/million cache hit)
3. Captured 28% share on OpenRouter → global developer adoption
4. Overseas inference volume → domestic GPU utilization rises
5. **While domestic pricing is low, global inference covers the fixed costs of training + inference + R&D**

### Tactic 3: Compliance / Private Deployment / Industry Agent → High-Margin Premium

**Financial industry** (anonymized case):
- A leading city commercial bank × Leading Coding startup X: private deployment + audit tokens
- Contract value 80 million / 3 years
- Per-token price 3x the standard API
- **Gross margin 85%+**

**Government customer** (anonymized case):
- A provincial government cloud × Leading comprehensive cloud B: industry Agent templates (government Q&A / document review / data analysis)
- Contract value 120 million / 3 years
- Includes compute + model + implementation + O&M bundled
- **Gross margin 70%+**

**Manufacturing** (anonymized case):
- An automotive group × Leading video cloud A: Model A + digital human + short video generation
- Contract value 50 million / 1 year
- Used for dealer training videos / marketing assets / customer support
- **Gross margin 80%+**

---

## 6. Counterpoints / Risk Factors

### 6.1 Three Hidden Concerns About Operating at 1/10 Price

**Concern 1: How long can the subsidy war last?**
- Current Chinese API prices = cost + thin profit (not a true market-clearing price)
- If the industry consolidates (2–3 oligopolies remain), prices may rebound 5–10x
- **Analog**: China cloud market price war 2018–2020 → 30–50% price increases 2021–2022

**Concern 2: Can the open-source flywheel persist?**
- Leader R / Model B currently combine "love for the community + national strategic support"
- If policy support weakens or team commercializes under pressure → open-source licenses may tighten
- **Analog**: Red Hat / MongoDB / Elastic all followed the path "open-source → commercial tightening"

**Concern 3: Sustainability of the compliance premium**
- The current 30–100% premium for compliance/private deployment is based on "domestic substitution + data security" policies
- If overseas models regain access to China → compliance premium will be squeezed

### 6.2 Three Fragile Points of the Closed Loop

**Fragile Point 1: Window period for single-point models**
- Model A's current short-drama penetration 95% → industry saturation
- Overseas video model Gen 3 catching up → How long can ByteDance's moat last?
- **Assessment**: video model window 18–24 months, must continue investing in next-gen models

**Fragile Point 2: Homogenization of Coding models**
- Model C currently the Coding leader, but overseas models + Cursor/Devin are competing
- Once overseas models regain access, the Coding lead may rotate
- **Assessment**: Coding window 12–18 months, must bind developer ecosystem

**Fragile Point 3: The price war quagmire for general LLMs**
- Domestic open-source 7B/70B prices already fallen to 0.5–2 yuan/million tokens
- Little room for further price cuts (already near marginal cost)
- **Assessment**: General LLM track will consolidate to 3–5 oligopolies within 2 years, price war ending

---

## 7. Conclusion: Conditions Under Which a Business Closed Loop Holds

### 7.1 Four Conditions for a Valid Closed Loop (all must be met simultaneously)

✅ **Condition 1**: The model is a leader (top 3) in a specific vertical scenario
✅ **Condition 2**: Customer business is deeply sticky (switching cost > benefit of switching)
✅ **Condition 3**: Token revenue > compute + R&D + sales costs (gross margin > 30%)
✅ **Condition 4**: Possess "own fish pond" or "open-source flywheel" or "compliance premium" (at least one)

### 7.2 Business Model Benchmark: Overseas vs. China

| Dimension | Overseas (OpenAI / Anthropic) | China (Leading video cloud A / Coding leader X / Comprehensive cloud B) |
|---|---|---|
| **Core scenarios** | Developers + individual Pro | In-group scenarios + industry key accounts |
| **Closed-loop path** | Model capability + toolchain + ecosystem | In-group fish pond + open-source flywheel + compliance premium |
| **Moat** | Model quality + toolchain | Own scenarios + data compliance + localization |
| **Gross margin** | 38–50% | 70–93% (leaders) / 30–50% (generic) |
| **Price war attitude** | Cautious, avoid undermining global pricing | Aggressive, penetrate domestic market first |
| **Sustainability** | High (CFO acceptance strong) | Medium (dependent on policy + open-source ecosystem) |

### 7.3 Judgments for Readers

**For Chinese MaaS players**:
- The general LLM track will consolidate within 18 months
- Vertical scenarios (video / Coding / short dramas / industry Agents) are the real profit battleground for 2026–2028
- "Own fish pond" is the ultimate moat; the path of in-group scenario fish pond → Token harvesting is worth fully learning

**For customers / investors**:
- "Price hikes without volume loss" holds for leader AI models (validated by Coding leader X)
- The 1/10 price can sustain for 2–3 more years, then will rebound 5–10x (industry consolidation)
- Open-source flywheel = global inference amortizes domestic costs; **Leader R / Model B are structural winners**

**For overseas readers**:
- China's MaaS sales paradigm is "form learnable, spirit unlearnable"
- The real moat is the in-group scenario fish pond — a unique asset of Chinese internet giants
- Overseas can learn “annual framework + Token packages + outcome-sharing” pricing, but not the "own fish pond"

---

## Data Sources

- Public account "Intelligent Insights" report 2026/6/3 (core data source for domestic MaaS business)
- Leading comprehensive cloud B FY2026 Q3 financial report: AI revenue 89.71 billion / quarter
- Morgan Stanley AI computing report: unit token economics
- J.P. Morgan token economy report: enterprise AI budget triple jump
- Anthropic 2026 Q1 earnings call: ARR growth curve
- Domestic open-source leader R public technical reports: MoE architecture + inference cost
- OpenRouter public data: 2026-02 market share
- NVIDIA H100 / H200 / Blackwell public datasheet: GPU cost estimates
- IDC industry reports: GPU pricing + electricity costs in China cloud market
- Leading Coding startup X CEO earnings call: Model C price hike + call volume data
- National Development and Reform Commission 2025 data center electricity pricing policy

**Data as of**: 2026-06-12. Some figures are back-calculated estimates; actual data may vary by 10–20% due to customer mix / discount rates.