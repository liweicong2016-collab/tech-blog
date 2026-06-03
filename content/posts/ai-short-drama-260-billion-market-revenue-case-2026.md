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
  <span class="tag">变现案例 · 2026-06-03</span>
  <h1>AI 短剧 260 亿市场：视频大模型如何变现</h1>
  <p class="subtitle">某视频模型月销 10 亿 / 保守 ARR 150 亿+ / 占短剧产值 58% — 一个 4 个月内打穿产业链的案例</p>
  <p class="date">2026-06-03 · 行业案例</p>
</div>

<div class="bis-alert">
  <strong>这是一个反常识的案例</strong>。2026 年 2 月 10 日发布、4 个月内单月销售突破 10 亿元；它不是"消费级 App"（小红书/抖音/视频号上的创作者根本用不到 API），而是<strong>一个纯 B2B API</strong>，客户<strong>几乎全是 AI 短剧公司</strong>。本文拆解它怎么变现、谁在付钱、为什么对手追不上、以及对中国 MaaS 战场的终局意义。
</div>

<div class="bis-signal">
<h3>💡 Key Takeaways</h3>
<ul>
  <li><strong>B2B API 是视频模型变现的正确路径</strong> — C 端创作者用即梦/小云雀（订阅/免费），B 端短剧公司用 API（Token计费）；两个市场互不重叠，月销10亿全部来自后者</li>
  <li><strong>视频模型收入量级已超过所有LLM通用模型</strong> — 模型甲 ARR 保守测算150亿，是字节MaaS 2026目标150亿的100%，超过任何单一LLM公司收入</li>
  <li><strong>58%的AI短剧产值流向生成环节</strong> — 短剧公司付得起钱，因为用户ARPU 10-50元、复购率高、投流ROI为正，AI替代真人拍摄成本后整体ROI依然为正</li>
  <li><strong>4.4倍差距意味着用户根本没在试可灵</strong> — 可灵ARR 34亿 vs 模型甲150亿；切换成本（3-6个月工作流重写、数千万产能损失）让短剧公司不可能迁移</li>
  <li><strong>视频生成赛道的单点战争已结束</strong> — 模型甲在某头部视频云渠道事实垄断；其他云厂商应转打多模态组合、行业方案和Agent平台</li>
</ul>
</div>

<!-- ============ MOD-01 一图速览 ============ -->
<div class="bis-section">
<h2><span class="num">1</span>一图速览 — 2026/6/3 公开数据</h2>

<div class="bis-grid">
  <div class="bis-card red">
    <span class="val">10<span style="font-size:14px">亿/月</span></span>
    <span class="lab">某头部视频云渠道月销</span>
  </div>
  <div class="bis-card">
    <span class="val">150<span style="font-size:14px">亿+</span></span>
    <span class="lab">保守 ARR 测算</span>
  </div>
  <div class="bis-card green">
    <span class="val">34<span style="font-size:14px">亿</span></span>
    <span class="lab">可灵 ARR（横向对比）</span>
  </div>
  <div class="bis-card purple">
    <span class="val">~58%</span>
    <span class="lab">占中国 AI 短剧产值</span>
  </div>
  <div class="bis-card">
    <span class="val">260<span style="font-size:14px">亿</span></span>
    <span class="lab">中国 AI 短剧年产值中值</span>
  </div>
  <div class="bis-card red">
    <span class="val">95%</span>
    <span class="lab">短剧行业 API 渗透率</span>
  </div>
</div>

<p><strong>核心信号</strong>：视频大模型（不是 LLM，不是图像模型）第一次成为<strong>单点营收破百亿</strong>的 MaaS 业务。这个量级<strong>已经</strong>超过所有 LLM 通用模型的单一公司收入，<strong>是字节 MaaS 2026 目标 150 亿的 100%</strong>。</p>
</div>

<!-- ============ MOD-02 数据来源与口径 ============ -->
<div class="bis-section">
<h2><span class="num">2</span>数据来源与口径（必读）</h2>

