---
title: 国内MaaS大戦2026：Token経済の二つの戦線
date: 2026-06-02
draft: false
description: 2026年の国内MaaS事業深層観察：あるトップビデオクラウドは2026年の目標を前年比10倍の150億元とし、ビデオモデルの月間売上は10億元を突破。CodingモデルはQ1に83%値上げした一方、呼び出し量は400%増加した。コーディングとビデオモデルはすでに収益の主戦場となり、LLM汎用市場は底値で打ち抜かれた。
tags: ["マース", "トークンエコノミー", "国産AI", "クラウドコンピューティング", "大規模モデル", "推理", "GitCode", "オープンソース大規模モデル"]
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
  <span class="tag">業界観察 · 2026年6月</span>
  <h1>中国国内MaaS大戦2026：トークンエコノミーの二つの戦線</h1>
  <p class="subtitle">某大手動画クラウド、2026年の売上目標150億元 / Codingモデル、83%値上げも利用量400%増 / LLM汎用コースは底値で崩壊</p>
  <p class="date">2026年6月2日 · 業界観察</p>
</div>

<div class="bis-alert">
⚠️ <strong>2026年の業界コンセンサスは明確</strong>：最高クラスのモデルを作ること ＝ トークン消費量を増やし、顧客の支払い意欲を高める最善の方法である。LLM汎用コースは飽和状態であり、<strong>Coding（コードモデル）+ 動画モデル</strong>が収益化の二大主戦場となっている。本稿は2026年6月3日時点の公開業界報道に基づき、MaaS事業の全貌を復元する。
</div>

<div class="bis-signal">
<h3>💡 キーポイント</h3>
<ul>
  <li><strong>動画モデル：単点競争は既に終結</strong> — モデル甲は某大手動画クラウドにおいて、保守的なARR試算で150億元超、ショートドラマ業界での普及率95%で事実上の独占状態。Kling（可灵）のARRはわずか34億元、4.4倍の差</li>
  <li><strong>Codingモデル：値上げしても利用量減らず</strong> — 某大手Coding企業、Q1に83%値上げするも利用量は400%増加。中核的シーンで初めて海外トップ企業と価格面で肩を並べる</li>
  <li><strong>LLM汎用コースは底値で崩壊</strong> — 未来は最高クラスのモデル＋業界浸透にあり、価格競争ではない</li>
  <li><strong>シンデレラのガラスの靴効果</strong>：AIモデルは先行者利益が極めて強く、初期ユーザーの粘着性が極めて高い。これが、トップモデルが継続的な値上げに踏み切れる理由を説明する</li>
  <li><strong>プラットフォーム戦争はまだ終わっていない</strong>：単点モデルの勝敗は決したが、MaaSプラットフォーム全体（マルチモーダル/APIオーケストレーション/業界ソリューション）の戦争は、2026年第3四半期に決着すると予想される</li>
</ul>
</div>

<div class="bis-update">
  <span class="tag">📌 6月3日 データ更新</span>
  <p>公開データによると、<strong>某動画モデル（モデル甲）は某大手動画クラウドのチャネルで月間売上10億元</strong>、ARR換算で150億元超と試算される。AIショートドラマの年間生産額は220～300億元で、モデル甲がその約58%を占める。詳細は <a href="#mod-02-deep">2.4章 ショートドラマ経済の分析</a> と <a href="#mod-06-extreme">6.2章 ガラスの靴の極端な事例</a>、および関連事例ブログ <a href="/tech-blog/posts/ai-short-drama-260-billion-market-revenue-case-2026/"><strong>『AIショートドラマ260億市場：動画大規模モデルの収益化方法』</strong></a> を参照。
  </p>
</div>

<!-- ============ MOD-01 一目でわかる概要 ============ -->
<div class="bis-section">
<h2><span class="num">1</span>一目でわかる概要 — 2026 MaaS戦場データ</h2>

