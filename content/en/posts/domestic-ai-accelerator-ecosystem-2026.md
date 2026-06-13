---
title: "Practical observations on the domestic AI accelerator ecosystem: How many of the 6841 models run on the top domestic NPUs?"
date: 2026-06-02
draft: false
description: "A deep dive into China's 2026 domestic AI accelerator ecosystem, evaluating the maturity of the quantization stack, inference framework, and training framework across 6,841 open-source models, and illustrating TCO, quantization capability, and model coverage—the top concerns for overseas customers and deployers—in"
tags: ["Domestic AI chips", "AI accelerator", "Quantization", "Inference Framework", "MoE", "Model Ecosystem", "GitCode", "Open-source large model"]
slug: "domestic-ai-accelerator-ecosystem-2026"
cover:
  image: "https://images.unsplash.com/photo-1639762681485-074b7f938ba0?w=1200&q=80"
  alt: "AI Accelerators and Open-Source Model Ecosystem"
  caption: "Domestic AI accelerator: Ecosystem ready"
ShowToc: true
---

<link rel="stylesheet" href="/tech-blog/css/bis.css">

<div class="bis-wrap">

<div class="bis-hero">
  <span class="tag">Ecosystem Observation · 2026-06</span>
  <h1>Domestic AI Accelerator Ecosystem Real-World Observation</h1>
  <p class="subtitle">6,841 open-source models, 6 major task families, complete chain benchmarking NVIDIA ecosystem — full analysis of leading domestic NPU platform</p>
  <p class="date">2026-06-02 · Industry Observation</p>
</div>

<div class="bis-alert">
⚠️ <strong>Biggest Misconception</strong>: Domestic AI accelerators ≠ only run FP16. This article uses real download data + snapshots of 30 native models to prove that the entire INT4/INT8/rotation quantization/MTP optimization stack is complete, benchmarking against NVIDIA TensorRT-LLM. This is not a PPT; this is a fact running on GitCode.
</div>

<div class="bis-signal">
<h3>💡 Key Takeaways</h3>
<ul>
  <li><strong>6,841 models</strong> have already accumulated on the platform, with high head concentration (TOP 1 accounts for 29% of cumulative downloads of the first screen’s 30 models), star models have formed.</li>
  <li><strong>Full quantization stack</strong>: W4A8, W8A8, QuaRot, MTP, Flash/Turbo full coverage, directly benchmarking NVIDIA TensorRT-LLM ecosystem.</li>
  <li><strong>Inference framework compatibility</strong>: vLLM Ascend + SGLang Ascend have been adapted, existing PyTorch code runs with 0 changes.</li>
  <li><strong>6 major task families fully covered</strong>: general LLM, code LLM, multimodal VLM, speech ASR/TTS, vision/OCR, vertical industry.</li>
  <li><strong>Key direction in 2026 is industrial vision</strong>: PatchCore, WinCLIP, YOLOv10 released within three days, manufacturing/quality inspection are core target scenarios.</li>
</ul>
</div>

<!-- ============ MOD-01 生态规模 ============ -->
<div class="bis-section">
<h2><span class="num">1</span>Ecosystem Scale — An Underestimated Platform</h2>

<p>A leading domestic NPU vendor has accumulated <strong>6,841 models</strong> on a mainstream open-source model community (AtomGit community, filter ascendNative=true). We sampled the first screen’s 30 native/compatible models for analysis.</p>

<div class="bis-grid">
  <div class="bis-card">
    <span class="val">6,841</span>
    <span class="lab">Total Platform Models</span>
  </div>
  <div class="bis-card purple">
    <span class="val">5</span>
    <span class="lab">Model Families</span>
  </div>
  <div class="bis-card green">
    <span class="val">85K+</span>
    <span class="lab">Top 30 Cumulative Downloads</span>
  </div>
  <div class="bis-card red">
    <span class="val">24.6K</span>
    <span class="lab">TOP 1 Downloads</span>
  </div>
</div>

<p><strong>Concentration at the top</strong>: TOP 1 accounts for ~29% of cumulative downloads of the first screen’s 30 models, TOP 2 together ~48%. This means the ecosystem already has “star models” — customers don’t need to risk starting from scratch.</p>

<ul>
  <li>🥇 <strong>TOP 1</strong>: GLM-5-w4a8 — 32.6B MoE · W4A8 quantized · 24.6K downloads</li>
  <li>🥈 <strong>TOP 2</strong>: Qwen3.5-397B-A17B — 397B MoE · W8A8 + MTP · 16.3K downloads</li>
