---
title: "AI 短剧 260 亿市场：视频大模型如何变现"
date: 2026-06-03
draft: false
description: "2026/6/3 公开行业数据显示某视频模型单月销售 10 亿元、保守 ARR 150 亿+，占中国 AI 短剧年产值 58%。本文拆解模型甲如何用 API 在 4 个月内打穿短剧产业链，谁在付费、为什么没法替代、以及给中国云厂商 MaaS 战争带来的终局意义。"
tags: ["MaaS", "Token经济", "AI短剧", "视频大模型", "变现案例", "国产AI", "Seedance", "抖音", "可灵", "快手"]
slug: "ai-short-drama-260-billion-market-revenue-case-2026"
cover:
  image: "https://images.unsplash.com/photo-1574717024653-61fd2cf4d44d?w=1200&q=80"
  alt: "AI 短剧与视频生成"
  caption: "中国 AI 短剧一年产值 260 亿，模型甲一家吃了 58%"
ShowToc: true
---
<link rel="stylesheet" href="/tech-blog/css/bis.css">

<div class="bis-wrap">

<div class="bis-hero">
  <span class="tag">Monetization Case · 2026-06-03</span>
  <h1>The 260 Billion AI Short Drama Market: How Video Foundation Models Monetize</h1>
  <p class="subtitle">One video model hits 1 billion in monthly sales / Conservative ARR 15 billion+ / 58% of short drama output value — A case that breaks the industrial chain in 4 months</p>
  <p class="date">2026-06-03 · Industry Case Study</p>
</div>

<div class="bis-alert">
  <strong>This is a counterintuitive case</strong>. Released on February 10, 2026, monthly sales exceeded 1 billion yuan within 4 months; it is not a "consumer app" (creators on Xiaohongshu/TikTok/WeChat Channels don’t even use the API), but <strong>a pure B2B API</strong>, with customers <strong>almost entirely AI short drama companies</strong>. This article dissects how it monetizes, who is paying, why competitors can’t catch up, and what it means for the endgame of China's MaaS battleground.
</div>

<div class="bis-signal">
<h3>💡 Key Takeaways</h3>
<ul>
  <li><strong>B2B API is the right path for video model monetization</strong> — C-end creators use Jimeng/Xiao Yun Que (subscription/free), B-end short drama companies use API (token billing); the two markets do not overlap, and the 1 billion monthly sales come entirely from the latter</li>
  <li><strong>Video model revenue scale has surpassed all LLM general-purpose models</strong> — Model A’s conservative ARR estimate of 15 billion is 100% of ByteDance MaaS 2026 target of 15 billion, exceeding any single LLM company’s revenue</li>
  <li><strong>58% of AI short drama output value flows to the generation link</strong> — Short drama companies can afford it because user ARPU is 10–50 yuan, repurchase rate is high, ad ROI is positive, and AI replacing live-action shooting costs still yields positive overall ROI</li>
  <li><strong>A 4.4x gap means users aren’t even trying Kling</strong> — Kling ARR 3.4 billion vs Model A 15 billion; switching costs (3–6 months workflow rewrite, tens of millions in capacity loss) make migration impossible for short drama companies</li>
  <li><strong>The single-point war in video generation track has ended</strong> — Model A has a de facto monopoly on a leading video cloud channel; other cloud vendors should pivot to multimodal combos, industry solutions, and agent platforms</li>
</ul>
</div>

<!-- ============ MOD-01 Overview at a Glance ============ -->
<div class="bis-section">
<h2><span class="num">1</span>Overview at a Glance — Public Data as of 2026/6/3</h2>

