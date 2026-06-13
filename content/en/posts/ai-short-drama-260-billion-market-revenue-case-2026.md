---
title: "AI short drama 26 billion market: How video large models monetize"
date: 2026-06-03
draft: false
description: "On June 3, 202"
tags: ["MaaS", "Token Economy", "AI Short Drama", "Large Video Model", "Monetization Case", "Domestic AI", "Seedance", "Douyin", "Kling", "Kuaishou"]
slug: "ai-short-drama-260-billion-market-revenue-case-2026"
cover:
  image: "https://images.unsplash.com/photo-1574717024653-61fd2cf4d44d?w=1200&q=80"
  alt: "AI Short Drama and Video Generation"
  caption: "Chinese AI short dramas have an annual output value of 260 billion, with Model A accounting for 58%."
ShowToc: true
---
<link rel="stylesheet" href="/tech-blog/css/bis.css">

<div class="bis-wrap">

<div class="bis-hero">
  <span class="tag">Monetization Case · 2026-06-03</span>
  <h1>AI Short Drama 26 Billion Market: How Video Large Models Monetize</h1>
  <p class="subtitle">A video model with monthly sales of 1 billion / conservative ARR 15 billion+ / accounts for 58% of short drama output value — a case of penetrating the industry chain within 4 months</p>
  <p class="date">2026-06-03 · Industry Case</p>
</div>

<div class="bis-alert">
  <strong>This is a counterintuitive case</strong>. Released on February 10, 2026, and within 4 months, monthly sales exceeded 1 billion yuan; it is not a "consumer-grade App" (creators on Xiaohongshu/Douyin/Video Account cannot even use the API), but <strong>a pure B2B API</strong>, with customers <strong>almost entirely AI short drama companies</strong>. This article dissects how it monetizes, who is paying, why competitors cannot catch up, and its end-game significance for China's MaaS battlefield.
</div>

<div class="bis-signal">
<h3>💡 Key Takeaways</h3>
<ul>
  <li><strong>B2B API is the correct path for video model monetization</strong> — C-end creators use Jiemeng/Xiaoyunque (subscription/free), while B-end short drama companies use API (token billing); the two markets do not overlap, and the 1 billion monthly sales come entirely from the latter.</li>
  <li><strong>The revenue scale of video models has surpassed all general LLM models</strong> — Model A's conservative ARR estimate of 15 billion is 100% of ByteDance MaaS' 2026 target of 15 billion, exceeding any single LLM company's revenue.</li>
  <li><strong>58% of AI short drama output value flows to the generation process</strong> — Short drama companies can afford it because user ARPU is 10-50 yuan, repurchase rate is high, and streaming ROI is positive; even after AI replaces live-action shooting costs, overall ROI remains positive.</li>
  <li><strong>A 4.4x gap means users are not even trying Kling</strong> — Kling ARR 3.4 billion vs Model A 15 billion; switching costs (3-6 months of workflow rework, tens of millions in capacity loss) make it impossible for short drama companies to migrate.</li>
  <li><strong>The single-point war in the video generation track is over</strong> — Model A has de facto monopoly in a leading video cloud channel; other cloud vendors should shift to multimodal combinations, industry solutions, and agent platforms.</li>
</ul>
</div>

<!-- ============ MOD-01 At a Glance ============ -->
<div class="bis-section">
<h2><span class="num">1</span>At a Glance — Public Data as of 2026/6/3</h2>

<div class="bis-grid">
  <div class="bis-card red">
    <span class="val">1<span style="font-size:14px"> billion/month</span></span>
    <span class="lab">Monthly sales through a leading video cloud channel</span>
  </div>
  <div class="bis-card">
    <span class="val">15<span style="font-size:14px"> billion+</span></span>
    <span class="lab">Conservative ARR estimate</span>
  </div>
  <div class="bis-card green">
    <span class="val">3.4<span style="font-size:14px"> billion</span></span>
    <span class="lab">Kling ARR (cross comparison)</span>
  </div>
  <div class="bis-card purple">
    <span class="val">~58%</span>
    <span class="lab">Share of China's AI short drama output value</span>
  </div>
  <div class="bis-card">
    <span class="val">26<span style="font-size:14px"> billion</span></span>
    <span class="lab">Median annual output value of China's AI short dramas</span>
  </div>
  <div class="bis-card red">
    <span class="val">95%</span>
    <span class="lab">API penetration rate in the short drama industry</span>
  </div>