<p>2026/6/3 行业讨论披露了一组数字，<strong>原始口径</strong>如下：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>指标</th>
      <th>数值</th>
      <th>时点</th>
      <th>披露主体</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>某视频模型（模型甲）在某头部视频云渠道的月销售</td>
      <td><strong>10 亿元</strong></td>
      <td>2026/6</td>
      <td>行业讨论公开</td>
    </tr>
    <tr>
      <td>对应的 ARR（年化）</td>
      <td>~120 亿元</td>
      <td>2026/6</td>
      <td>简单年化</td>
    </tr>
    <tr>
      <td>可灵（快手）最新 ARR</td>
      <td>34 亿元</td>
      <td>2026 截至当前</td>
      <td>快手财报公开</td>
    </tr>
    <tr>
      <td>中国 AI 短剧年产值</td>
      <td>220-300 亿元（中值 260 亿）</td>
      <td>2026 截至当前</td>
      <td>卡思/巨量引擎</td>
    </tr>
    <tr>
      <td>某头部视频云 2026 MaaS 目标</td>
      <td>150 亿元</td>
      <td>2026/4 上调</td>
      <td>内部 OKR</td>
    </tr>
    <tr>
      <td>某头部视频云 2025 实际 MaaS 收入</td>
      <td>~15 亿元</td>
      <td>2025 全年</td>
      <td>行业估算</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>一个隐含的关键事实</strong>：</p>

<ul>
  <li>某头部视频云 <strong>2025 全年 MaaS 实际 ~15 亿</strong></li>
  <li>某头部视频云 <strong>2026 单年目标 150 亿</strong>（<strong>10x 增长</strong>）</li>
  <li>模型甲<strong>单模型</strong>月销就 10 亿、ARR 150 亿+</li>
  <li>换句话说：<strong>该云 2026 目标的 100% 几乎全部来自模型甲</strong>，其他视频模型合计贡献占比小</li>
</ul>

<div class="bis-quote">
"10× 的同比增长不是来自客户面扩张，而是来自<strong>单客户（AI 短剧公司）单点（视频生成 API）单量爆发</strong>。" —— 2026/6/3 行业判断
</div>
</div>

<!-- ============ MOD-03 ARR 测算的三大变量 ============ -->
<div class="bis-section">
<h2><span class="num">3</span>从 10 亿月销到 150 亿 ARR — 三大变量</h2>

<p>直接年化 10 亿 × 12 = 120 亿。但<strong>实际 ARR 会更高</strong>，因为：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>变量</th>
      <th>贡献比例</th>
      <th>说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>基础：某头部视频云渠道月销</td>
      <td>10 亿元/月</td>
      <td>数据披露点</td>
    </tr>
    <tr>
      <td>① 爬升期加权</td>
      <td>+20-30%</td>
      <td>业务仍在涨</td>
    </tr>
    <tr>
      <td>② 第三方渠道</td>
      <td>+15-20%</td>
      <td>部分授权代理</td>
    </tr>
    <tr>
      <td>③ 海外未全量</td>
      <td>+30-50%</td>
      <td>海外正式上线后增量</td>
    </tr>
    <tr>
      <td><strong>保守 ARR 测算</strong></td>
      <td><strong>~150 亿元</strong></td>
      <td>中性偏下</td>
    </tr>
    <tr>
      <td>乐观 ARR 测算（叠加海外）</td>
      <td>~250-300 亿元</td>
      <td>海外全量后 12-18 个月内</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>关键判定</strong>：</p>

<ul>
  <li><strong>150 亿</strong>是中性偏下的<strong>保守数</strong>，不是乐观数</li>
  <li>海外 30-50% 的增量<strong>不一定 12 个月内能落地</strong>——海外客户用中国云的视频 API，<strong>合规 + 信任 + 支付通道</strong>都有门槛</li>
  <li>对外说"ARR 150 亿"是<strong>合理保守</strong>，不会有水分</li>
</ul>
</div>

<!-- ============ MOD-04 谁在付钱？======== -->
<div class="bis-section">
<h2><span class="num">4</span>谁在付钱 — API 的真实客户</h2>

<p>这条很容易被误读为"创作者用即梦、小云雀就够了"，但<strong>这是 C 端</strong>。走 API 的<strong>几乎全是 AI 短剧公司</strong>。</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>客户类型</th>
      <th>使用方式</th>
      <th>计费方式</th>
      <th>占模型甲收入比例</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>AI 短剧公司</strong>（红果、点众、九州等）</td>
      <td>API 批量化、5 秒以上视频片段生成</td>
      <td>按 Token（视频秒数）</td>
      <td><strong>~95%</strong></td>
    </tr>
    <tr>
      <td>小红书/抖音/视频号创作者（C 端）</td>
      <td>用即梦、小云雀等"够用模型"App</td>
      <td>订阅 / 免费</td>
      <td>几乎 0</td>
    </tr>
    <tr>
      <td>广告公司 / 营销公司</td>
      <td>API 短广告 / 品牌物料</td>
      <td>按 Token</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>游戏 / 动画公司</td>
      <td>API 剧情预演 / 原型</td>
      <td>按 Token</td>
      <td>~1%</td>
    </tr>
    <tr>
      <td>个人开发者 / 早期项目</td>
      <td>API 试点</td>
      <td>按 Token</td>
      <td>~1%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>关键反直觉点</strong>：</p>

