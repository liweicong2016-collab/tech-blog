---
title: "国内 MaaS 大战 2026：Token 经济的两条战线"
date: 2026-06-02
draft: false
description: "2026 年国内 MaaS 业务深度观察：某头部视频云 2026 目标同比翻 10 倍至 150 亿元，视频模型单月收入破 10 亿；Coding 模型 Q1 涨价 83% 同时调用量增 400%。Coding 与视频模型已成赚钱主战场，LLM 通用赛道被地板价击穿。"
tags: ["MaaS", "Token经济", "国产AI", "云计算", "大模型", "推理", "GitCode", "开源大模型"]
slug: "domestic-maas-token-wars-2026"
cover:
  image: "https://images.unsplash.com/photo-1518770660439-4636190af475?w=1200&q=80"
  alt: "云计算与 Token 经济"
  caption: "Token 战场的两条主线：Coding 与视频"
ShowToc: true
---

<link rel="stylesheet" href="/tech-blog/css/bis.css">

<div class="bis-wrap">

<div class="bis-hero">
  <span class="tag">行业观察 · 2026-06</span>
  <h1>国内 MaaS 大战 2026：Token 经济的两条战线</h1>
  <p class="subtitle">某头部视频云 2026 营收目标 150 亿 / Coding 模型涨价 83% 同时调用量增 400% / LLM 通用赛道已被地板价击穿</p>
  <p class="date">2026-06-02 · 行业观察</p>
</div>

<div class="bis-alert">
⚠️ <strong>2026 年行业共识已经清晰</strong>：做出顶尖模型 = 拉高 Token 消耗 + 客户付费意愿的最好方式。LLM 通用赛道已饱和，<strong>Coding（代码模型）+ 视频模型</strong>成为两条赚钱主战场。本文基于 2026/6/3 公开行业报道还原 MaaS 业务全貌。
</div>

<div class="bis-update">
  <span class="tag">📌 6/3 数据更新</span>
  <p>公开数据显示，<strong>某视频模型（模型甲）在某头部视频云渠道月销 10 亿元</strong>，推算 ARR 150 亿+；AI 短剧年产值 220-300 亿元，模型甲一家约占 58%。详见 <a href="#mod-02-deep">2.4 章 短剧经济解剖</a> 与 <a href="#mod-06-extreme">6.2 章 水晶鞋极端案例</a>，并参考关联案例博客 <a href="/tech-blog/posts/ai-short-drama-260-billion-market-revenue-case-2026/"><strong>《AI 短剧 260 亿市场：视频大模型如何变现》</strong></a>。
  </p>
</div>

<!-- ============ MOD-01 一图速览 ============ -->
<div class="bis-section">
<h2><span class="num">1</span>一图速览 — 2026 MaaS 战场数据</h2>

<div class="bis-grid">
  <div class="bis-card">
    <span class="val">150<span style="font-size:14px">亿</span></span>
    <span class="lab">某头部视频云 2026 营收目标</span>
  </div>
  <div class="bis-card red">
    <span class="val">10×</span>
    <span class="lab">2026 目标 ÷ 2025 实际</span>
  </div>
  <div class="bis-card green">
    <span class="val">+83%</span>
    <span class="lab">Coding 模型 Q1 涨价幅度</span>
  </div>
  <div class="bis-card purple">
    <span class="val">+400%</span>
    <span class="lab">Coding 模型 Q1 调用量</span>
  </div>
  <div class="bis-card">
    <span class="val">10<span style="font-size:14px">亿+</span></span>
    <span class="lab">某视频模型单月收入</span>
  </div>
  <div class="bis-card red">
    <span class="val">~40%</span>
    <span class="lab">Token 月度增速</span>
  </div>
</div>

<p><strong>核心信号</strong>：当一家公司能把模型价格<strong>涨 83%</strong>而调用量<strong>同时增长 400%</strong>，意味着"提价不掉量"在头部 AI 模型上成立 — 这与互联网时代"先免费后涨价"的逻辑完全相反。</p>
</div>