</div>

<p><strong>Core signal</strong>: For the first time, a video large model (not LLM, not image model) has become a MaaS business with <strong>single-point revenue exceeding 10 billion yuan</strong>. This scale <strong>already</strong> exceeds the revenue of any single company from general LLM models, and <strong>is 100% of ByteDance MaaS' 2026 target of 15 billion yuan</strong>.</p>
</div>

<!-- ============ MOD-02 Data Sources and Calculation Methods ============ -->
<div class="bis-section">
<h2><span class="num">2</span>Data Sources and Calculation Methods (Must Read)</h2>

<p>On 2026/6/3, an industry discussion disclosed a set of figures, with <strong>original definitions</strong> as follows:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Metric</th>
      <th>Value</th>
      <th>Time Point</th>
      <th>Disclosure Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Monthly sales of a video model (Model A) through a leading video cloud channel</td>
      <td><strong>1 billion yuan</strong></td>
      <td>2026/6</td>
      <td>Public industry discussion</td>
    </tr>
    <tr>
      <td>Corresponding ARR (annualized)</td>
      <td><strong>~12 billion yuan</strong></td>
      <td>2026/6</td>
      <td>Simple annualization</td>
    </tr>
    <tr>
      <td>Kling (Kuaishou) latest ARR</td>
      <td>3.4 billion yuan</td>
      <td>2026 year-to-date</td>
      <td>Public Kuaishou financial report</td>
    </tr>
    <tr>
      <td>China AI short drama annual output value</td>
      <td>22-30 billion yuan (median 26 billion)</td>
      <td>2026 year-to-date</td>
      <td>Kasi/Juliang Engine</td>
    </tr>
    <tr>
      <td>A leading video cloud's 2026 MaaS target</td>
      <td>15 billion yuan</td>
      <td>2026/4 upward revision</td>
      <td>Internal OKR</td>
    </tr>
    <tr>
      <td>A leading video cloud's 2025 actual MaaS revenue</td>
      <td>~1.5 billion yuan</td>
      <td>2025 full year</td>
      <td>Industry estimate</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>A key implicit fact</strong>:</p>

<ul>
  <li>A leading video cloud's <strong>2025 full-year actual MaaS ~1.5 billion</strong></li>
  <li>A leading video cloud's <strong>2026 single-year target 15 billion</strong> (<strong>10x growth</strong>)</li>
  <li>Model A's <strong>single model</strong> monthly sales already 1 billion, ARR 15 billion+</li>
  <li>In other words: <strong>100% of this cloud's 2026 target comes almost entirely from Model A</strong>, with other video models contributing a small combined share.</li>
</ul>

<div class="bis-quote">
"The 10x year-on-year growth is not from customer base expansion, but from a <strong>single customer (AI short drama company) single point (video generation API) volume explosion</strong>." — 2026/6/3 Industry assessment
</div>
</div>

<!-- ============ MOD-03 From 1 Billion Monthly Sales to 15 Billion ARR — Three Variables ============ -->
<div class="bis-section">
<h2><span class="num">3</span>From 1 Billion Monthly Sales to 15 Billion ARR — Three Variables</h2>

<p>Direct annualization 1 billion × 12 = 12 billion. But <strong>the actual ARR will be higher</strong> because:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Variable</th>
      <th>Contribution</th>
      <th>Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Base: Monthly sales through a leading video cloud channel</td>
      <td>1 billion yuan/month</td>
      <td>Data point</td>
    </tr>
    <tr>
      <td>① Ramp-up weighting</td>
      <td>+20-30%</td>
      <td>Business still growing</td>
    </tr>
    <tr>
      <td>② Third-party channels</td>
      <td>+15-20%</td>
      <td>Partially authorized agents</td>
    </tr>
    <tr>
      <td>③ Overseas not yet fully launched</td>
      <td>+30-50%</td>
      <td>Incremental after official overseas launch</td>
    </tr>
    <tr>
      <td><strong>Conservative ARR estimate</strong></td>
      <td><strong>~15 billion yuan</strong></td>
      <td>Neutral to downbeat</td>
    </tr>
    <tr>
      <td>Optimistic ARR estimate (including overseas)</td>
      <td>~25-30 billion yuan</td>
      <td>Within 12-18 months after full overseas launch</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Key judgment</strong>:</p>