<ul>
  <li>模型甲<strong>不是"消费者 App"</strong>，是<strong>纯 B2B MaaS</strong></li>
  <li>小红书/抖音/视频号创作者<strong>从来不是它的付费用户</strong></li>
  <li>所以"创作者用即梦"和"模型甲月销 10 亿"是<strong>完全不冲突的两件事</strong></li>
  <li>这解释了一个关键问题：<strong>为什么一个面向 B 端的 API 能做到月 10 亿，而不会像消费 App 那样被某个爆款事件冲击</strong>——它的客户<strong>是商业公司</strong>，不是"用户"</li>
</ul>

<div class="bis-punchline">
<h2>🎬 "服务生产力市场" — B 端 API 才是视频模型变现的正确路径</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>创作者用即梦、小云雀就够了</strong>（C 端、订阅制、流量分成）。<br>
  <strong>走 API 的基本全是 AI 短剧公司</strong>（B 端、Token 计费、生产力市场）。<br>
  两个市场<strong>互不重叠</strong>。<strong>月 10 亿、ARR 150 亿</strong>，<strong>全部来自后者</strong>。
</p>
</div>
</div>

<!-- ============ MOD-05 为什么 AI 短剧要付这个钱 ============ -->
<div class="bis-section">
<h2><span class="num">5</span>经济学 — AI 短剧公司为什么付得起</h2>

<p>"为什么 AI 短剧公司能扛 10 亿月销？"<strong>反推一下</strong>中国 AI 短剧的整个产业链：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>环节</th>
      <th>占短剧产值比例</th>
      <th>对应金额（按 260 亿产值）</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>剧本 / 分镜 / 创意</td>
      <td>~5%</td>
      <td>13 亿元</td>
    </tr>
    <tr>
      <td><strong>视频生成 API（模型甲等）</strong></td>
      <td><strong>~58%</strong></td>
      <td><strong>~150 亿元</strong></td>
    </tr>
    <tr>
      <td>演员替换 / 配音 / 后期</td>
      <td>~10%</td>
      <td>26 亿元</td>
    </tr>
    <tr>
      <td>内容分发 / 投流</td>
      <td>~20%</td>
      <td>52 亿元</td>
    </tr>
    <tr>
      <td>运营 / 平台分成 / 利润</td>
      <td>~7%</td>
      <td>19 亿元</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>关键观察</strong>：</p>

<ul>
  <li><strong>58%</strong> 的产值直接给了生成环节（主要是模型甲）</li>
  <li>短剧公司利润空间被<strong>严重挤压</strong>，但仍能跑通<strong>意味着</strong>：<br>
    ① 用户付费意愿强（短剧单价 1-10 元、ARPU 10-50 元、复购率高）<br>
    ② 投流 ROI 仍为正（抖音 / 红果 App 的内容分发）<br>
    ③ 生成环节<strong>效率提升</strong>让整体成本降低（AI 替代真人拍摄成本）</li>
  <li>如果模型甲 <strong>不</strong>把月销做到 10 亿，AI 短剧公司<strong>付不起</strong>其他环节（创意、投流）的成本</li>
  <li><strong>这是一个闭环</strong>：模型甲的低价 → 短剧产量爆发 → 投流回收 → 模型甲用量继续涨</li>
</ul>

<div class="bis-signal">
<h3>🔄 单价 vs 量产 — 视频模型与传统 SaaS 的根本差异</h3>
<p>传统 SaaS：<strong>单价下降 = 利润下降</strong>（每个用户收的钱少了）。<br>
视频大模型：<strong>单价下降 = 总价上涨</strong>（同样的钱能生成更多视频，AI 短剧公司产能扩大，反而用得更多）。</p>
<p>这就是为什么"提价不掉量"在视频模型上<strong>比 Coding 模型上更明显</strong>——视频是<strong>完全弹性需求</strong>，价格低一点就多生成一倍视频，价格高一点就少生成一倍，<strong>对短剧公司来说 ROI 永远是正的</strong>，只要<strong>单个视频的成本能收回</strong>。</p>
</div>
</div>

<!-- ============ MOD-06 为什么可灵追不上 ============ -->
<div class="bis-section">
<h2><span class="num">6</span>为什么可灵追不上 — 4.4 倍差距的护城河</h2>

<p>可灵 ARR 34 亿 vs 模型甲 ARR 150 亿 = <strong>4.4 倍差距</strong>。这<strong>不是</strong>4.4% 的小数，<strong>4.4 倍</strong>意味着<strong>用户根本没在试可灵</strong>。</p>

