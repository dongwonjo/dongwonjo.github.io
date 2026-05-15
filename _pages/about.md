---
permalink: /
title: null
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<p style="font-size: 1.5em; font-weight: bold; margin-bottom: 0.2em;">Dongwon Jo</p>

<p style="font-size: 0.85em; line-height: 1.6; margin-top: 15px;">
I am a Ph.D. student in Electrical & Computer Engineering at Seoul National University, advised by <a href="https://vlsi.snu.ac.kr/" target="_blank">Prof. Jae-Joon Kim</a>.
I received my B.S. in Electrical & Electronic Engineering from Yonsei University.
My research interests are summarized below.
</p>

<p style="font-size: 1.2em; font-weight: bold; margin-top: 15px; margin-bottom: 0.2em;">Research Interests</p>
<hr class="section-hr">

<p style="font-size: 0.85em; line-height: 1.6;">
My primary research aims to make model compression broadly applicable in real-world scenarios. A central theme of my work focuses on <strong>reducing the memory and compute costs of Deep Neural Networks (DNNs)</strong> that achieve superior accuracy through increased complexity, via <strong>algorithm–hardware co-design</strong>. Specifically, my research agenda includes:
</p>

<ul style="font-size: 0.85em; line-height: 1.6;">
  <li>Development of DNN accelerators</li>
  <li>Design of hardware-friendly DNNs (e.g., quantized or sparsified models)</li>
  <li>Model compression algorithms for efficient inference</li>
</ul>

<p style="font-size: 0.85em; line-height: 1.6;">
Currently, my research primarily targets <strong>generative models</strong>, including <strong>large language models (LLMs)</strong> and <strong>diffusion models</strong>, with a focus on practical efficiency and scalability. As these models are increasingly deployed in long-context settings, the associated memory and compute costs grow rapidly, creating fundamental barriers to real-world adoption. My work seeks to address these challenges through principled algorithm design, with the goal of making powerful generative models accessible under realistic resource constraints. Ongoing research topics include:
</p>

<ul style="font-size: 0.85em; line-height: 1.6;">
  <li>Quantization and pruning algorithms for LLMs and diffusion models</li>
  <li>KV cache compression and sparse attention for long-context LLM inference</li>
  <li>Kernel-level optimization for high-throughput generative models</li>
</ul>

<p style="font-size: 0.85em; line-height: 1.6;">
<strong>*Keywords:</strong> <em>Generative Models, Efficient Inference, Model Compression, Algorithm-Hardware Co-design</em>
</p>

<p style="font-size: 1.2em; font-weight: bold; margin-top: 30px; margin-bottom: 0.2em;">Selected Publications <a href="/publications/" style="font-size:0.8em; font-weight:normal; color:#52adc8;">[Full List]</a></p>
<hr class="section-hr">
<div class="selected-research">
  
  <div style="display:flex; gap:16px; margin-bottom:24px; align-items:flex-start; flex-wrap:wrap;">
    <div style="flex:0 0 min(200px, 30%); min-width:80px;">
      <img src="/images/paper/TokenSparseAttention.PNG" style="width:100%; height:120px; object-fit:contain; background-color:white; border:none; border-radius:4px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    </div>
    <div style="flex:1; min-width:0;">
      <p style="font-size:0.9em; font-weight:bold; margin:0 0 4px 0; line-height:1.4;">Token Sparse Attention: Efficient Long-Context Inference with Interleaved Token Selection</p>
      <p class="research-authors" style="font-size:0.8em; margin:0 0 4px 0;"><strong>Dongwon Jo</strong>, Beomseok Kang, Jiwon Song, Jae-Joon Kim</p>
      <p class="research-venue" style="font-size:0.8em; margin:0 0 8px 0;"><em>ICML 2026</em></p>   
      <a href="https://arxiv.org/abs/2602.03216" class="btn btn--primary btn--small">Paper</a>
      <a href="https://github.com/dongwonjo/Token-Sparse-Attention" class="btn btn--primary btn--small">Code</a>
      <a href="/portfolio/token_sparse_attention/" class="btn btn--primary btn--small">Project</a>
    </div>
  </div>

  <div style="display:flex; gap:16px; margin-bottom:24px; align-items:flex-start; flex-wrap:wrap;">
    <div style="flex:0 0 min(200px, 30%); min-width:80px;">
      <img src="/images/paper/FastKV.PNG" style="width:100%; height:120px; object-fit:contain; background-color:white; border:none; border-radius:4px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    </div>
    <div style="flex:1; min-width:0;">
      <p style="font-size:0.9em; font-weight:bold; margin:0 0 4px 0; line-height:1.4;">FastKV: Decoupling of Context Reduction and KV Cache Compression for Prefill-Decoding Acceleration</p>
      <p class="research-authors" style="font-size:0.8em; margin:0 0 4px 0;"><strong>Dongwon Jo*</strong>, Jiwon Song*, Yulhwa Kim, Jae-Joon Kim</p>
      <p class="research-venue" style="font-size:0.8em; margin:0 0 8px 0;"><em>ACL Findings 2026</em></p>
      <a href="https://arxiv.org/abs/2502.01068" class="btn btn--primary btn--small">Paper</a>
      <a href="https://github.com/dongwonjo/FastKV" class="btn btn--primary btn--small">Code</a>
    </div>
  </div>

  <div style="display:flex; gap:16px; margin-bottom:24px; align-items:flex-start; flex-wrap:wrap;">
    <div style="flex:0 0 min(200px, 30%); min-width:80px;">
      <img src="/images/paper/BinaryMoS.PNG" style="width:100%; height:120px; object-fit:contain; background-color:white; border:none; border-radius:4px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    </div>
    <div style="flex:1; min-width:0;">
      <p style="font-size:0.9em; font-weight:bold; margin:0 0 4px 0; line-height:1.4;">Mixture of Scales: Memory-Efficient Token-Adaptive Binarization for Large Language Models</p>
      <p class="research-authors" style="font-size:0.8em; margin:0 0 4px 0;"><strong>Dongwon Jo</strong>, Taesu Kim, Yulhwa Kim, Jae-Joon Kim</p>
      <p class="research-venue" style="font-size:0.8em; margin:0 0 8px 0;"><em>NeurIPS 2024</em></p>
      <a href="https://arxiv.org/abs/2406.12311" class="btn btn--primary btn--small">Paper</a>
      <a href="https://github.com/dongwonjo/BinaryMoS" class="btn btn--primary btn--small">Code</a>
    </div>
  </div>