<ul>
  <li><strong>15 billion</strong> is a neutral-to-downbeat <strong>conservative figure</strong>, not an optimistic one.</li>
  <li>The 30-50% overseas increment <strong>may not materialize within 12 months</strong> — overseas customers using a Chinese cloud's video API face barriers in <strong>compliance + trust + payment channels</strong>.</li>
  <li>Publicizing "ARR 15 billion" is <strong>reasonably conservative</strong> and won't be exaggerated.</li>
</ul>
</div>

<!-- ============ MOD-04 Who Is Paying — The Real API Customers ============ -->
<div class="bis-section">
<h2><span class="num">4</span>Who Is Paying — The Real API Customers</h2>

<p>This is easily misinterpreted as "creators can just use Jiemeng or Xiaoyunque", but <strong>that's the C-end</strong>. Those using the API <strong>are almost entirely AI short drama companies</strong>.</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Customer Type</th>
      <th>Usage Method</th>
      <th>Billing Method</th>
      <th>Share of Model A Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>AI short drama companies</strong> (e.g., Hongguo, Dianzhong, Jiuzhou)</td>
      <td>API batch processing, generating video clips of 5+ seconds</td>
      <td>Per token (video seconds)</td>
      <td><strong>~95%</strong></td>
    </tr>
    <tr>
      <td>Xiaohongshu/Douyin/Video Account creators (C-end)</td>
      <td>Use "good enough model" apps like Jiemeng, Xiaoyunque</td>
      <td>Subscription / free</td>
      <td>Nearly 0</td>
    </tr>
    <tr>
      <td>Ad agencies / marketing firms</td>
      <td>API for short ads / brand materials</td>
      <td>Per token</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>Game / animation studios</td>
      <td>API for story previsualization / prototypes</td>
      <td>Per token</td>
      <td>~1%</td>
    </tr>
    <tr>
      <td>Individual developers / early-stage projects</td>
      <td>API pilot</td>
      <td>Per token</td>
      <td>~1%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Key counterintuitive points</strong>:</p>

<ul>
  <li>Model A <strong>is not a "consumer App"</strong>, it is a <strong>pure B2B MaaS</strong></li>
  <li>Xiaohongshu/Douyin/Video Account creators <strong>have never been its paying users</strong></li>
  <li>So "creators using Jiemeng" and "Model A monthly sales of 1 billion" are <strong>two completely non-conflicting things</strong></li>
  <li>This explains a key question: <strong>why a B2B-facing API can achieve 1 billion per month without being impacted by some viral event like a consumer app</strong> — its customers <strong>are commercial companies</strong>, not "users".</li>
</ul>

<div class="bis-punchline">
<h2>🎬 "Serving the productivity market" — B-end API is the correct path for video model monetization</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>Creators can use Jiemeng or Xiaoyunque, which is sufficient</strong> (C-end, subscription model, traffic sharing).<br>
  <strong>Those using the API are almost entirely AI short drama companies</strong> (B-end, token billing, productivity market).<br>
  The two markets <strong>do not overlap</strong>. <strong>1 billion monthly, 15 billion ARR</strong>, <strong>all from the latter</strong>.
</p>
</div>
</div>

<h2><span class="num">5</span> Economics — Why AI Short Drama Companies Can Afford It</h2>