<!-- ============ MOD-02 视频模型线 ============ -->
<div class="bis-section">
<h2><span class="num">2</span>战线一：视频模型 — 某头部视频云 150 亿目标</h2>

<p>某头部视频云 2026 年 4 月将 MaaS 业务营收目标上调至 <strong>150 亿元</strong>，几乎每月都在上调（2025 年底原目标仅 100 亿元）。</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>指标</th>
      <th>数据</th>
      <th>时点</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2025 年全年实际 MaaS 收入</td>
      <td><strong>~15 亿元</strong></td>
      <td>2025 全年</td>
    </tr>
    <tr>
      <td>2026 年 MaaS 营收目标</td>
      <td><strong>150 亿元</strong>（去年 10 倍）</td>
      <td>2026/4 上调</td>
    </tr>
    <tr>
      <td>2025 年底原目标</td>
      <td>100 亿元</td>
      <td>2025/12</td>
    </tr>
    <tr>
      <td>Token 日均消耗量月度增速</td>
      <td><strong>~40%</strong></td>
      <td>2026 截至当前</td>
    </tr>
  </tbody>
</table>
</div>

<div class="bis-signal">
<h3>🎬 某视频模型（代号：模型甲）的爆发</h3>
<ul>
  <li><strong>单月收入已超 10 亿元</strong>，仍在爬升期</li>
  <li>2026/2/10 发布 → 春节排队 10 小时 → 开启"白名单 + 年框 + 满血版"商业化</li>
  <li>全球视频模型市场份额<strong>第 2</strong>（仅次于某海外巨头）</li>
  <li>Artificial Analysis Video Arena Elo 1269，超越海外顶尖视频模型</li>
  <li>短剧行业渗透率<strong>~95%</strong>（"短剧从业者很难不是模型甲用户"）</li>
  <li>2026 目标：全球第 1</li>
</ul>
</div>

<!-- ============ MOD-02-Deep 短剧经济解剖 ============ -->
<div class="bis-section" id="mod-02-deep">
<h2><span class="num">2.5</span>短剧经济解剖 — 模型甲 10 亿月销的真正来源</h2>

<p>2026/6/3 公开行业数据显示：<strong>模型甲在某头部视频云的月销已达 10 亿元</strong>（≈ARR 120 亿）。考虑三大变量后，<strong>保守 ARR 测算 150 亿+</strong>：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>变量</th>
      <th>贡献</th>
      <th>说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>基础月销（某头部视频云渠道）</td>
      <td>10 亿元</td>
      <td>数据披露点</td>
    </tr>
    <tr>
      <td>爬升期加权</td>
      <td>+20-30%</td>
      <td>业务在涨</td>
    </tr>
    <tr>
      <td>第三方渠道</td>
      <td>+15-20%</td>
      <td>部分授权代理</td>
    </tr>
    <tr>
      <td>海外未全量</td>
      <td>+30-50%</td>
      <td>海外正式上线后增量</td>
    </tr>
    <tr>
      <td><strong>保守 ARR 测算</strong></td>
      <td><strong>~150 亿元</strong></td>
      <td>中性偏下</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>横向对比：可灵 ARR 34 亿</strong>（快手公开披露），模型甲是其 <strong>4.4 倍</strong>。差距源于：</p>

<ul>
  <li>短剧场景几乎由模型甲垄断，<strong>95% 渗透率</strong>是事实标准</li>
  <li>创作者端（小红书/抖音/视频号 C 端）由即梦、小云雀等"够用模型"覆盖，<strong>创作者根本用不到 API 计费</strong></li>
  <li>走 API 的<strong>几乎全是 AI 短剧公司</strong>——需要批量化、可控成本、5 秒以上视频片段生成</li>
</ul>