<div class="bis-grid">
  <div class="bis-card">
    <span class="val">150<span style="font-size:14px">億</span></span>
    <span class="lab">某大手動画クラウド2026年売上目標</span>
  </div>
  <div class="bis-card red">
    <span class="val">10×</span>
    <span class="lab">2026年目標 ÷ 2025年実績</span>
  </div>
  <div class="bis-card green">
    <span class="val">+83%</span>
    <span class="lab">Codingモデル Q1値上げ幅</span>
  </div>
  <div class="bis-card purple">
    <span class="val">+400%</span>
    <span class="lab">Codingモデル Q1利用量</span>
  </div>
  <div class="bis-card">
    <span class="val">10<span style="font-size:14px">億+</span></span>
    <span class="lab">某動画モデル月間収入</span>
  </div>
  <div class="bis-card red">
    <span class="val">~40%</span>
    <span class="lab">トークン月間成長率</span>
  </div>
</div>

<p><strong>コアシグナル</strong>：ある企業がモデル価格を<strong>83%値上げ</strong>しても、利用量が<strong>同時に400%成長</strong>したという事実は、「値上げしても利用量が減らない」ことがトップAIモデルで成立することを意味する。これは、「まず無料で囲い込み、後から値上げする」というインターネット時代のロジックとは完全に逆である。</p>
</div>

<!-- ============ MOD-02 動画モデル戦線 ============ -->
<div class="bis-section">
<h2><span class="num">2</span>戦線一：動画モデル — 某大手動画クラウド150億目標</h2>

<p>某大手動画クラウドは2026年4月、MaaS事業の売上目標を <strong>150億元</strong> に上方修正した。ほぼ毎月のように上方修正されている（2025年末の当初目標はわずか100億元）。</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>指標</th>
      <th>データ</th>
      <th>時点</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2025年通期 MaaS 実績収入</td>
      <td><strong>~15億元</strong></td>
      <td>2025年通期</td>
    </tr>
    <tr>
      <td>2026年 MaaS 売上目標</td>
      <td><strong>150億元</strong>（前年の10倍）</td>
      <td>2026年4月に上方修正</td>
    </tr>
    <tr>
      <td>2025年末の当初目標</td>
      <td>100億元</td>
      <td>2025年12月</td>
    </tr>
    <tr>
      <td>1日あたりのトークン消費量の月次成長率</td>
      <td><strong>~40%</strong></td>
      <td>2026年 現時点まで</td>
    </tr>
  </tbody>
</table>
</div>

<div class="bis-signal">
<h3>🎬 某動画モデル（コードネーム：モデル甲）の爆発的成長</h3>
<ul>
  <li><strong>月間収入が既に10億元を突破</strong>、現在も上昇中</li>
  <li>2026年2月10日に発表 → 春節期間中は10時間待ち → 「ホワイトリスト + 年間契約 + フルスペック版」の商用化を開始</li>
  <li>グローバル動画モデル市場シェア<strong>第2位</strong>（某海外大手に次ぐ）</li>
  <li>Artificial Analysis 動画アリーナ Elo 1269、海外トップクラスの動画モデルを超越</li>
  <li>ショートドラマ業界での普及率<strong>~95%</strong>（「ショートドラマ従事者でモデル甲のユーザーでないことは難しい」）</li>
  <li>2026年の目標：世界第1位</li>
</ul>
</div>

<!-- ============ MOD-02-Deep ショートドラマ経済の分析 ============ -->
<div class="bis-section" id="mod-02-deep">
<h2><span class="num">2.5</span>ショートドラマ経済の分析 — モデル甲の月商10億の真の源泉</h2>

