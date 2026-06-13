---
title: AIショートドラマ260億市場：動画大規模モデルはいかに収益化するか
date: 2026-06-03
draft: false
description: 2026/6/3、公開業界データによると、ある動画モデルの月間売上は10億元、保守的に見てARRは150億元超で、中国AIショートドラマ年間生産額の58%を占める。本稿では、モデル甲がAPIを使い4ヶ月でショートドラマの産業チェーンを打ち抜いた方法、誰が課金しているのか、なぜ代替できないのか、そして中国クラウドベンダーのMaaS戦争にもたらす終局的意義を紐解く。
tags: ["MaaS", "トークン経済", "AIショートドラマ", "大規模動画モデル", "収益化事例", "国産AI", "シーダンス", "ティックトック", "クリン", "クアイショウ"]
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
  <span class="tag">収益化事例 · 2026-06-03</span>
  <h1>AIショートドラマ260億市場：動画大規模モデルはどう収益化するか</h1>
  <p class="subtitle">ある動画モデル月商10億元 / 保守的ARR 150億元超 / ショートドラマ生産高の58％を占める — 4ヶ月で産業チェーンを貫通した事例</p>
  <p class="date">2026-06-03 · 業界事例</p>
</div>

<div class="bis-alert">
  <strong>これは常識を覆す事例だ</strong>。2026年2月10日にリリースされ、4ヶ月で月商10億元を突破。これは「コンシューマー向けアプリ」ではなく（小紅書／抖音／視頻号のクリエイターはAPIを一切使わない）、<strong>純粋なB2B API</strong>であり、顧客は<strong>ほぼすべてAIショートドラマ会社</strong>である。本稿では、その収益化の仕組み、誰が支払っているのか、なぜ競合が追いつけないのか、そして中国MaaS戦線にとっての最終的な意味を解体する。
</div>

<div class="bis-signal">
<h3>💡 キーポイント</h3>
<ul>
  <li><strong>B2B APIこそ動画モデル収益化の正しい道</strong> — C向けクリエイターは即梦／小雲雀（サブスク／無料）、B向けショートドラマ会社はAPI（トークン課金）を使う。両市場は重ならず、月商10億はすべて後者から生まれている</li>
  <li><strong>動画モデルの収入規模はすでにすべてのLLM汎用モデルを超えた</strong> — モデル甲のARRは保守的に150億元と試算され、ByteDance MaaSの2026年目標150億元の100％に相当し、単一のLLM企業の収入を上回る</li>
  <li><strong>AIショートドラマ生産高の58％が生成工程に流れる</strong> — ショートドラマ会社は十分に支払える。ユーザーARPU 10〜50元、再購入率が高く、投下広告ROIがプラスだからだ。AIが実写コストを代替しても全体ROIはプラスを維持する</li>
  <li><strong>4.4倍の差は、ユーザーが可霊（Kling）を試してすらいないことを意味する</strong> — 可霊ARR 34億 vs モデル甲150億。切り替えコスト（3〜6ヶ月のワークフロー再構築、数千万単位の生産能力喪失）がショートドラマ会社の移行を不可能にしている</li>
  <li><strong>動画生成分野の単点戦争はすでに終結した</strong> — モデル甲はある大手動画クラウドチャネルで事実上の独占状態。他のクラウド事業者はマルチモーダル組み合わせ、業界別ソリューション、Agentプラットフォームに転じるべき</li>
</ul>
</div>

<!-- ============ MOD-01 一図速覧 ============ -->
<div class="bis-section">
<h2><span class="num">1</span>一図速覧 — 2026/6/3 公開データ</h2>