<div class="bis-punchline">
<h2>💰 中国 AI 短剧 260 亿市场，模型甲一家吃 ~58%</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>2026 年中国 AI 短剧年产值 220-300 亿元（中值 260 亿元）</strong>。模型甲 ARR 150 亿 ÷ 短剧产值 260 亿 = <strong>~58%</strong>。这意味着 AI 短剧产业链上每赚 1 元，其中 6 角是直接付给模型甲的 API Token 费。<br><br>
  <strong>剩下的 4 角</strong>：剧本/分镜/演员替换/配音/分发/投流，<strong>但生成环节</strong>已基本被模型甲<strong>事实上垄断</strong>。
</p>
</div>

<p><strong>某头部视频云的反应</strong>：</p>

<ul>
  <li><strong>2025 年底</strong> MaaS 营收目标：100 亿元</li>
  <li><strong>2026 年 4 月</strong> 上调至：<strong>150 亿元</strong>（去年 15 亿的 10 倍）</li>
  <li>2025 实际：~15 亿元 → 2026 目标 150 亿元 = <strong>10x 同比增长</strong></li>
  <li>核心驱动：模型甲 ARR 单点就占 150 亿中的 ~100%（其他视频模型合计贡献占比小）</li>
</ul>

<div class="bis-quote">
"兄弟们的判断：<strong>中国云厂商在 MaaS 市场的战争，至少在今年，是已经提前结束了</strong>。" —— 2026/6/3 行业讨论
</div>

<p><strong>对此判断的拆解</strong>：</p>

<ul>
  <li>✅ <strong>成立的部分</strong>：<strong>单点视频模型</strong>（视频生成赛道），模型甲在某头部视频云渠道事实上已无对手</li>
  <li>⚠️ <strong>不成立的部分</strong>：<strong>整体 MaaS 平台</strong>（多模态、API 编排、行业方案），公司 B/公司 C 仍在持续投入，2026 Q3 才会见分晓</li>
  <li>📊 <strong>更准确表述</strong>：<strong>"单点模型"（视频生成）的战争在某头部视频云渠道已赢；"整体 MaaS 平台"的战争远远没结束</strong></li>
</ul>
</div>

<!-- ============ MOD-03 Coding 模型线 ============ -->
<div class="bis-section">
<h2><span class="num">3</span>战线二：Coding 模型 — 某创业公司 Q1 涨价 83%</h2>

<p>2026 年 Q1，<strong>某头部 Coding 创业公司（代号：公司 X）</strong>的接口调用价格累计提升约 <strong>83%</strong>，但 API 调用量<strong>仍增长 400%</strong>。</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Coding 战场关键数据（2026 Q1）</th>
      <th>数值</th>
      <th>含义</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>接口调用价格涨幅</td>
      <td><strong>+83%</strong></td>
      <td>多次调价累计</td>
    </tr>
    <tr>
      <td>API 调用量增长</td>
      <td><strong>+400%</strong></td>
      <td>价格上涨但量没掉</td>
    </tr>
    <tr>
      <td>缓存命中 Token 价格</td>
      <td>接近海外头部模型 A</td>
      <td>国产首次核心场景价格对齐</td>
    </tr>
    <tr>
      <td>Coding 能力</td>
      <td>国内头部水平</td>
      <td>是涨价的底气</td>
    </tr>
  </tbody>
</table>
</div>

<div class="bis-punchline">
<h2>💡 "提价不掉量"在头部 AI 模型上成立</h2>
<ul>
  <li>✅ 涨价 83% 的同时，调用量增长 400%</li>
  <li>✅ 这是国产大模型首次在<strong>核心场景</strong>与海外头部厂商实现价格对齐</li>
  <li>✅ 战略选择：2024 年就押注类 Anthropic 路线（专注重模型智能 + Coding）</li>
  <li>✅ 数据来源：公司 X CEO 在 2026 Q1 财报电话会议披露</li>
</ul>
</div>
</div>

<!-- ============ MOD-04 某头部综合云 MaaS 组织升级 ============ -->
<div class="bis-section">
<h2><span class="num">4</span>某头部综合云的 MaaS 组织升级</h2>

<p>2025 年开始，某头部综合云（代号：公司 B）陆续成立<strong>数个新 MaaS 销售团队</strong>，与原直销团队合作打单。</p>