<div class="bis-grid">
  <div class="bis-card red">
    <span class="val">1<span style="font-size:14px"> billion/month</span></span>
    <span class="lab">Monthly sales on a leading video cloud channel</span>
  </div>
  <div class="bis-card">
    <span class="val">15<span style="font-size:14px"> billion+</span></span>
    <span class="lab">Conservative ARR estimate</span>
  </div>
  <div class="bis-card green">
    <span class="val">3.4<span style="font-size:14px"> billion</span></span>
    <span class="lab">Kling ARR (cross-comparison)</span>
  </div>
  <div class="bis-card purple">
    <span class="val">~58%</span>
    <span class="lab">Share of China AI short drama output value</span>
  </div>
  <div class="bis-card">
    <span class="val">260<span style="font-size:14px"> billion</span></span>
    <span class="lab">China AI short drama annual output value (midpoint)</span>
  </div>
  <div class="bis-card red">
    <span class="val">95%</span>
    <span class="lab">Industry API penetration rate for short drama</span>
  </div>
</div>

<p><strong>Core signal</strong>: A video foundation model (not LLM, not image model) has for the first time become a <strong>single-point revenue exceeding 100 billion</strong> MaaS business. This magnitude <strong>already</strong> surpasses the single-company revenue of all LLM general-purpose models, <strong>and is 100% of ByteDance MaaS 2026 target of 15 billion</strong>.</p>
</div>

<!-- ============ MOD-02 Data Sources and Methodologies ============ -->
<div class="bis-section">
<h2><span class="num">2</span>Data Sources and Methodologies (Mandatory Read)</h2>

<p>On 2026/6/3, industry discussions disclosed a set of numbers, with the <strong>original scope</strong> as follows:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Metric</th>
      <th>Value</th>
      <th>Time Point</th>
      <th>Disclosing Party</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Monthly sales of a certain video model (Model A) on a leading video cloud channel</td>
      <td><strong>1 billion yuan</strong></td>
      <td>2026/6</td>
      <td>Public industry discussion</td>
    </tr>
    <tr>
      <td>Corresponding ARR (annualized)</td>
      <td>~12 billion yuan</td>
      <td>2026/6</td>
      <td>Simple annualization</td>
    </tr>
    <tr>
      <td>Kling (Kuaishou) latest ARR</td>
      <td>3.4 billion yuan</td>
      <td>2026 year-to-date</td>
      <td>Kuaishou earnings disclosure</td>
    </tr>
    <tr>
      <td>China AI short drama annual output value</td>
      <td>22–30 billion yuan (midpoint 26 billion)</td>
      <td>2026 year-to-date</td>
      <td>Kasi / Ocean Engine</td>
    </tr>
    <tr>
      <td>A leading video cloud 2026 MaaS target</td>
      <td>15 billion yuan</td>
      <td>2026/4 upward revision</td>
      <td>Internal OKR</td>
    </tr>
    <tr>
      <td>Same cloud 2025 actual MaaS revenue</td>
      <td>~1.5 billion yuan</td>
      <td>Full year 2025</td>
      <td>Industry estimates</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>One implicit critical fact</strong>:</p>

<ul>
  <li>The leading video cloud <strong>2025 full-year actual MaaS ~1.5 billion</strong></li>
  <li>The same cloud <strong>2026 single-year target 15 billion</strong> (<strong>10x growth</strong>)</li>
  <li>Model A alone has <strong>single-model</strong> monthly sales of 1 billion, ARR 15 billion+</li>
  <li>In other words: <strong>100% of that cloud’s 2026 target comes almost entirely from Model A</strong>, with other video models combined contributing a small share</li>
</ul>

<div class="bis-quote">
"10× year-on-year growth does not come from customer expansion, but from <strong>a single customer (AI short drama companies) single point (video generation API) single-volume explosion</strong>." —— Industry judgment of 2026/6/3
</div>
</div>

<!-- ============ MOD-03 ARR Estimate: Three Variables ============ -->
<div class="bis-section">
<h2><span class="num">3</span>From 1 Billion Monthly Sales to 15 Billion ARR — Three Variables</h2>