</ul>

<p class="bis-quote">Data timestamp: 2026-06-03 · Platform: AtomGit AI Community (domestic NPU model platform) · Filter ascendNative=true</p>
</div>

<!-- ============ MOD-02 量化栈 ============ -->
<div class="bis-section">
<h2><span class="num">2</span>Quantization Technology Stack — The Entire Inference Optimization Stack Is Ready</h2>

<p>This is the most common question from overseas customers: <strong>“Can domestic NPUs run quantized models?”</strong> The answer is yes — full coverage.</p>

<div class="bis-grid">
  <div class="bis-card">
    <span class="val" style="color:#2b5fff">W4A8</span>
    <span class="lab">4-bit weights + 8-bit activations<br>GLM-5-w4a8 · GLM-5.1-w4a8</span>
  </div>
  <div class="bis-card green">
    <span class="val" style="color:#1f9d6b">W8A8</span>
    <span class="lab">8-bit weights + activations<br>Qwen3.5-397B · a leading MoE</span>
  </div>
  <div class="bis-card purple">
    <span class="val" style="color:#7c3aed">QuaRot</span>
    <span class="lab">Rotation quantization<br>A leading MoE · Qwen3-Coder</span>
  </div>
  <div class="bis-card red">
    <span class="val" style="color:#e23b3b">MTP</span>
    <span class="lab">Multi-token prediction<br>Qwen3.5-397B · GLM-5-mtp</span>
  </div>
  <div class="bis-card">
    <span class="val" style="color:#e67e22">Flash</span>
    <span class="lab">Lightweight inference edition<br>glm-4.7-flash · z-image-turbo</span>
  </div>
  <div class="bis-card">
    <span class="val" style="color:#7c3aed">Rot</span>
    <span class="lab">Quantized RoPE-aware rotation<br>GLM-5-W8A8-Rot</span>
  </div>
</div>

<div class="bis-punchline">
<h2>📌 Sales Talking Points</h2>
<ul>
  <li>✅ <strong>W4A8 is ready</strong> — not “future support”, it’s a fact with 24.6K downloads on GitCode.</li>
  <li>✅ <strong>W8A8 is ready</strong> — 397B MoE + W8A8 + MTP triple combo, verified with 16.3K downloads.</li>
  <li>✅ <strong>QuaRot rotation quantization</strong> — used by a leading MoE and Qwen3-Coder.</li>
  <li>✅ <strong>MTP (multi-token prediction)</strong> — killer feature for high‑QPS serving scenarios.</li>
  <li>✅ <strong>Flash/Turbo lightweight editions</strong> — edge / cost-sensitive scenarios.</li>
</ul>
</div>
</div>

<!-- ============ MOD-03 推理框架 ============ -->
<div class="bis-section">
<h2><span class="num">3</span>Inference and Training Frameworks — 1:1 Benchmarking the NVIDIA Ecosystem</h2>

<p>This is the second most common question: <strong>“Does vLLM / SGLang run on domestic NPUs? Do I need to rewrite code?”</strong> — No rewriting needed.</p>

<div class="bis-timeline">
  <div class="bis-tl-item">
    <div class="tl-date">Inference Framework</div>
    <div class="tl-text"><strong>vLLM Ascend</strong> — main overseas inference framework, already adapted for Qwen3.5, GLM-4.7</div>
  </div>
  <div class="bis-tl-item">
    <div class="tl-date">Inference Framework</div>
    <div class="tl-text"><strong>SGLang Ascend</strong> — Qwen3-Next-80B-A3B already adapted (supported 8 months ago)</div>
  </div>
  <div class="bis-tl-item">
    <div class="tl-date">Inference Engine</div>
    <div class="tl-text"><strong>MindIE</strong> (vendor’s own inference engine) — used by Qwen-Image-series</div>
  </div>
  <div class="bis-tl-item">
    <div class="tl-date">Training Framework</div>
    <div class="tl-text"><strong>MindSpore-Lab</strong> (vendor’s own training) — Qwen3-8B has been run on MindSpore</div>
  </div>
  <div class="bis-tl-item">
    <div class="tl-date">Ecosystem Compatibility</div>
    <div class="tl-text"><strong>PyTorch-NPU</strong> — existing PyTorch code runs with zero changes on YOLOv5/v10, PatchCore, WinCLIP, rapidOCR</div>
  </div>
  <div class="bis-tl-item highlight">
    <div class="tl-date">Fine‑tuning / Alignment</div>
    <div class="tl-text"><strong>Ascend-SACT</strong> — fine‑tuning/alignment toolchain, already used by GLM-5 series</div>
  </div>
