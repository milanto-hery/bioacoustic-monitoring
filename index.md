---
layout: default
title: Bioacoustic Monitoring Framework
---

<div align="center">
  <h1>🎙️ Bioacoustic monitoring framework</h1>
  <p><i>A high-end interactive documentation hub for end-to-end bioacoustic analysis</i></p>

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.10">
    <img src="https://img.shields.io/badge/Platform-Raspberry%20Pi-C51A4A?style=for-the-badge&logo=raspberry-pi&logoColor=white" alt="Raspberry pi">
    <img src="https://img.shields.io/badge/Tool-Sonic%20Visualiser-ff69b4?style=for-the-badge" alt="Sonic visualiser">
    <img src="https://img.shields.io/badge/AI-Neural%20Network-success?style=for-the-badge" alt="Neural network">
  </p>
</div>

---

## 👁️ System vision

The bioacoustic monitoring framework was built to streamline the complex processes spanning from rugged hardware deployment at the edge, precision manual labeling by bioacoustic experts, to advanced machine learning preprocessing utilizing temporal-frequency localization arrays.

This documentation serves as a central hub, cleanly separating the intricate engineering steps for every stage of the pipeline.

---

## 🗂️ Explore the framework

<div class="dash-grid">

  <a href="{{ site.baseurl }}/docs/architecture/" class="dash-card">
    <h3>🏗️ 1. Architecture</h3>
    <p>High-level mermaid diagram explaining the interaction between hardware, data, and ai pipelines.</p>
  </a>

  <a href="{{ site.baseurl }}/docs/acquisition/" class="dash-card">
    <h3>📡 2. Data acquisition</h3>
    <p>Details on edge recording protocols, 10s cron logic, and resilient cloud syncing strategies.</p>
  </a>

  <a href="{{ site.baseurl }}/docs/labeling/" class="dash-card">
    <h3>🎧 3. Expert labeling</h3>
    <p>The core methodology using sonic visualiser for sub-second, multi-frequency bounding boxes.</p>
  </a>

  <a href="{{ site.baseurl }}/docs/pipeline/" class="dash-card">
    <h3>🧠 4. Preprocessing & training</h3>
    <p>How `.svl` xml is parsed and converted directly into machine-ingestible mel-spectrogram features.</p>
  </a>

</div>

---

## 🔗 External repositories

For source code, setup instructions, and deployment scripts, please refer to the specific repositories:

* 📥 **Acquisition repo:** [bioacoustic-edge-sync](https://github.com/milanto-hery.github.io/bioacoustic-edge-sync.git)
* ⚙️ **Pipeline repo:** [bioacoustic-detection-pipeline](https://github.com/milanto-hery.github.io/bioacoustic-detection-pipeline.git)

---

<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto hery</a> | © 2026</p>
</div>