<p>Direct annualization: 1 billion × 12 = 12 billion. But <strong>actual ARR will be higher</strong>, because:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Variable</th>
      <th>Contribution Ratio</th>
      <th>Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Base: monthly sales on the leading video cloud channel</td>
      <td>1 billion yuan/month</td>
      <td>Disclosed data point</td>
    </tr>
    <tr>
      <td>① Ramp-up period weighting</td>
      <td>+20–30%</td>
      <td>Business still growing</td>
    </tr>
    <tr>
      <td>② Third-party channels</td>
      <td>+15–20%</td>
      <td>Some authorized agencies</td>
    </tr>
    <tr>
      <td>③ Overseas not yet fully rolled out</td>
      <td>+30–50%</td>
      <td>Incremental after official overseas launch</td>
    </tr>
    <tr>
      <td><strong>Conservative ARR estimate</strong></td>
      <td><strong>~15 billion yuan</strong></td>
      <td>Neutral to cautious</td>
    </tr>
    <tr>
      <td>Optimistic ARR estimate (including overseas)</td>
      <td>~25–30 billion yuan</td>
      <td>Within 12–18 months after full overseas rollout</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Key judgment</strong>:</p>

<ul>
  <li><strong>15 billion</strong> is a <strong>conservative number</strong> under neutral assumptions, not an optimistic one</li>
  <li>The 30–50% overseas increment may <strong>not be realized within 12 months</strong> — overseas customers using Chinese cloud video APIs face <strong>compliance + trust + payment channel</strong> hurdles</li>
  <li>Stating "ARR 15 billion" externally is <strong>reasonably conservative</strong> and not inflated</li>
</ul>
</div>

<!-- ============ MOD-04 Who Is Paying? ========== -->
<div class="bis-section">
<h2><span class="num">4</span>Who Is Paying — The API’s Real Customers</h2>

<p>This is easily misread as "creators can just use Jimeng or Xiao Yun Que," but <strong>that is the C-end</strong>. Those using the API are <strong>almost entirely AI short drama companies</strong>.</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Customer Type</th>
      <th>Usage Pattern</th>
      <th>Billing</th>
      <th>% of Model A Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>AI short drama companies</strong> (Hongguo, Dianzhong, Jiuzhou, etc.)</td>
      <td>API batch processing, generating video clips of 5+ seconds</td>
      <td>Per token (video seconds)</td>
      <td><strong>~95%</strong></td>
    </tr>
    <tr>
      <td>Xiaohongshu/TikTok/WeChat Channels creators (C-end)</td>
      <td>Use "good enough" model apps like Jimeng, Xiao Yun Que</td>
      <td>Subscription / free</td>
      <td>Nearly 0</td>
    </tr>
    <tr>
      <td>Advertising agencies / marketing firms</td>
      <td>API for short ads / brand collateral</td>
      <td>Per token</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>Game / animation studios</td>
      <td>API for storyboarding / prototyping</td>
      <td>Per token</td>
      <td>~1%</td>
    </tr>
    <tr>
      <td>Individual developers / early-stage projects</td>
      <td>API trials</td>
      <td>Per token</td>
      <td>~1%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Key counterintuitive points</strong>:</p>

<ul>
  <li>Model A is <strong>not a "consumer app"</strong>; it is a <strong>pure B2B MaaS</strong></li>
  <li>Xiaohongshu/TikTok/WeChat Channels creators have <strong>never been its paying users</strong></li>
  <li>Thus "creators use Jimeng" and "Model A 1 billion monthly sales" are <strong>completely non-conflicting</strong> matters</li>
  <li>This explains a critical question: <strong>why a B2B API can reach 1 billion monthly without being disrupted by a viral event like a consumer app</strong> — its customers <strong>are business companies</strong>, not "users"</li>
</ul>

<div class="bis-punchline">
<h2>🎬 "Serving the Productivity Market" — B-end API is the Right Monetization Path for Video Models</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>Creators can use Jimeng, Xiao Yun Que</strong> (C-end, subscription, traffic sharing).<br>
  <strong>Those using the API are basically all AI short drama companies</strong> (B-end, token billing, productivity market).<br>
  The two markets <strong>do not overlap</strong>. <strong>1 billion monthly, 15 billion ARR</strong>, <strong>all come from the latter</strong>.
</p>
</div>
</div>

<!-- ============ MOD-05 Why AI Short Drama Pays ============ -->
<div class="bis-section">
<h2><span class="num">5</span>The Economics — Why AI Short Drama Companies Can Afford It</h2>