<p>2026年6月3日の公開業界データによると：<strong>モデル甲の某大手動画クラウドにおける月商は既に10億元に達している</strong>（≈ARR 120億）。三大変数を考慮すると、<strong>保守的なARR試算は150億元超</strong>となる：</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>変数</th>
      <th>寄与</th>
      <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>基礎月商（某大手動画クラウドチャネル）</td>
      <td>10億元</td>
      <td>データ開示点</td>
    </tr>
    <tr>
      <td>上昇期による加重</td>
      <td>+20-30%</td>
      <td>ビジネス成長中</td>
    </tr>
    <tr>
      <td>サードパーティチャネル</td>
      <td>+15-20%</td>
      <td>一部ライセンス代理店経由</td>
    </tr>
    <tr>
      <td>海外未全面展開</td>
      <td>+30-50%</td>
      <td>海外正式リリース後の増加分</td>
    </tr>
    <tr>
      <td><strong>保守的ARR試算</strong></td>
      <td><strong>~150億元</strong></td>
      <td>中立的かつやや低め</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>横断比較：KlingのARRは34億</strong>（Kuaishouの公開開示）、モデル甲はその <strong>4.4倍</strong>。この差は以下に起因する：</p>

<ul>
  <li>ショートドラマシーンはほぼモデル甲が独占、<strong>95%の普及率</strong>は事実上の標準</li>
  <li>クリエイター向け（RED/ Douyin/ WeChat ChannelのC側）は、Jimeng（即夢）、XiaoYunQue（小云雀）などの「十分使えるモデル」がカバーし、<strong>クリエイターはAPI課金に全く触れない</strong></li>
  <li>APIを利用するのは<strong>ほぼすべてAIショートドラマ企業</strong>——バッチ処理、コストコントロール、5秒以上の動画クリップ生成が必要</li>
</ul>

<div class="bis-punchline">
<h2>💰 中国AIショートドラマ260億市場、モデル甲が約58%を獲得</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
  <strong>2026年の中国AIショートドラマの年間生産額は220～300億元（中央値260億元）</strong>。モデル甲のARR 150億 ÷ ショートドラマ生産額 260億 = <strong>~58%</strong>。これは、AIショートドラマの産業チェーンで稼がれる1元のうち、0.6元が直接モデル甲へのAPIトークン料として支払われることを意味する。<br><br>
  <strong>残りの0.4元</strong>は：脚本/絵コンテ/俳優差し替え/吹き替え/配信/広告出稿に使われるが、<strong>生成工程</strong>は既にモデル甲に<strong>事実上独占</strong>されている。
</p>
</div>

<p><strong>某大手動画クラウドの反応</strong>：</p>

<ul>
  <li><strong>2025年末</strong> MaaS売上目標：100億元</li>
  <li><strong>2026年4月</strong> 上方修正：<strong>150億元</strong>（前年実績15億の10倍）</li>
  <li>2025年実績：~15億元 → 2026年目標 150億元 = <strong>前年比10倍成長</strong></li>
  <li>コアドライバー：モデル甲のARR単体で150億の約100%を占める（他の動画モデルの合計貢献は小さい）</li>
</ul>

<div class="bis-quote">
「我々の見解：<strong>中国クラウドベンダーによるMaaS市場の戦争は、少なくとも今年は、既に早期決着している</strong>。」 —— 2026年6月3日 業界討論より
</div>

<p><strong>この見解の分析</strong>：</p>

<ul>
  <li>✅ <strong>成立する部分</strong>：<strong>単点動画モデル</strong>（動画生成コース）において、モデル甲は某大手動画クラウドチャネルで事実上無敵である</li>
  <li>⚠️ <strong>成立しない部分</strong>：<strong>MaaSプラットフォーム全体</strong>（マルチモーダル、APIオーケストレーション、業界ソリューション）においては、B社/C社は継続的に投資しており、2026年第3四半期に決着がつく見通し</li>
  <li>📊 <strong>より正確な表現</strong>：<strong>「単点モデル」（動画生成）の戦争は某大手動画クラウドチャネルで勝利したが、「MaaSプラットフォーム全体」の戦争は全く終わっていない</strong></li>