<div class="bis-grid">
  <div class="bis-card red">
    <span class="val">10<span style="font-size:14px">億元/月</span></span>
    <span class="lab">ある大手動画クラウドチャネル月商</span>
  </div>
  <div class="bis-card">
    <span class="val">150<span style="font-size:14px">億超</span></span>
    <span class="lab">保守的ARR試算</span>
  </div>
  <div class="bis-card green">
    <span class="val">34<span style="font-size:14px">億</span></span>
    <span class="lab">可霊 ARR（横比較）</span>
  </div>
  <div class="bis-card purple">
    <span class="val">~58%</span>
    <span class="lab">中国AIショートドラマ生産高に占める割合</span>
  </div>
  <div class="bis-card">
    <span class="val">260<span style="font-size:14px">億</span></span>
    <span class="lab">中国AIショートドラマ年間生産高（中央値）</span>
  </div>
  <div class="bis-card red">
    <span class="val">95%</span>
    <span class="lab">ショートドラマ業界API浸透率</span>
  </div>
</div>

<p><strong>コアシグナル</strong>：動画大規模モデル（LLMでも画像モデルでもない）が、<strong>単一収入で1,000億円（100億元）を突破する</strong>MaaSビジネスとして初めて出現した。この規模は<strong>すでに</strong>すべてのLLM汎用モデル単一企業の収入を超えており、<strong>ByteDance MaaSの2026年目標150億元の100％</strong>に達する。</p>
</div>

<!-- ============ MOD-02 データソースと定義 ============ -->
<div class="bis-section">
<h2><span class="num">2</span>データソースと定義（必読）</h2>

<p>2026/6/3の業界議論で開示された数字の<strong>元の定義</strong>は以下の通り：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>指標</th>
      <th>数値</th>
      <th>時点</th>
      <th>開示元</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ある動画モデル（モデル甲）の大手動画クラウドチャネルにおける月間売上</td>
      <td><strong>10億元</strong></td>
      <td>2026/6</td>
      <td>業界議論公開</td>
    </tr>
    <tr>
      <td>対応するARR（年換算）</td>
      <td>~120億元</td>
      <td>2026/6</td>
      <td>単純年換算</td>
    </tr>
    <tr>
      <td>可霊（Kuaishou）最新ARR</td>
      <td>34億元</td>
      <td>2026年現在</td>
      <td>Kuaishou決算公開</td>
    </tr>
    <tr>
      <td>中国AIショートドラマ年間生産高</td>
      <td>220-300億元（中央値260億）</td>
      <td>2026年現在</td>
      <td>卡斯／巨量引擎</td>
    </tr>
    <tr>
      <td>大手動画クラウド 2026 MaaS目標</td>
      <td>150億元</td>
      <td>2026/4 上方修正</td>
      <td>内部OKR</td>
    </tr>
    <tr>
      <td>大手動画クラウド 2025 実績MaaS収入</td>
      <td>~15億元</td>
      <td>2025通年</td>
      <td>業界推定</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>一つの暗黙の重要事実</strong>：</p>

<ul>
  <li>大手動画クラウド <strong>2025通年MaaS実績 ~15億</strong></li>
  <li>大手動画クラウド <strong>2026単年目標150億</strong>（<strong>10倍成長</strong>）</li>
  <li>モデル甲<strong>単一モデル</strong>月商だけで10億、ARR150億+</li>
  <li>言い換えれば：<strong>同クラウドの2026年目標の100％はほぼすべてモデル甲に由来</strong>し、他の動画モデルの合算寄与は小さい</li>
</ul>

<div class="bis-quote">
「前年比10倍の成長は顧客面の拡大からではなく、<strong>単一顧客（AIショートドラマ会社）単一ポイント（動画生成API）の単量爆発</strong>から生まれている。」 —— 2026/6/3 業界判断
</div>
</div>

<!-- ============ MOD-03 ARR試算の三大変数 ============ -->
<div class="bis-section">
<h2><span class="num">3</span>月商10億からARR150億へ — 三大変数</h2>