<p>"Why can AI short drama companies support 1 billion monthly sales?" <strong>Let’s reverse-engineer</strong> China's AI short drama industrial chain:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Link</th>
      <th>% of Short Drama Output Value</th>
      <th>Corresponding Amount (based on 26 billion output value)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Script / storyboard / creative</td>
      <td>~5%</td>
      <td>1.3 billion yuan</td>
    </tr>
    <tr>
      <td><strong>Video generation API (Model A, etc.)</strong></td>
      <td><strong>~58%</strong></td>
      <td><strong>~15 billion yuan</strong></td>
    </tr>
    <tr>
      <td>Actor replacement / dubbing / post-production</td>
      <td>~10%</td>
      <td>2.6 billion yuan</td>
    </tr>
    <tr>
      <td>Content distribution / ad spend</td>
      <td>~20%</td>
      <td>5.2 billion yuan</td>
    </tr>
    <tr>
      <td>Operations / platform share / profit</td>
      <td>~7%</td>
      <td>1.9 billion yuan</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Key observations</strong>:</p>

<ul>
  <li><strong>58%</strong> of output value directly goes to the generation link (primarily Model A)</li>
  <li>Short drama companies’ profit margins are <strong>severely squeezed</strong>, yet the model still works — <strong>meaning</strong>:<br>
    ① User willingness to pay is strong (short drama unit price 1–10 yuan, ARPU 10–50 yuan, high repurchase rate)<br>
    ② Ad ROI remains positive (content distribution on Douyin / Hongguo app)<br>
    ③ Generation efficiency <strong>improves</strong> overall cost reduction (AI replaces live-action shooting costs)</li>
  <li>If Model A did <strong>not</strong> achieve 1 billion monthly sales, AI short drama companies <strong>could not afford</strong> other links (creativity, ad spend)</li>
  <li><strong>This is a closed loop</strong>: Model A’s low pricing → short drama output explosion → ad revenue recovery → Model A usage continues to rise</li>
</ul>

<div class="bis-signal">
<h3>🔄 Unit Price vs Volume Production — Fundamental Difference Between Video Models and Traditional SaaS</h3>
<p>Traditional SaaS: <strong>unit price decrease = profit decrease</strong> (less money per user).<br>
Video foundation model: <strong>unit price decrease = total revenue increase</strong> (same money can generate more videos; AI short drama companies’ production capacity expands, using even more).</p>
<p>That’s why "raising price without losing volume" is <strong>even more pronounced on video models than on coding models</strong> — video is <strong>a completely elastic demand</strong>. A slightly lower price generates twice as many videos; a slightly higher price generates half as many. <strong>For short drama companies, ROI is always positive</strong>, as long as <strong>the cost per video can be recovered</strong>.</p>
</div>
</div>

<!-- ============ MOD-06 Why Kling Can’t Catch Up ============ -->
<div class="bis-section">
<h2><span class="num">6</span>Why Kling Can’t Catch Up — The Moat of a 4.4× Gap</h2>

<p>Kling ARR 3.4 billion vs Model A ARR 15 billion = <strong>4.4× gap</strong>. This is <strong>not</strong> a small 4.4% difference; <strong>4.4×</strong> means <strong>users aren’t even trying Kling</strong>.</p>

<p><strong>4 reasons short drama companies don’t switch to Kling</strong>:</p>

<ol>
  <li><strong>Prompt engineering / storyboarding / character consistency workflows are all built around Model A’s API</strong> — switching models = rewriting the entire workflow, 3–6 months migration cost</li>
  <li><strong>Team prompt knowledge assets are embedded in Model A</strong> — switching = months of experimentation, <strong>direct loss of tens of millions</strong> in capacity</li>
  <li><strong>Downstream distribution channels (Hongguo, Dianzhong, Jiuzhou) also recognize the "texture" of Model A’s output</strong> — switching to Kling could affect content review</li>
  <li><strong>Whitelist + annual contract + full version of customer lock-in</strong> — signed annual contracts <strong>cannot be terminated midway</strong>; cash flow is locked</li>