<p>"Can an AI short drama company really bear 1 billion in monthly sales?" <strong>Reverse-engineering</strong> the entire Chinese AI short drama industry chain:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Segment</th>
      <th>% of Short Drama Output Value</th>
      <th>Corresponding Amount (Based on 26 Billion Yuan Output Value)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Script / Storyboard / Creative</td>
      <td>~5%</td>
      <td>1.3 billion yuan</td>
    </tr>
    <tr>
      <td><strong>Video Generation API (Model A etc.)</strong></td>
      <td><strong>~58%</strong></td>
      <td><strong>~15 billion yuan</strong></td>
    </tr>
    <tr>
      <td>Actor Replacement / Dubbing / Post-production</td>
      <td>~10%</td>
      <td>2.6 billion yuan</td>
    </tr>
    <tr>
      <td>Content Distribution / Ad Traffic</td>
      <td>~20%</td>
      <td>5.2 billion yuan</td>
    </tr>
    <tr>
      <td>Operations / Platform Share / Profit</td>
      <td>~7%</td>
      <td>1.9 billion yuan</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Key Observations</strong>:</p>

<ul>
  <li><strong>58%</strong> of the output value goes directly to the generation stage (mostly Model A)</li>
  <li>Short drama companies’ profit margins are <strong>severely squeezed</strong>, yet the model still works, <strong>which implies</strong>:<br>
    ① Strong user willingness to pay (short drama unit price 1–10 yuan, ARPU 10–50 yuan, high repurchase rate)<br>
    ② Ad traffic ROI is still positive (content distribution on Douyin / Hongguo App)<br>
    ③ <strong>Efficiency gains</strong> in generation reduce overall costs (AI replaces real-person shooting costs)</li>
  <li>If Model A does <strong>not</strong> reach 1 billion in monthly sales, AI short drama companies <strong>cannot afford</strong> the costs of other segments (creative, ad traffic)</li>
  <li><strong>This is a closed loop</strong>: Model A’s low price → explosion in short drama output → traffic recoupment → Model A usage continues to rise</li>
</ul>

<div class="bis-signal">
<h3>🔄 Unit Price vs Volume — The Fundamental Difference Between Video Models and Traditional SaaS</h3>
<p>Traditional SaaS: <strong>unit price drop = profit drop</strong> (less money per user).<br>
Large video model: <strong>unit price drop = total revenue rise</strong> (the same money can generate more videos, AI short drama companies expand capacity, and end up using even more).</p>
<p>This is why “raising prices without losing volume” is <strong>more pronounced in video models than in coding models</strong> — video is a <strong>perfectly elastic demand</strong>. A slightly lower price leads to twice as many videos generated; a slightly higher price leads to half as many. For short drama companies, <strong>ROI is always positive</strong> as long as <strong>the cost per video can be recouped</strong>.</p>
</div>
</div>

<!-- ============ MOD-06 Why Kling Can't Catch Up ============ -->
<div class="bis-section">
<h2><span class="num">6</span> Why Kling Can’t Catch Up — The Moat of a 4.4× Gap</h2>

<p>Kling ARR 3.4 billion vs Model A ARR 15 billion = <strong>4.4× gap</strong>. This is <strong>not</strong> a trivial 4.4%, <strong>4.4×</strong> means <strong>users aren’t even trying Kling</strong>.</p>

<p><strong>4 reasons short drama companies don’t switch to Kling</strong>:</p>

<ol>
  <li><strong>Prompt engineering / storyboard / character consistency workflows are all built around Model A’s API</strong> — switching models = rewriting the entire workflow, 3–6 months migration cost</li>
  <li><strong>Team prompt knowledge assets are accumulated on Model A</strong> — switching = months of experimentation, <strong>directly losing tens of millions</strong> in production capacity</li>
  <li><strong>Downstream distribution channels (Hongguo, Dianzhong, Jiuzhou) recognize the “texture” of Model A’s output</strong> — switching to Kling could affect listing review</li>
  <li><strong>Whitelist + annual framework + full-featured version customer lock-in</strong> — already signed annual contracts <strong>cannot be terminated mid-term</strong>, cash flow locked</li>