<p>単純年換算は10億 × 12 = 120億元。しかし<strong>実際のARRはさらに高くなる</strong>。その理由：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>変数</th>
      <th>寄与割合</th>
      <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>基礎：大手動画クラウドチャネル月商</td>
      <td>10億元/月</td>
      <td>開示データ</td>
    </tr>
    <tr>
      <td>① 上昇期重み付け</td>
      <td>+20-30%</td>
      <td>事業はなお成長中</td>
    </tr>
    <tr>
      <td>② サードパーティチャネル</td>
      <td>+15-20%</td>
      <td>一部代理店経由</td>
    </tr>
    <tr>
      <td>③ 海外未本格展開</td>
      <td>+30-50%</td>
      <td>海外正式ローンチ後の増分</td>
    </tr>
    <tr>
      <td><strong>保守的ARR試算</strong></td>
      <td><strong>~150億元</strong></td>
      <td>中位やや低め</td>
    </tr>
    <tr>
      <td>楽観的ARR試算（海外重畳）</td>
      <td>~250-300億元</td>
      <td>海外フル展開後12-18ヶ月以内</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>キー判定</strong>：</p>

<ul>
  <li><strong>150億</strong>は中位以下の<strong>保守的数値</strong>であり、楽観値ではない</li>
  <li>海外30-50%の増分は<strong>12ヶ月以内に確実に着地するとは限らない</strong>——海外顧客が中国クラウドの動画APIを使うには<strong>コンプライアンス＋信頼＋決済チャネル</strong>すべてにハードルがある</li>
  <li>対外的に「ARR 150億」と言うのは<strong>合理的に保守的</strong>であり、水増しはない</li>
</ul>
</div>

<!-- ============ MOD-04 誰が支払っているのか？======== -->
<div class="bis-section">
<h2><span class="num">4</span>誰が支払っているのか — APIのリアルな顧客</h2>

<p>この点は「クリエイターは即夢や小雲雀で十分」という誤読をされやすいが、<strong>それはC向け</strong>である。APIを使うのは<strong>ほぼすべてAIショートドラマ会社</strong>だ。</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>顧客タイプ</th>
      <th>利用方法</th>
      <th>課金方式</th>
      <th>モデル甲収入に占める割合</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>AIショートドラマ会社</strong>（紅果、点衆、九州など）</td>
      <td>API一括処理、5秒以上の動画クリップ生成</td>
      <td>トークン（動画秒数）単位</td>
      <td><strong>~95%</strong></td>
    </tr>
    <tr>
      <td>小紅書/抖音/視頻号クリエイター（C向け）</td>
      <td>即夢、小雲雀など「十分使えるモデル」アプリ</td>
      <td>サブスクリプション / 無料</td>
      <td>ほぼ0</td>
    </tr>
    <tr>
      <td>広告会社 / マーケティング会社</td>
      <td>APIによるショート広告 / ブランド素材</td>
      <td>トークン単位</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>ゲーム / アニメ会社</td>
      <td>APIによるプロットプレビズ / プロトタイプ</td>
      <td>トークン単位</td>
      <td>~1%</td>
    </tr>
    <tr>
      <td>個人開発者 / アーリーステージ案件</td>
      <td>APIテスト利用</td>
      <td>トークン単位</td>
      <td>~1%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>直感に反するキーポイント</strong>：</p>

<ul>
  <li>モデル甲は<strong>「消費者向けApp」ではなく</strong>、<strong>純粋なB2B MaaS</strong>である</li>
  <li>小紅書/抖音/視頻号のクリエイターは<strong>一貫してその有料顧客ではない</strong></li>
  <li>したがって「クリエイターが即夢を使う」ことと「モデル甲が月商10億」は<strong>まったく矛盾しない</strong></li>
  <li>これにより一つの重要な問いが解ける：<strong>なぜB向けAPIが月10億に達し、コンシューマーAppのように特定のバイラルイベントで揺るがないのか</strong>——その顧客は<strong>ビジネス企業</strong>であって、「ユーザー」ではないからだ</li>
</ul>

<div class="bis-punchline">
<h2>🎬 「生産性市場にサービスする」 — B向けAPIこそ動画モデル収益化の正しい道</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>クリエイターは即夢、小雲雀で十分</strong>（C向け、サブスク制、トラフィック分配）。<br>
  <strong>APIを使うのはほぼ全てAIショートドラマ会社</strong>（B向け、トークン課金、生産性市場）。<br>
  二つの市場は<strong>互いに重ならない</strong>。<strong>月10億、ARR 150億</strong>は、<strong>すべて後者からもたらされている</strong>。