</ul>
</div>

<!-- ============ MOD-03 Codingモデル戦線 ============ -->
<div class="bis-section">
<h2><span class="num">3</span>戦線二：Codingモデル — 某スタートアップ、Q1に83%値上げ</h2>

<p>2026年第1四半期、<strong>某大手Codingスタートアップ（コードネーム：X社）</strong>のAPI利用価格は累計で約 <strong>83%</strong> 上昇したが、API利用量は<strong>依然として400%増加</strong>した。</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Coding戦場の主要データ（2026年Q1）</th>
      <th>数値</th>
      <th>意味</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>API利用価格の上昇幅</td>
      <td><strong>+83%</strong></td>
      <td>複数回の価格調整の累計</td>
    </tr>
    <tr>
      <td>API利用量の成長</td>
      <td><strong>+400%</strong></td>
      <td>価格上昇にもかかわらず利用量は減少せず</td>
    </tr>
    <tr>
      <td>キャッシュヒットトークン価格</td>
      <td>海外トップモデルAに接近</td>
      <td>国産初の中核的シーンでの価格面での同等化</td>
    </tr>
    <tr>
      <td>Coding能力</td>
      <td>国内トップレベル</td>
      <td>値上げの裏付けとなる実力</td>
    </tr>
  </tbody>
</table>
</div>

<div class="bis-punchline">
<h2>💡 「値上げしても利用量が減らない」はトップAIモデルで成立</h2>
<ul>
  <li>✅ 83%値上げと同時に、利用量は400%成長</li>
  <li>✅ これは国産大規模モデルが初めて<strong>中核的シーン</strong>で海外トップ企業と価格面で肩を並べた事例</li>
  <li>✅ 戦略的選択：2024年からAnthropic類似路線（モデルインテリジェンス＋Codingに特化）に賭ける</li>
  <li>✅ データソース：X社CEOが2026年Q1決算電話会議で開示</li>
</ul>
</div>
</div>

<!-- ============ MOD-04 某大手総合クラウドのMaaS組織強化 ============ -->
<div class="bis-section">
<h2><span class="num">4</span>某大手総合クラウドのMaaS組織強化</h2>

<p>2025年から、某大手総合クラウド（コードネーム：B社）は相次いで<strong>複数の新しいMaaSセールスチーム</strong>を立ち上げ、既存の直販チームと協力して案件を獲得している。</p>

<div class="bis-signal">
<h3>🏢 営業組織の三段階進化パス</h3>
<ul>
  <li><strong>フェーズ1：従来型クラウド営業</strong> — CPU/ストレージ/帯域リソースの販売</li>
  <li><strong>フェーズ2：MaaS営業</strong> — トークン/モデルAPIの販売（B社の現在地）</li>
  <li><strong>フェーズ3：Agent営業</strong> — 業務能力の販売/シーン別ソリューションの販売（将来の方向性）</li>
</ul>
</div>

<p><strong>MaaSセールスチームのコアタスク</strong>：</p>
<ul>
  <li>企業の利用シーンを開拓する</li>
  <li>企業顧客がAgent機能を使いこなせるように推進する</li>
  <li><strong>トークン消費量を増やす</strong>（これがKPI）</li>
</ul>
</div>

<!-- ============ MOD-05 競争環境 ============ -->
<div class="bis-section">
<h2><span class="num">5</span>競争環境 — Coding戦場でしのぎを削る三陣営</h2>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>陣営</th>
      <th>代表プレイヤー（匿名化）</th>
      <th>2026年の動き</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><span class="bis-tag-r">大手クラウドサービス</span></td>
      <td>A社（動画クラウド）、B社（総合クラウド）、C社（総合クラウド）</td>
      <td>Codingプランを発表、営業強化</td>
    </tr>
    <tr>
      <td><span class="bis-tag-m">AIスタートアップ</span></td>
      <td>X社（Codingトップ）、Y社、Z社</td>
      <td>Codingプラン＋モデル反復</td>
    </tr>
    <tr>
      <td><span class="bis-tag-n">通信キャリア陣営</span></td>
      <td>社名非公表</td>
      <td>相次いでCodingプランを発表</td>
    </tr>
  </tbody>