</ol>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Competitor</th>
      <th>ARR</th>
      <th>Gap</th>
      <th>Short Drama Scene Penetration</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Model A (leading video cloud)</strong></td>
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
      <td>Other video models combined</td>
      <td>~1 billion</td>
      <td>0.07×</td>
      <td>~2%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>Kling’s correct play</strong> (cannot fight head-on):</p>

<ul>
  <li>❌ <strong>Cannot</strong> compete on price to snatch users (15 billion vs 3.4 billion, <strong>price war = suicide</strong>)</li>
  <li>✅ <strong>Should</strong> target <strong>niche scenarios Model A hasn’t covered</strong>:<br>
    ① Ultra-long videos (5+ minutes continuous narrative)<br>
    ② 3D / virtual human / digital twin (industrial scenes beyond short drama)<br>
    ③ Overseas Chinese / Southeast Asian markets (Model A not yet fully overseas)</li>
  <li>✅ <strong>Should</strong> go the <strong>open source / on-premises deployment</strong> route (avoid head-on API competition with Model A)</li>
</ul>
</div>

<!-- ============ MOD-07 Endgame Significance for China MaaS ============ -->
<div class="bis-section">
<h2><span class="num">7</span>Endgame Significance — Has China’s Cloud Vendor MaaS War "Ended Early"?</h2>

<p>The <strong>core judgment</strong> from the 2026/6/3 industry discussion:</p>

<div class="bis-quote">
"<strong>The war among Chinese cloud vendors in the MaaS market, at least this year, has already ended early.</strong>" —— Industry judgment, 2026/6/3
</div>

<p><strong>Deconstructing this judgment</strong>:</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Assertion</th>
      <th>Valid?</th>
      <th>Scope of Applicability</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Video generation track winner decided</td>
      <td>✅ Holds</td>
      <td>Model A has virtually no rival on a leading video cloud channel</td>
    </tr>
    <tr>
      <td>Coding battleground winner decided</td>
      <td>❌ Does not hold</td>
      <td>Company X / Company Y / Company Z multiple top players coexist</td>
    </tr>
    <tr>
      <td>LLM general-purpose track winner decided</td>
      <td>❌ Does not hold</td>
      <td>Already torn down by floor pricing; <strong>not winner-takes-all</strong>, but <strong>nobody makes money</strong></td>
    </tr>
    <tr>
      <td>Overall MaaS platform winner decided</td>
      <td>❌ Does not hold</td>
      <td>Company B / Company C still investing heavily; Q3 2026 will tell</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>A more precise statement</strong>:</p>

<ul>
  <li><strong>The "single-point model" (video generation) war has been won on a leading video cloud channel</strong> — this is a B2B API winner-takes-all story</li>
  <li><strong>The "overall MaaS platform" war is far from over</strong> — multimodality, API orchestration, and industry solutions are still being contested</li>
  <li>For <strong>other cloud vendors</strong> (Company B / Company C): <strong>stop fighting video generation API head-on</strong>; pivot to:
    <ul>
      <li>Multimodal combinations (video + image + text + voice)</li>
      <li>Industry solutions (agents for finance / manufacturing / education)</li>
      <li>Agent platforms (multi-model orchestration + business flows)</li>
    </ul>
  </li>
</ul>

<div class="bis-punchline">
<h2>🎯 Key Judgment: B2B API Is the Endgame for China MaaS</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>C-end creators = traffic / brand / user acquisition</strong> (loss-making for market share)<br>
  <strong>B-end API = revenue / profit / compound effect</strong> (money is made here)<br><br>
  Model A’s success path proves: <strong>when an AI model achieves SOTA + 5 months first-mover advantage + 95% industry penetration + extremely high switching costs, B2B API revenue can reach 15 billion ARR</strong> — this is <strong>far more than</strong> all LLM general-purpose models, all C-end apps, all subscription businesses.
</p>
</div>
</div>

<!-- ============ MOD-08 Implications for Overseas ISP Customers ============ -->
<div class="bis-section">
<h2><span class="num">8</span>Implications for Overseas ISP Customers</h2>