</div>

<p><strong>1:1 mapping to the NVIDIA ecosystem</strong>: from training (MindSpore / PyTorch-NPU) to inference (vLLM / SGLang / MindIE) to fine‑tuning (SACT), the whole toolchain is complete.</p>
</div>

<!-- ============ MOD-04 模型家族矩阵 ============ -->
<div class="bis-section">
<h2><span class="num">4</span>Model Family Matrix — 6 Major Task Families Fully Covered</h2>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Task Family</th>
      <th>Representative Models (Selection)</th>
      <th>Ecosystem Maturity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><span class="bis-tag-m">General LLM</span></td>
      <td>GLM-5 / 4.7 · Qwen3 / 3.5 · Gemma-4 · a 1B domestic on‑device model</td>
      <td>⭐⭐⭐⭐⭐</td>
    </tr>
    <tr>
      <td><span class="bis-tag-r">Code LLM</span></td>
      <td>Qwen3-Coder-480B-A35B (21.4B active + W8A8 + QuaRot)</td>
      <td>⭐⭐⭐⭐⭐</td>
    </tr>
    <tr>
      <td><span class="bis-tag-m">Multimodal VLM</span></td>
      <td>Qwen3.5 VLM · Qwen-Image · z-image · HunyuanWorld (3D)</td>
      <td>⭐⭐⭐⭐</td>
    </tr>
    <tr>
      <td><span class="bis-tag-n">Speech ASR / TTS</span></td>
      <td>Qwen3-ASR-1.7B · whisper-large-v3-turbo · Kokoro-82M TTS</td>
      <td>⭐⭐⭐⭐</td>
    </tr>
    <tr>
      <td><span class="bis-tag-n">Vision / OCR</span></td>
      <td>YOLOv5 / v10 · PatchCore · WinCLIP · rapidOCR · pix2struct-docvqa</td>
      <td>⭐⭐⭐⭐⭐</td>
    </tr>
    <tr>
      <td><span class="bis-tag-r">Vertical Industry</span></td>
      <td>PatchCore industrial anomaly detection · WinCLIP zero‑shot industrial vision</td>
      <td>⭐⭐⭐ (growing)</td>
    </tr>
  </tbody>
</table>
</div>

<div class="bis-signal">
<h3>🔍 Key Signal: Vertical Industry Models Are Accelerating</h3>
<ul>
  <li>PatchCore (industrial anomaly detection) — released 1 day ago</li>
  <li>WinCLIP (zero‑shot industrial vision) — released 3 days ago</li>
  <li>Multiple industrial vision models released within 3 days → manufacturing/logistics is the key direction in 2026</li>
</ul>
</div>
</div>

<!-- ============ MOD-05 客户场景映射 ============ -->
<div class="bis-section">
<h2><span class="num">5</span>Customer Scenario Mapping — One Picture Shows There Is a Ready‑Made Solution for Your Business</h2>

<p>This is the core of the sales tool — when a customer says “We want to do XX,” you can immediately map it to a concrete model on GitCode.</p>

<div class="bis-table-wrap">
<table class="bis-table">
  <thead>
    <tr>
      <th>Customer Business Scenario</th>
      <th>Recommended Model</th>
      <th>Why This One</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>LLM API Service</strong></td>
      <td>GLM-5-w4a8</td>
      <td>24.6K downloads, W4A8 quantization saves memory</td>
    </tr>
    <tr>
      <td><strong>Code Assistant / Copilot</strong></td>
      <td>Qwen3-Coder-480B-A35B-w8a8-QuaRot</td>
      <td>480B MoE 21.4B active + W8A8 + QuaRot triple optimization</td>
    </tr>
    <tr>
      <td><strong>RAG / Document Intelligence</strong></td>
      <td>pix2struct-docvqa · hunyuan-ocr · rapidOCR-npu</td>
      <td>OCR + document VQA trio</td>
    </tr>
    <tr>
      <td><strong>Multilingual ASR / TTS</strong></td>
      <td>Qwen3-ASR-1.7B + Kokoro-82M</td>
      <td>1.7B lightweight ASR + 82M on‑device TTS</td>
    </tr>
    <tr>
      <td><strong>Industrial Quality Inspection</strong></td>
      <td>PatchCore · YOLOv10-Ascend · WinCLIP</td>
      <td>Industrial vision trio, all released within 3 days</td>
    </tr>
    <tr>
      <td><strong>AIGC Marketing Content</strong></td>
      <td>Qwen-Image-series · z-image-turbo</td>
      <td>Image generation + on‑device turbo edition</td>
    </tr>
    <tr>
      <td><strong>Agent High QPS Platform</strong></td>
      <td>Qwen3.5-397B-A17B-w8a8-mtp</td>
      <td>397B MoE + W8A8 + MTP triple optimization</td>
    </tr>
    <tr>
      <td><strong>3D / World Model</strong></td>
      <td>HunyuanWorld-Mirror-Ascend</td>
      <td>3D world generation, already adapted</td>
    </tr>
  </tbody>