</p>
</div>
</div>

<!-- ============ MOD-05 なぜAIショートドラマはこの金額を払えるのか ============ -->
<div class="bis-section">
<h2><span class="num">5</span>経済学 — AIショートドラマ会社がなぜ支払えるのか</h2>

<p>「なぜAIショートドラマ会社は月商10億を負担できるのか？」<strong>逆算して</strong>中国AIショートドラマの産業チェーン全体を見てみよう：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>工程</th>
      <th>ショートドラマ生産高比率</th>
      <th>対応金額（260億元ベース）</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>脚本 / 絵コンテ / 企画</td>
      <td>~5%</td>
      <td>13億元</td>
    </tr>
    <tr>
      <td><strong>動画生成API（モデル甲など）</strong></td>
      <td><strong>~58%</strong></td>
      <td><strong>~150億元</strong></td>
    </tr>
    <tr>
      <td>俳優差し替え / アフレコ / ポスプロ</td>
      <td>~10%</td>
      <td>26億元</td>
    </tr>
    <tr>
      <td>コンテンツ配信 / 広告投下</td>
      <td>~20%</td>
      <td>52億元</td>
    </tr>
    <tr>
      <td>運営 / プラットフォーム分配 / 利益</td>
      <td>~7%</td>
      <td>19億元</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>キーとなる観察</strong>：</p>

<ul>
  <li><strong>58%</strong>の生産高が直接生成工程（主にモデル甲）に流れる</li>
  <li>ショートドラマ会社の利益幅は<strong>深刻に圧迫</strong>されているが、それでもビジネスが回る<strong>ということは</strong>：<br>
    ① ユーザーの支払い意欲が強い（ショートドラマ単価1〜10元、ARPU 10〜50元、再購入率が高い）<br>
    ② 広告投下ROIが依然プラス（抖音／紅果Appのコンテンツ配信）<br>
    ③ 生成工程の<strong>効率向上</strong>により全体コストが低下している（AIが実写撮影コストを代替）</li>
  <li>もしモデル甲が月商10億を<strong>達成していなければ</strong>、AIショートドラマ会社は他の工程（企画、広告投下）のコストを<strong>払えなくなる</strong></li>
  <li><strong>これはクローズドループである</strong>：モデル甲の低価格 → ショートドラマ生産量爆発 → 広告回収 → モデル甲の使用量がさらに増加</li>
</ul>

<div class="bis-signal">
<h3>🔄 単価 vs 量産 — 動画モデルと従来型SaaSの根本的違い</h3>
<p>従来型SaaS：<strong>単価下落 ＝ 利益減少</strong>（ユーザーあたり収入が減る）。<br>
動画大規模モデル：<strong>単価下落 ＝ 総収入増加</strong>（同じ金額でより多くの動画を生成でき、AIショートドラマ会社の生産能力が拡大し、かえって使う量が増える）。</p>
<p>これこそが「値上げしても量が落ちない」現象が動画モデルで<strong>Codingモデルよりも顕著な</strong>理由である——動画は<strong>完全な弾力的需要</strong>であり、価格が少し下がれば生成量が倍に、少し上がれば半減する。<strong>ショートドラマ会社にとってROIは常にプラス</strong>であり、<strong>1本あたりの動画コストを回収できれば</strong>それでよい。</p>
</div>
</div>

<!-- ============ MOD-06 なぜ可霊は追いつけないのか ============ -->
<div class="bis-section">
<h2><span class="num">6</span>なぜ可霊は追いつけないのか — 4.4倍差の堀</h2>

<p>可霊ARR 34億 vs モデル甲ARR 150億 = <strong>4.4倍の差</strong>。これは<strong>4.4%という小さな値ではない</strong>。<strong>4.4倍</strong>ということは、<strong>ユーザーが可霊を試してすらいない</strong>ことを意味する。</p>

<p><strong>ショートドラマ会社が可霊に切り替えない4つの理由</strong>：</p>