<div class="bis-signal">
<h3>🏢 销售组织三阶段进化路径</h3>
<ul>
  <li><strong>阶段一：传统云销售</strong> — 卖 CPU/存储/带宽资源</li>
  <li><strong>阶段二：MaaS 销售</strong> — 卖 Token / 模型 API（公司 B 当前所在阶段）</li>
  <li><strong>阶段三：Agent 销售</strong> — 卖业务能力 / 卖场景解决方案（未来方向）</li>
</ul>
</div>

<p><strong>MaaS 销售团队核心任务</strong>：</p>
<ul>
  <li>挖掘企业使用场景</li>
  <li>推动企业客户把 Agent 能力使用起来</li>
  <li><strong>增加 Token 消耗</strong>（这是 KPI）</li>
</ul>
</div>

<!-- ============ MOD-05 竞争格局 ============ -->
<div class="bis-section">
<h2><span class="num">5</span>竞争格局 — 三类玩家在 Coding 战场厮杀</h2>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>阵营</th>
      <th>代表玩家（脱敏）</th>
      <th>2026 动作</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><span class="bis-tag-r">大厂云服务</span></td>
      <td>公司 A（视频云）、公司 B（综合云）、公司 C（综合云）</td>
      <td>推出 Coding Plan，加大销售</td>
    </tr>
    <tr>
      <td><span class="bis-tag-m">AI 创业公司</span></td>
      <td>公司 X（Coding 头部）、公司 Y、公司 Z</td>
      <td>Coding Plan + 模型迭代</td>
    </tr>
    <tr>
      <td><span class="bis-tag-n">运营商阵营</span></td>
      <td>未点名</td>
      <td>陆续推出 Coding Plan</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>共同打法</strong>：先用相对低价格吸引用户进入生意范围 → 大量消耗 Token → 后期提价。</p>

<div class="bis-quote">
"Token 大战，如今已经清晰地划分为两条战线：一条是 Coding（代码）模型，另一条则是视频模型。相比拥挤的 LLM 模型赛道里各家公司已经把模型打到地板价，头部的 Coding 和视频模型依然拥有一定的议价权，尤其是视频模型。" —— 2026 行业共识
</div>
</div>

<!-- ============ MOD-06 灰姑娘水晶鞋效应 ============ -->
<div class="bis-section">
<h2><span class="num">6</span>理论："灰姑娘水晶鞋效应"</h2>

<p>2025 年底，海外 API 服务商 OpenRouter 提出一个理论：</p>

<div class="bis-punchline">
<h2>👠 灰姑娘水晶鞋效应</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
<strong>AI 模型发布第一个月进来的用户，比后来用户留存率更高</strong>。因为当用户用到效果好的模型，就会像灰姑娘穿上水晶鞋一样，产生<strong>极高忠诚度</strong>，并且把业务<strong>深度绑定</strong>在这个模型上。
</p>
</div>

<p><strong>战略含义</strong>：</p>
<ul>
  <li>先发优势 + 早期用户 = 长期护城河</li>
  <li>解释了为什么大厂敢"先低价圈用户"</li>
  <li>解释了为什么 Coding 模型能涨价不掉量（用户已被绑定）</li>
  <li>解释了为什么某视频模型 95% 渗透短剧行业后形成事实标准</li>
</ul>

<!-- ============ MOD-06-Extreme 水晶鞋极端案例 ============ -->
<div class="bis-signal" id="mod-06-extreme">
<h3>👠 6.1 水晶鞋的极端案例 — 模型甲的 150 亿 ARR 经济学</h3>
<p>水晶鞋效应在模型甲身上达到了<strong>极端形态</strong>——已经不是"用户黏性高"，而是"用户<strong>根本没得选</strong>"：</p>