</table>
</div>

<p><strong>共通の戦法</strong>：まず比較的低価格でユーザーをビジネス圏内に引き込み → 大量のトークンを消費させる → 後期に値上げする。</p>

<div class="bis-quote">
「トークン大戦は、今や明確に二つの戦線に分かれている。一つはCoding（コード）モデル、そしてもう一つは動画モデルである。各社がモデルを底値まで叩き合う混雑したLLMモデルコースとは異なり、トップクラスのCodingと動画モデルは依然として一定の価格決定力、特に動画モデルはそれを保持している。」 —— 2026年 業界コンセンサス
</div>
</div>

<!-- ============ MOD-06 シンデレラのガラスの靴効果 ============ -->
<div class="bis-section">
<h2><span class="num">6</span>理論：「シンデレラのガラスの靴効果」</h2>

<p>2025年末、海外APIサービスプロバイダーのOpenRouterが一つの理論を提唱した：</p>

<div class="bis-punchline">
<h2>👠 シンデレラのガラスの靴効果</h2>
<p style="font-size:15.5px;line-height:1.7;margin:0">
<strong>AIモデルリリース後、最初の1ヶ月で流入したユーザーは、後続のユーザーよりも定着率が高い</strong>。なぜなら、ユーザーは効果の良いモデルを使うと、シンデレラがガラスの靴を履いた時のような<strong>極めて高いロイヤルティ</strong>を生み、ビジネスを<strong>そのモデルに深くロックイン</strong>するからである。
</p>
</div>

<p><strong>戦略的意味</strong>：</p>
<ul>
  <li>先行者利益＋初期ユーザー ＝ 長期的な堀</li>
  <li>大手が「まず低価格でユーザーを囲い込む」ことに積極的な理由を説明する</li>
  <li>Codingモデルが値上げしても利用量が減らない理由を説明する（ユーザーは既にロックインされている）</li>
  <li>某動画モデルがショートドラマ業界に95%浸透した後、事実上の標準となった理由を説明する</li>
</ul>

<!-- ============ MOD-06-Extreme ガラスの靴の極端な事例 ============ -->
<div class="bis-signal" id="mod-06-extreme">
<h3>👠 6.1 ガラスの靴の極端な事例 — モデル甲の150億ARR経済学</h3>
<p>ガラスの靴効果はモデル甲において<strong>極端な形態</strong>に達している——もはや「ユーザー粘着性が高い」ではなく、「ユーザーに<strong>選択肢がない</strong>」状態である：</p>

<ul>
  <li><strong>ショートドラマAPI利用の95%がモデル甲</strong>（「ショートドラマ従事者でモデル甲のユーザーでないことは難しい」）</li>
  <li>ライバルのKling ARR 34億 ＝ モデル甲の0.22倍、<strong>差は4.4倍</strong>であり、4.4%ではない</li>
  <li>ショートドラマ企業がモデルを切り替える際の限界費用は極めて高い：
    <ul>
      <li>プロンプトエンジニアリング/絵コンテ/キャラクターの一貫性に関するワークフローは、すべてモデル甲のAPIに合わせて再構築されている</li>
      <li>チームのプロンプトに関する知的資産はモデル甲に蓄積されている</li>
      <li>下流の配信チャネル（紅果、点众、九州）のコンテンツも、モデル甲による「質感」を評価している</li>
    </ul>
  </li>
  <li>したがって、<strong>モデル甲は単なる「値上げしても利用量減らず」ではなく、「値上げしても</strong>代替が効かない**」状態である</li>
</ul>