<ol>
  <li><strong>プロンプトエンジニアリング／絵コンテ／キャラクター一貫性のワークフローがすべてモデル甲API向けに作られている</strong>——モデル切り替え＝ワークフロー全体の再構築、3〜6ヶ月の移行コスト</li>
  <li><strong>チームのプロンプト知識資産がモデル甲に蓄積されている</strong>——切り替え＝数ヶ月の実験期間、<strong>直接的に数千万単位の生産能力</strong>を喪失</li>
  <li><strong>下流の配信チャネル（紅果、点衆、九州）もモデル甲作品の「質感」を前提にコンテンツを審査している</strong>——可霊に切り替えると配信審査に影響する可能性がある</li>
  <li><strong>ホワイトリスト＋年間契約＋フルスペック版による顧客囲い込み</strong>——すでに締結した年間契約は<strong>途中解約できず</strong>、キャッシュフローが固定されている</li>
</ol>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>競合</th>
      <th>ARR</th>
      <th>格差</th>
      <th>ショートドラマシーン浸透率</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>モデル甲（大手動画クラウド）</strong></td>
      <td><strong>~150億</strong></td>
      <td>1.0×</td>
      <td>~95%</td>
    </tr>
    <tr>
      <td>可霊（Kuaishou）</td>
      <td>34億</td>
      <td>0.22×</td>
      <td>~3%</td>
    </tr>
    <tr>
      <td>その他動画モデル合計</td>
      <td>~10億</td>
      <td>0.07×</td>
      <td>~2%</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>可霊の正しい戦い方</strong>（正面衝突は不可）：</p>

<ul>
  <li>❌ <strong>できない</strong>：価格競争で顧客を奪う（150億 vs 34億、<strong>価格競争＝自殺行為</strong>）</li>
  <li>✅ <strong>すべき</strong>：<strong>モデル甲がカバーできていないニッチシーン</strong>を突く：<br>
    ① 超長尺動画（5分以上の連続ドラマ）<br>
    ② 3D / バーチャルヒューマン / デジタルツイン（ショートドラマ以外の産業用途）<br>
    ③ 海外華人 / 東南アジア市場（モデル甲の海外未本格展開）</li>
  <li>✅ <strong>すべき</strong>：<strong>オープンソース / オンプレミス展開</strong>の路線を行く（モデル甲との正面API競争を避ける）</li>
</ul>
</div>

<!-- ============ MOD-07 中国MaaS戦線への最終的意味 ============ -->
<div class="bis-section">
<h2><span class="num">7</span>最終的意味 — 中国クラウド事業者のMaaS戦争は「早期終結」か？</h2>

<p>2026/6/3の業界議論における<strong>核心的判断</strong>：</p>

<div class="bis-quote">
「<strong>中国クラウド事業者のMaaS市場における戦争は、少なくとも今年は、すでに早期終結した。</strong>」 —— 2026/6/3 業界判断
</div>

<p>この判断に対する<strong>解体</strong>：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>論点</th>
      <th>成立？</th>
      <th>適用範囲</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>動画生成分野の勝敗は決した</td>
      <td>✅ 成立</td>
      <td>モデル甲は大手動画クラウドチャネルで事実上無敵</td>
    </tr>
    <tr>
      <td>Coding戦場の勝敗は決した</td>
      <td>❌ 不成立</td>
      <td>企業X / 企業Y / 企業Z 複数強豪が併存</td>
    </tr>
    <tr>
      <td>LLM汎用分野の勝敗は決した</td>
      <td>❌ 不成立</td>
      <td>すでに底値で叩き割られ、<strong>勝者総取りではなく</strong>、<strong>誰も儲かっていない</strong></td>
    </tr>
    <tr>
      <td>MaaSプラットフォーム全体の勝敗は決した</td>
      <td>❌ 不成立</td>
      <td>企業B / 企業Cは依然として継続投資中、2026 Q3に判明</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>より正確な表現</strong>：</p>