<ul>
  <li><strong>短剧 API 调用 95% 由模型甲承担</strong>（"短剧从业者很难不是模型甲用户"）</li>
  <li>对手可灵 ARR 34 亿 = 模型甲的 0.22 倍，<strong>差距已是 4.4 倍</strong>，不是 4.4%</li>
  <li>短剧公司切换模型的边际成本极高：
    <ul>
      <li>Prompt 工程 / 分镜 / 角色一致性的工作流都是按模型甲的接口重新做的</li>
      <li>团队的 prompt 知识资产沉淀在模型甲上</li>
      <li>下游分销渠道（红果、点众、九州）的内容也认模型甲出品的"质感"</li>
    </ul>
  </li>
  <li>因此<strong>模型甲不是单纯"涨价不掉量"</strong>，而是"涨价<strong>没法</strong>被替代"</li>
</ul>

<p><strong>对比 Coding 模型</strong>（涨价不掉量）：</p>

<ul>
  <li>Coding 模型有<strong>多家头部</strong>（公司 X + 公司 Y + 创业公司 Z），用户能切换</li>
  <li>模型甲在视频生成赛道<strong>几乎一家独大</strong>，用户<strong>切换成本</strong>远超 Coding</li>
  <li>结论：<strong>视频模型的护城河比 Coding 更深</strong>，单点战争的结束时间更早</li>
</ul>

<p><strong>给竞争者（可灵）的启示</strong>：</p>

<ul>
  <li>❌ <strong>不能</strong>用价格战抢用户（模型甲 ARR 150 亿 vs 可灵 34 亿，<strong>价格战=自杀</strong>）</li>
  <li>✅ <strong>应该</strong>切<strong>模型甲没覆盖的细分场景</strong>：
    <ul>
      <li>超长视频（5 分钟以上连续剧情）</li>
      <li>3D / 虚拟人 / 数字孪生（短剧外的工业场景）</li>
      <li>海外华人 / 东南亚市场（模型甲海外未全量）</li>
    </ul>
  </li>
  <li>✅ <strong>应该</strong>走<strong>开源 / 本地部署</strong>路线（避开与模型甲的正面 API 竞争）</li>
</ul>
</div>
</div>

<!-- ============ MOD-07 一句话总结 + 数据局限 ============ -->
<div class="bis-section">
<h2><span class="num">7</span>结论与数据局限</h2>

<div class="bis-punchline">
<h2>🎯 一句话总结（v2 修订）</h2>
<p style="font-size:16px;line-height:1.7;margin:0">
  <strong>2026 年 MaaS 战场已分裂为 Coding + 视频两条线</strong>，头部公司能涨价 83% 同时调用量增 400%，说明头部 AI 模型已具备<strong>"提价不掉量"</strong>的护城河；视频模型依靠 95% 行业渗透形成事实标准，<strong>ARR 150 亿</strong>，某头部视频云 MaaS 目标上调至 150 亿；<strong>LLM 通用赛道已被地板价击穿</strong>，未来属于顶尖模型 + 行业渗透。<br><br>
  <strong>关键修订</strong>：在视频生成赛道，<strong>单点战争的胜负已分</strong>，模型甲在某头部视频云渠道事实上已无对手；但在<strong>整体 MaaS 平台</strong>（多模态 / API 编排 / 行业方案）层面，公司 B/公司 C 仍在持续投入，<strong>真正的平台战争 2026 Q3 才会见分晓</strong>。
</p>
</div>

<div class="bis-signal">
<h3>📊 数据局限（必读）</h3>
<ul>
  <li>本文数字均来自 2026/6/3 公开行业报道，未做交叉验证</li>
  <li>各家 MaaS 营收口径定义可能不同（各头部云 + 各 Coding 模型公司各自解释）</li>
  <li>"单月超 10 亿"、"~95% 渗透"等数据为媒体报道，未审计</li>
  <li>决策引用需进一步核实，建议结合各家财报与行业白皮书</li>
  <li>公司名按公开博客脱敏规则隐去，仅保留模型代号称谓与数字</li>
</ul>
</div>

<div class="bis-foot">
<p>数据来源：2026/6/3 行业媒体公开报道 · 撰写：Tech Observer</p>
</div>

</div>