</table>
</div>
</div>

<!-- ============ MOD-06 客户故事信号 ============ -->
<div class="bis-section">
<h2><span class="num">6</span>Customer Story Signals — Industrial Vision Is the 2026 Focus</h2>

<p>By analyzing model release timestamps, we can infer the direction of ecosystem investment:</p>

<div class="bis-timeline">
  <div class="bis-tl-item highlight">
    <div class="tl-date">1 day ago</div>
    <div class="tl-text"><strong>PatchCore industrial anomaly detection</strong> released — clear move toward manufacturing/logistics/quality inspection</div>
  </div>
  <div class="bis-tl-item highlight">
    <div class="tl-date">3 days ago</div>
    <div class="tl-text"><strong>WinCLIP zero‑shot industrial vision</strong> released — zero‑shot means customers <strong>don’t need training data</strong>, ready to use out of the box</div>
  </div>
  <div class="bis-tl-item highlight">
    <div class="tl-date">3 days ago</div>
    <div class="tl-text"><strong>rapidOCR-npu</strong> released — OCR is a hard requirement in finance/government/legal scenarios</div>
  </div>
  <div class="bis-tl-item highlight">
    <div class="tl-date">3 days ago</div>
    <div class="tl-text"><strong>pix2struct-docvqa</strong> released — document intelligence, paired with rapidOCR</div>
  </div>
</div>

<div class="bis-signal">
<h3>💼 Insights for Sales/Pre-Sales</h3>
<ul>
  <li><strong>Industrial Vision Trio</strong> (PatchCore + WinCLIP + YOLOv10) has been released together — manufacturing/logistics industries can be targeted proactively.</li>
  <li><strong>OCR + Document VQA</strong> (rapidOCR + pix2struct + hunyuan-ocr) trio — ready for government/enterprise/finance/legal scenarios.</li>
  <li><strong>Zero‑shot models</strong> (WinCLIP) suit customers without training data — lower deployment barrier.</li>
</ul>
</div>
</div>

<!-- ============ MOD-07 一句话总结 + 下一步 ============ -->
<div class="bis-section">
<h2><span class="num">7</span>Conclusion and Next Steps</h2>

<div class="bis-punchline">
<h2>🎯 One Sentence for Overseas Customers</h2>
<p style="font-size:16px;line-height:1.7;margin:0">
<strong>Domestic AI accelerators are not a “downgraded alternative” to NVIDIA — they are already a mature ecosystem with a complete quantization stack, vLLM/SGLang compatibility, and 6,841 accumulated models.</strong> For customers needing long‑term TCO optimization and avoiding single‑supply risk, 2026 is a window for serious evaluation.
</p>
</div>

<p><strong>Next Steps for Deployers</strong>:</p>
<ul>
  <li>✅ Try: Go to the AtomGit AI Community ascendNative=true filter page to see models directly.</li>
  <li>✅ Evaluate: Start PoC from the customer’s most painful scenario (usually LLM API / OCR / industrial quality inspection).</li>
  <li>✅ Compare: Run the same model on domestic NPU vs. NVIDIA using vLLM / SGLang, compare TCO.</li>
  <li>✅ Migrate: PyTorch code requires 0 changes; CUDA code migrates via the torch_npu adapter.</li>
</ul>

<p class="bis-quote">Drop-in replacement for CUDA stack — already a community consensus, not a PPT slogan.</p>
</div>

<div class="bis-foot">
<p>This article is a public industry observation; all data comes from the AtomGit AI Community (ai.gitcode.com) public filter page ascendNative=true.</p>
<p>Data timestamp: 2026-06-03 · Written by: Tech Observer.</p>
</div>

</div>