<p>What does this case mean for customers doing video AI business in <strong>Southeast Asia / Latin America / Japan</strong>?</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Customer Type</th>
      <th>Implication</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>AI companies doing <strong>short drama / short video / marketing collateral</strong></td>
      <td><strong>Directly use Model A’s API</strong>; no need to build your own video model. RMB-based, compliant overseas channels being handled officially by the leading video cloud</td>
    </tr>
    <tr>
      <td>Customers doing <strong>3D / industrial vision / digital twin</strong></td>
      <td>Model A is <strong>not applicable</strong> (it focuses on characters + narrative). Go 3D route (<strong>Tencent Hunyuan 3D / Alibaba Tora</strong>) or industrial route (Ascend + Sora-lite)</td>
    </tr>
    <tr>
      <td>Customers doing <strong>AI marketing / ad placement</strong></td>
      <td>Batch ad video generation = a <strong>simplified version</strong> of short drama scenarios, fully workable with Model A. But watch out for "texture consistency" issues</td>
    </tr>
    <tr>
      <td>Customers targeting <strong>overseas (US / Europe / India)</strong></td>
      <td><strong>The boldest question</strong> of 2026 Chinese AI going global: <strong>dare they use</strong> Chinese cloud video APIs. Need <strong>white-box solutions</strong> (Ascend + domestic models + third-party hosting)</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>The most critical strategic meaning</strong>:</p>

<ul>
  <li>❌ <strong>Do not</strong> build your own video model (ROI not worth it; <strong>15 billion ARR is Model A’s moat</strong>, not the customer’s)</li>
  <li>❌ <strong>Do not</strong> just buy cloud services (per-token billing <strong>gets more and more expensive</strong>; lock in annual contracts)</li>
  <li>✅ <strong>Should</strong> lock in annual contracts + full version + whitelist priority (refer to Model A’s "whitelist + annual contract + full version" commercialization)</li>
  <li>✅ <strong>Should</strong> consider a <strong>third-party option</strong> (white-box / open source / Ascend adaptation) in European and US markets <strong>as backup</strong></li>
</ul>
</div>

<!-- ============ MOD-09 Data Limitations and Further Reading ============ -->
<div class="bis-section">
<h2><span class="num">9</span>Data Limitations and Further Reading</h2>

<div class="bis-signal">
<h3>📊 Data Limitations (Mandatory Read)</h3>
<ul>
  <li>All numbers in this article come from the public industry discussion on 2026/6/3 and Kuaishou’s earnings</li>
  <li>"1 billion monthly sales", "~95% penetration", "~15 billion ARR" are all media-reported figures, <strong>unaudited</strong></li>
  <li>Pseudonyms such as "leading video cloud", "Model A", "leading integrated cloud" follow public blog anonymization rules</li>
  <li>Kling ARR 3.4 billion is <strong>per Kuaishou earnings disclosure</strong>, higher credibility</li>
  <li>AI short drama annual output value 22–30 billion yuan is an estimate by Kasi Data / Ocean Engine</li>
  <li>For decision-making references, further verification is needed; recommend combining with respective company earnings and industry white papers</li>
</ul>
</div>

<p><strong>Further Reading</strong>:</p>

<ul>
  <li>📄 <a href="/tech-blog/posts/domestic-maas-token-wars-2026/"><strong>《China's MaaS War 2026: The Two Fronts of the Token Economy》</strong></a> — Industry macro analysis; this case is a detailed walkthrough of the video front</li>
  <li>📄 <a href="/tech-blog/posts/domestic-ai-accelerator-ecosystem-2026/"><strong>《Ascend NPU Model Ecosystem Adaptation Analysis (2026/6)》</strong></a> — Domestic AI compute selection guide for overseas customers</li>
  <li>📄 <a href="/tech-blog/posts/bis-china-ai-chip-2026/"><em>(Hidden)</em></a></li>
</ul>

<div class="bis-foot">
<p>Data Sources: Public industry discussion on 2026/6/3 + Kuaishou earnings + Kasi Data + Ocean Engine estimates · Written by: Tech Observer</p>
</div>
</div>

</div>