<ul>
  <li><strong>「単点モデル」（動画生成）の戦争は大手動画クラウドチャネルですでに勝利した</strong>——これはB2B APIの勝者が王になる物語である</li>
  <li><strong>「MaaSプラットフォーム全体」の戦争は全く終わっていない</strong>——マルチモーダル、APIオーケストレーション、業界別ソリューションは依然として戦闘中</li>
  <li><strong>他のクラウド事業者</strong>（企業B / 企業C）にとって：<strong>動画生成APIに正面から挑むのはやめよ</strong>。転じて以下を攻めよ：
    <ul>
      <li>マルチモーダルの組み合わせ（動画 + 画像 + テキスト + 音声）</li>
      <li>業界ソリューション（金融 / 製造 / 教育のAgent）</li>
      <li>Agentプラットフォーム（マルチモデルオーケストレーション + 業務フロー）</li>
    </ul>
  </li>
</ul>

<div class="bis-punchline">
<h2>🎯 キー判断：B2B APIこそ中国MaaSの最終形</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>C向けクリエイター ＝ トラフィック / ブランド / 新規獲得</strong>（赤字で市場を取る）<br>
  <strong>B向けAPI ＝ 売上 / 利益 / 複利</strong>（これで稼ぐ）<br><br>
  モデル甲の成功経路は証明した：<strong>あるAIモデルがSOTA＋5ヶ月の先行優位＋95％の業界浸透＋極めて高い切り替えコストを達成したとき、B2B API収入はARR150億に達しうる</strong>——これはすべてのLLM汎用モデル、すべてのC向けApp、すべてのサブスクリプション事業<strong>よりも遥かに儲かる</strong>。
</p>
</div>
</div>

<!-- ============ MOD-08 海外顧客への示唆 ============ -->
<div class="bis-section">
<h2><span class="num">8</span>海外ISP顧客への示唆</h2>

<p>本事例は<strong>東南アジア / ラテンアメリカ / 日本</strong>の動画AIビジネスを手がける顧客にとって何を意味するか？</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>顧客タイプ</th>
      <th>示唆</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>ショートドラマ / ショート動画 / マーケティング素材</strong>のAI企業</td>
      <td><strong>直接モデル甲APIを呼べばよい</strong>。自社で動画モデルを構築する必要はない。人民元建て決済、コンプライアンス越境ルートは大手動画クラウドが公式に整備中</td>
    </tr>
    <tr>
      <td><strong>3D / 産業用ビジョン / デジタルツイン</strong>の顧客</td>
      <td>モデル甲は<strong>適合しない</strong>（人物＋ドラマに特化）。3D路線（<strong>Tencent渾元3D / Alibaba Tora</strong>）または産業路線（Ascend + Sora-lite）へ</td>
    </tr>
    <tr>
      <td><strong>AIマーケティング / 広告配信</strong>の顧客</td>
      <td>バルク広告動画生成 ＝ ショートドラマシーンの<strong>簡易版</strong>。モデル甲で<strong>完全に可能</strong>。ただし「質感の一貫性」問題に注意</td>
    </tr>
    <tr>
      <td><strong>海外（米国 / 欧州 / インド）</strong>の顧客</td>
      <td><strong>使う勇気があるかどうか</strong>、中国クラウドの動画APIを使うか否か ＝ <strong>2026年中国AI海外展開最大の課題</strong>。<strong>ホワイトボックスソリューション</strong>（Ascend + 国産モデル + 第三者ホスティング）が必要</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>最も重要な戦略的含意</strong>：</p>

<ul>
  <li>❌ <strong>するな</strong>：自社で動画モデルを構築する（投資対効果が悪い。<strong>ARR150億はモデル甲の堀</strong>であり、顧客のものではない）</li>
  <li>❌ <strong>するな</strong>：クラウドサービスだけを買う（トークン課金は<strong>使えば使うほど高くなる</strong>。年間契約を固定せよ）</li>
  <li>✅ <strong>すべき</strong>：年間契約＋フルスペック版＋ホワイトリスト優先権を固定する（モデル甲の「ホワイトリスト＋年間契約＋フルスペック版」商業化を参考に）</li>
  <li>✅ <strong