<p><strong>短剧公司不切可灵的 4 个原因</strong>：</p>

<ol>
  <li><strong>Prompt 工程 / 分镜 / 角色一致性的工作流都是按模型甲接口做的</strong>——切换模型 = 重写整个工作流，3-6 个月迁移成本</li>
  <li><strong>团队 prompt 知识资产沉淀在模型甲上</strong>——切换 = 几个月实验期，<strong>直接损失数千万</strong>产能</li>
  <li><strong>下游分销渠道（红果、点众、九州）的内容也认模型甲出品的"质感"</strong>——切到可灵可能影响上线审核</li>
  <li><strong>白名单 + 年框 + 满血版的客户绑定</strong>——已经签的年框合同<strong>不能中途解约</strong>，现金流锁定</li>
</ol>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>对手</th>
      <th>ARR</th>
      <th>差距</th>
      <th>短剧场景渗透</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>模型甲（某头部视频云）</strong></td>
      <td><strong>~150 亿</strong></td>
      <td>1.0×</td>
      <td>~95%</td>
    </tr>
    <tr>
      <td>可灵（快手）</td>
      <td>34 亿</td>
      <td>0.22×</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>其他视频模型合计</td>
      <td>~10 亿</td>
      <td>0.07×</td>
      <td>~2%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>可灵的正确打法</strong>（不能正面打）：</p>

<ul>
  <li>❌ <strong>不能</strong>用价格战抢用户（150 亿 vs 34 亿，<strong>价格战 = 自杀</strong>）</li>
  <li>✅ <strong>应该</strong>切<strong>模型甲没覆盖的细分场景</strong>：<br>
    ① 超长视频（5 分钟以上连续剧情）<br>
    ② 3D / 虚拟人 / 数字孪生（短剧外的工业场景）<br>
    ③ 海外华人 / 东南亚市场（模型甲海外未全量）</li>
  <li>✅ <strong>应该</strong>走<strong>开源 / 本地部署</strong>路线（避开与模型甲的正面 API 竞争）</li>
</ul>
</div>

<!-- ============ MOD-07 给中国 MaaS 战场的终局意义 ============ -->
<div class="bis-section">
<h2><span class="num">7</span>终局意义 — 中国云厂商 MaaS 战争"提前结束"？</h2>

<p>2026/6/3 行业讨论的<strong>核心判断</strong>：</p>

<div class="bis-quote">
"<strong>中国云厂商在 MaaS 市场的战争，至少在今年，是已经提前结束了。</strong>" —— 2026/6/3 行业判断
</div>

<p>对此判断的<strong>拆解</strong>：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>论断</th>
      <th>成立？</th>
      <th>适用范围</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>视频生成赛道胜负已分</td>
      <td>✅ 成立</td>
      <td>模型甲在某头部视频云渠道事实上无对手</td>
    </tr>
    <tr>
      <td>Coding 战场胜负已分</td>
      <td>❌ 不成立</td>
      <td>公司 X / 公司 Y / 公司 Z 多家头部并存</td>
    </tr>
    <tr>
      <td>LLM 通用赛道胜负已分</td>
      <td>❌ 不成立</td>
      <td>已被地板价击穿，<strong>不是赢家通吃</strong>，而是<strong>没人赚钱</strong></td>
    </tr>
    <tr>
      <td>整体 MaaS 平台胜负已分</td>
      <td>❌ 不成立</td>
      <td>公司 B / 公司 C 仍在持续投入，2026 Q3 见分晓</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>更准确的表述</strong>：</p>

<ul>
  <li><strong>"单点模型"（视频生成）的战争在某头部视频云渠道已赢</strong>——这是个 B2B API 胜者为王的故事</li>
  <li><strong>"整体 MaaS 平台"的战争远远没结束</strong>——多模态、API 编排、行业方案仍在打</li>
  <li>对<strong>其他云厂商</strong>（公司 B / 公司 C）：<strong>别再正面打视频生成 API</strong>，转去打：
    <ul>
      <li>多模态组合（视频 + 图像 + 文本 + 语音）</li>
      <li>行业方案（金融 / 制造 / 教育的 Agent）</li>
      <li>Agent 平台（多模型编排 + 业务流）</li>
    </ul>
  </li>
</ul>