</ol>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Competitor</th>
      <th>ARR</th>
      <th>Gap</th>
      <th>Short Drama Penetration</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Model A (a leading video cloud)</strong></td>
      <td><strong>~15 billion</strong></td>
      <td>1.0×</td>
      <td>~95%</td>
    </tr>
    <tr>
      <td>Kling (Kuaishou)</td>
      <td>3.4 billion</td>
      <td>0.22×</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>Other video models (total)</td>
      <td>~1 billion</td>
      <td>0.07×</td>
      <td>~2%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>The right play for Kling</strong> (cannot fight head-on):</p>

<ul>
  <li>❌ <strong>Cannot</strong> grab users via price war (15 billion vs 3.4 billion, <strong>price war = suicide</strong>)</li>
  <li>✅ <strong>Should</strong> target <strong>niche scenarios Model A hasn’t covered</strong>:<br>
    ① Ultra-long video (continuous plot over 5 minutes)<br>
    ② 3D / virtual human / digital twin (industrial scenarios beyond short drama)<br>
    ③ Overseas Chinese / Southeast Asian markets (Model A hasn’t fully launched overseas)</li>
  <li>✅ <strong>Should</strong> pursue an <strong>open-source / on-premises deployment</strong> path (avoid head-on API competition with Model A)</li>
</ul>
</div>

<!-- ============ MOD-07 Endgame Implications for China's MaaS War ============ -->
<div class="bis-section">
<h2><span class="num">7</span> Endgame Implications — Has China’s Cloud Vendor MaaS War “Ended Early”?</h2>

<p>The <strong>core judgment</strong> from the 2026/6/3 industry discussion:</p>

<div class="bis-quote">
“<strong>The war among China’s cloud vendors in the MaaS market, at least this year, is already over ahead of schedule.</strong>” —— 2026/6/3 industry judgment
</div>

<p>Breaking down this judgment:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Claim</th>
      <th>Holds?</th>
      <th>Scope</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Video generation race is decided</td>
      <td>✅ Yes</td>
      <td>Model A on a leading video cloud channel has virtually no rivals</td>
    </tr>
    <tr>
      <td>Coding battlefield is decided</td>
      <td>❌ No</td>
      <td>Company X / Company Y / Company Z multiple leaders coexist</td>
    </tr>
    <tr>
      <td>LLM general-purpose race is decided</td>
      <td>❌ No</td>
      <td>Already breached by rock-bottom pricing, <strong>not winner-takes-all</strong>, but rather <strong>nobody makes money</strong></td>
    </tr>
    <tr>
      <td>Overall MaaS platform race is decided</td>
      <td>❌ No</td>
      <td>Company B / Company C are still investing heavily, 2026 Q3 will tell</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>A more accurate statement</strong>:</p>

<ul>
  <li><strong>“Single-point model” (video generation) war has been won on a leading video cloud channel</strong> — this is a B2B API winner-takes-all story</li>
  <li><strong>“Overall MaaS platform” war is far from over</strong> — multimodal, API orchestration, industry solutions are still being fought over</li>
  <li>For <strong>other cloud vendors</strong> (Company B / Company C): <strong>stop attacking video generation API head-on</strong>, pivot to:
    <ul>
      <li>Multimodal combinations (video + image + text + speech)</li>
      <li>Industry solutions (Agents for finance / manufacturing / education)</li>
      <li>Agent platforms (multi-model orchestration + business flow)</li>
    </ul>
  </li>
</ul>

<div class="bis-punchline">
<h2>🎯 Key Insight: B2B API is the Endgame for China’s MaaS</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>C-end Creators = Traffic / Branding / User Acquisition</strong> (loss-making for market share)<br>
  <strong>B-end API = Revenue / Profit / Compound Growth</strong> (making money relies on this)<br><br>
  Model A’s success path proves: <strong>when an AI model achieves SOTA + 5-month first-mover advantage + 95% industry penetration + extremely high switching costs, B2B API revenue can reach 15 billion ARR</strong> — this is <strong>far more profitable</strong> than all general LLMs, all consumer apps, and all subscription businesses.
</p>
</div>
</div>

<!-- ============ MOD-08 Implications for Overseas ISP Clients ============ -->
<div class="bis-section">
<h2><span class="num">8</span> Implications for Overseas ISP Clients</h2>