</div>
<p style="font-size: 1.2em; font-weight: bold; margin-top: 30px; margin-bottom: 0.2em;">Education</p>
<hr class="section-hr">

<table style="width:100%; border:none; border-collapse:collapse;">
  <tr style="border:none;">
    <td style="border:none; padding: 4px 0;"><strong>Seoul National University</strong></td>
    <td style="border:none; padding: 4px 0; text-align:right;">Seoul, Korea</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0;">M.S./Ph.D. in Electrical &amp; Computer Engineering</td>
    <td style="border:none; padding: 2px 0; text-align:right;">Sep. 2022 – Present</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0 12px 0;" colspan="2">Advisor: Prof. Jae-Joon Kim</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 4px 0;"><strong>Yonsei University</strong></td>
    <td style="border:none; padding: 4px 0; text-align:right;">Seoul, Korea</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0;">B.S. in Electrical &amp; Electronic Engineering</td>
    <td style="border:none; padding: 2px 0; text-align:right;">Mar. 2016 – Aug. 2022</td>
  </tr>
</table>

<p style="font-size: 1.2em; font-weight: bold; margin-top: 30px; margin-bottom: 0.2em;">Work Experiences</p>
<hr class="section-hr">

<table style="width:100%; border:none; border-collapse:collapse;">
  <tr style="border:none;">
    <td style="border:none; padding: 4px 0;"><strong>SqueezeBits Inc.</strong></td>
    <td style="border:none; padding: 4px 0; text-align:right;">Seoul, Korea</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0;">Research Intern</td>
    <td style="border:none; padding: 2px 0; text-align:right;">Jun. 2022 – Jul. 2022</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0 12px 0;">External Collaborator</td>
    <td style="border:none; padding: 2px 0 12px 0; text-align:right;">Feb. 2023 – May. 2023</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 4px 0;"><strong>Seoul National University</strong></td>
    <td style="border:none; padding: 4px 0; text-align:right;">Seoul, Korea</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0;">Undergraduate Research Intern</td>
    <td style="border:none; padding: 2px 0; text-align:right;">Dec. 2021 – Jun. 2022</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0 12px 0;" colspan="2">with Prof. Jae-Joon Kim</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 4px 0;"><strong>Republic of Korea Air Force</strong></td>
    <td style="border:none; padding: 4px 0; text-align:right;">Seoul, Korea</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0 12px 0;">Sergeant (Military Service)</td>
    <td style="border:none; padding: 2px 0 12px 0; text-align:right;">Jan. 2018 – Dec. 2019</td>
  </tr>
</table>

<p style="font-size: 1.2em; font-weight: bold; margin-top: 30px; margin-bottom: 0.2em;">Academic Services</p>
<hr class="section-hr">

<table style="width:100%; border:none; border-collapse:collapse;">
  <tr>
    <td style="border:none; padding: 4px 0;"><strong>Conference Reviewer</strong></td>
    <td style="border:none; text-align:right;"></td>
  </tr>
  <tr>
    <td style="border:none; padding: 2px 0;" colspan="2">NeurIPS 2025, ICML 2026 (<stroing>Gold Reviewer</stroing>), NeurIPS 2026</td>
  </tr>
  <tr>
    <td style="border:none; padding: 12px 0 4px 0;"><strong>Journal Reviewer</strong></td>
    <td style="border:none; text-align:right;"></td>
  </tr>
  <tr>
    <td style="border:none; padding: 2px 0;" colspan="2">IEEE Transactions on Multimedia (TMM)</td>
  </tr>
</table>

<p style="font-size: 1.2em; font-weight: bold; margin-top: 30px; margin-bottom: 0.2em;">Teaching</p>
<hr class="section-hr">

<table style="width:100%; border:none; border-collapse:collapse;">
  <tr style="border:none;">
    <td style="border:none; padding: 4px 0;"><strong>Teaching Assistant</strong></td>
    <td style="border:none; padding: 4px 0; text-align:right;">Seoul National University</td>
  </tr>
  <tr style="border:none;">
    <td style="border:none; padding: 2px 0 12px 0;">430.201A 002: Digital Logic Design and Lab</td>
    <td style="border:none; padding: 2px 0 12px 0; text-align:right;">Sep. 2022 – Dec. 2022</td>
  </tr>
</table>