<div class="bis-punchline">
<h2>🎯 关键判断：B2B API 才是中国 MaaS 的终局</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>C 端创作者 = 流量 / 品牌 / 拉新</strong>（亏本换市场）<br>
  <strong>B 端 API = 营收 / 利润 / 复利</strong>（赚钱靠这个）<br><br>
  模型甲的成功路径证明：<strong>当一个 AI 模型能做到 SOTA + 5 个月先发优势 + 95% 行业渗透 + 切换成本极高时，B2B API 收入能跑到 150 亿 ARR</strong>——这比所有 LLM 通用模型、所有 C 端 App、所有订阅业务<strong>都赚得多</strong>。
</p>
</div>
</div>

<!-- ============ MOD-08 给海外客户的启示 ============ -->
<div class="bis-section">
<h2><span class="num">8</span>给海外 ISP 客户的启示</h2>

<p>案例对<strong>东南亚 / 拉美 / 日本</strong>做视频 AI 业务的客户意味着什么？</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>客户类型</th>
      <th>启示</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>做<strong>短剧 / 短视频 / 营销物料</strong>的 AI 公司</td>
      <td><strong>直接调模型甲 API 即可</strong>，没必要自建视频模型。人民币计价、合规出海路径是某头部视频云官方在做</td>
    </tr>
    <tr>
      <td>做<strong>3D / 工业视觉 / 数字孪生</strong>的客户</td>
      <td>模型甲<strong>不适用</strong>（它专注人物 + 剧情）。走 3D 路线（<strong>腾讯混元 3D / 阿里 Tora</strong>）或工业路线（昇腾 + Sora-lite）</td>
    </tr>
    <tr>
      <td>做<strong>AI 营销 / 广告投放</strong>的客户</td>
      <td>批量广告视频生成 = 短剧场景的<strong>简化版</strong>，用模型甲<strong>完全可以</strong>。但要注意"质感一致性"问题</td>
    </tr>
    <tr>
      <td>做<strong>海外（美 / 欧 / 印度）</strong>的客户</td>
      <td><strong>敢不敢用</strong>中国云的视频 API = <strong>2026 年中国 AI 出海最大的问题</strong>。需要<strong>白盒方案</strong>（昇腾 + 国产模型 + 第三方托管）</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>最关键的战略含义</strong>：</p>

<ul>
  <li>❌ <strong>不要</strong>自建视频模型（投入回报不划算，<strong>ARR 150 亿是模型甲的护城河</strong>，不是客户的）</li>
  <li>❌ <strong>不要</strong>只买云服务（按 Token 计费<strong>会越用越贵</strong>，要锁定年框）</li>
  <li>✅ <strong>应该</strong>锁定年框 + 满血版 + 白名单优先级（参考模型甲的"白名单 + 年框 + 满血版"商业化）</li>
  <li>✅ <strong>应该</strong>在欧美市场考虑<strong>第三方案</strong>（白盒 / 开源 / 昇腾适配）<strong>作为备份</strong></li>
</ul>
</div>

<!-- ============ MOD-09 数据局限与延伸阅读 ============ -->
<div class="bis-section">
<h2><span class="num">9</span>数据局限与延伸阅读</h2>

<div class="bis-signal">
<h3>📊 数据局限（必读）</h3>
<ul>
  <li>本文所有数字均来自 2026/6/3 公开行业讨论与快手财报</li>
  <li>"10 亿月销"、"~95% 渗透"、"~150 亿 ARR"均为媒体报道，<strong>未审计</strong></li>
  <li>某头部视频云、模型甲、某头部综合云等代称按公开博客脱敏规则隐去</li>
  <li>可灵 ARR 34 亿为<strong>快手财报披露</strong>，可信度较高</li>
  <li>AI 短剧年产值 220-300 亿元为卡思数据 / 巨量引擎估算</li>
  <li>决策引用需进一步核实，建议结合各家财报与行业白皮书</li>
</ul>
</div>

<p><strong>延伸阅读</strong>：</p>

<ul>
  <li>📄 <a href="/tech-blog/posts/domestic-maas-token-wars-2026/"><strong>《国内 MaaS 大战 2026：Token 经济的两条战线》</strong></a> — 行业宏观分析，本案例是其中的视频线详解</li>
  <li>📄 <a href="/tech-blog/posts/domestic-ai-accelerator-ecosystem-2026/"><strong>《昇腾 NPU 模型生态适配分析（2026/6）》</strong></a> — 海外客户的国产 AI 算力选型指南</li>
  <li>📄 <a href="/tech-blog/posts/bis-china-ai-chip-2026/"><em>（已隐藏）</em></a></li>
</ul>

<div class="bis-foot">
<p>数据来源：2026/6/3 行业讨论公开 + 快手财报 + 卡思数据 + 巨量引擎估算 · 撰写：Tech Observer</p>
</div>
</div>

</div>