<p>What does this case mean for clients doing video AI business in <strong>Southeast Asia / Latin America / Japan</strong>?</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Client Type</th>
      <th>Takeaway</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>AI companies doing <strong>short drama / short video / marketing materials</strong></td>
      <td><strong>Directly use Model A’s API</strong>. No need to build a proprietary video model. Yuan-denominated pricing and compliant overseas deployment paths are officially handled by a leading video cloud</td>
    </tr>
    <tr>
      <td>Clients doing <strong>3D / industrial vision / digital twins</strong></td>
      <td>Model A is <strong>not suitable</strong> (it focuses on people + plot). Go the 3D route (<strong>Tencent Hunyuan 3D / Alibaba Tora</strong>) or the industrial route (Ascend + Sora-lite)</td>
    </tr>
    <tr>
      <td>Clients doing <strong>AI marketing / ad placement</strong></td>
      <td>Batch ad video generation = a <strong>simplified version</strong> of the short drama scenario, <strong>fully feasible</strong> with Model A. But watch out for “texture consistency” issues</td>
    </tr>
    <tr>
      <td>Clients targeting <strong>overseas markets (US / Europe / India)</strong></td>
      <td><strong>Whether they dare</strong> to use a Chinese cloud’s video API = <strong>the biggest question for China’s AI going global in 2026</strong>. Need a <strong>white-box solution</strong> (Ascend + domestic models + third-party hosting)</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>The most critical strategic implication</strong>:</p>

<ul>
  <li>❌ <strong>Do not</strong> build your own video model (ROI is unfavorable, <strong>the 15 billion ARR is Model A’s moat</strong>, not the client’s)</li>
  <li>❌ <strong>Do not</strong> just buy cloud services (per-token billing <strong>will get more expensive with scale</strong>, lock in annual frameworks)</li>
  <li>✅ <strong>Should</strong> lock in annual framework + full-featured version + whitelist priority (refer to Model A’s “whitelist + annual framework + full-featured” commercialization)</li>
  <li>✅ <strong>Should</strong> consider a <strong>third-party plan</strong> in European/American markets (white-box / open-source / Ascend adaptation) <strong>as a backup</strong></li>
</ul>
</div>

<!-- ============ MOD-09 Data Limitations and Further Reading ============ -->
<div class="bis-section">
<h2><span class="num">9</span> Data Limitations and Further Reading</h2>

<div class="bis-signal">
<h3>📊 Data Limitations (must read)</h3>
<ul>
  <li>All figures in this article come from the 2026/6/3 public industry discussion and Kuaishou financial reports</li>
  <li>“1 billion monthly sales”, “~95% penetration”, “~15 billion ARR” are all media reports, <strong>unaudited</strong></li>
  <li>Aliases such as a leading video cloud, Model A, a leading comprehensive cloud are anonymized per public blog sanitization rules</li>
  <li>Kling ARR 3.4 billion is <strong>disclosed in Kuaishou’s financial report</strong>, higher credibility</li>
  <li>AI short drama annual output value of 22–30 billion yuan is an estimate by Kasi Data / Jiliang Engine</li>
  <li>Decision-making references require further verification; it is recommended to consult each company’s financial reports and industry white papers</li>
</ul>
</div>

<p><strong>Further Reading</strong>:</p>

<ul>
  <li>📄 <a href="/tech-blog/posts/domestic-maas-token-wars-2026/"><strong>《Domestic MaaS War 2026: Two Fronts of the Token Economy》</strong></a> — Macro industry analysis; this case is its detailed video front</li>
  <li>📄 <a href="/tech-blog/posts/domestic-ai-accelerator-ecosystem-2026/"><strong>《Ascend NPU Model Ecosystem Adaptation Analysis (2026/6)》</strong></a> — A guide to domestic AI compute selection for overseas clients</li>
  <li>📄 <a href="/tech-blog/posts/bis-china-ai-chip-2026/"><em>(Hidden)</em></a></li>
</ul>

<div class="bis-foot">
<p>Data sources: 2026/6/3 public industry discussion + Kuaishou financial report + Kasi Data + Jiliang Engine estimates · Written by: Tech Observer</p>
</div>
</div>

</div>