<p><strong>Codingモデルとの比較</strong>（値上げしても利用量減らず）：</p>

<ul>
  <li>Codingモデルには<strong>複数のトップ企業</strong>（X社＋Y社＋スタートアップZ社）が存在し、ユーザーは乗り換え可能</li>
  <li>モデル甲は動画生成コースで<strong>ほぼ一人勝ち</strong>状態であり、ユーザーの<strong>乗り換えコスト</strong>はCodingの比ではない</li>
  <li>結論：<strong>動画モデルの堀はCodingよりも深く</strong>、単点競争の終結時期はより早い</li>
</ul>

<p><strong>競合（Kling）への示唆</strong>：</p>

<ul>
  <li>❌ <strong>できない</strong>：価格競争でユーザーを奪うこと（モデル甲 ARR 150億 vs Kling 34億、<strong>価格競争＝自殺行為</strong>）</li>
  <li>✅ <strong>すべきこと</strong>：<strong>モデル甲がカバーしていない細分化シーン</strong>を切り開く：
    <ul>
      <li>超長尺動画（5分以上の連続ドラマ）</li>
      <li>3D/バーチャルヒューマン/デジタルツイン（ショートドラマ以外の産業シーン）</li>
      <li>海外華人/東南アジア市場（モデル甲の海外展開が未完了）</li>
    </ul>
  </li>
  <li>✅ <strong>すべきこと</strong>：<strong>オープンソース/オンプレミス</strong>路線を進む（モデル甲とのAPI正面競争を回避）</li>
</ul>
</div>
</div>

<!-- ============ MOD-07 一言まとめ + データの限界 ============ -->
<div class="bis-section">
<h2><span class="num">7</span>結論とデータの限界</h2>

<div class="bis-punchline">
<h2>🎯 一言まとめ（v2 改訂版）</h2>
<p style="font-size:16px;line-height:1.7;margin:0">
  <strong>2026年のMaaS戦場はCoding＋動画の二つの戦線に分裂した</strong>。トップ企業は83%値上げしながら利用量を400%増やせることは、トップAIモデルが<strong>「値上げしても利用量が減らない」</strong>堀を既に持つことを示す。動画モデルは95%の業界浸透により事実上の標準を形成し、<strong>ARRは150億</strong>、某大手動画クラウドのMaaS目標は150億に上方修正された。<strong>LLM汎用コースは底値で崩壊</strong>し、未来は最高クラスのモデル＋業界浸透に属する。<br><br>
  <strong>主な改訂点</strong>：動画生成コースにおいて、<strong>単点競争の勝敗は決した</strong>。モデル甲は某大手動画クラウドチャネルにおいて事実上無敵である。しかし、<strong>MaaSプラットフォーム全体</strong>（マルチモーダル/APIオーケストレーション/業界ソリューション）のレベルでは、B社/C社が依然として投資を続けており、<strong>真のプラットフォーム戦争は2026年第3四半期に決着する</strong>見通しである。
</p>
</div>

<div class="bis-signal">
<h3>📊 データの限界（必読）</h3>
<ul>
  <li>本稿の数字はすべて2026年6月3日時点の公開業界報道に基づき、クロスチェックは行われていない</li>
  <li>各社のMaaS収入の定義範囲は異なる可能性がある（各大手クラウド＋各Codingモデル企業がそれぞれ解釈）</li>
  <li>「単月10億超」「約95%浸透」などのデータはメディア報道によるもので、監査未了</li>
  <li>意思決定に引用する場合は、各社の財務報告書や業界白書と照合するなど、さらなる検証が推奨される</li>
  <li>企業名は公開ブログの匿名化ルールに従い伏せられ、モデルのコードネームと数字のみが残されている</li>
</ul>
</div>

<div class="bis-foot">
<p>データソース：2026年6月3日 業界メディア公開報道 · 執筆：Tech Observer</p>
</div>

</div>