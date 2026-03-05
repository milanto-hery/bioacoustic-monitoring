---
layout: page
title: Bioacoustic Monitoring Framework
---

<div align="center">
  <h1>🎙️ Bioacoustic Monitoring Framework</h1>
  <p><i>A High-End Interactive Documentation Hub for End-to-End Bioacoustic Analysis</i></p>

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.10">
    <img src="https://img.shields.io/badge/Platform-Raspberry%20Pi-C51A4A?style=for-the-badge&logo=raspberry-pi&logoColor=white" alt="Raspberry Pi">
    <img src="https://img.shields.io/badge/Tool-Sonic%20Visualiser-ff69b4?style=for-the-badge" alt="Sonic Visualiser">
    <img src="https://img.shields.io/badge/AI-Neural%20Network-success?style=for-the-badge" alt="Neural Network">
  </p>
</div>

---

## 👁️ System Vision

The Bioacoustic Monitoring Framework was built to streamline the complex processes spanning from rugged hardware deployment at the edge, precision manual labeling by bioacoustic experts, to advanced machine learning preprocessing utilizing Temporal-Frequency localization arrays.

This documentation serves as a central hub, cleanly separating the intricate engineering steps for every stage of the pipeline.

---

## 🗂️ Explore the Framework

<style>
  .dash-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }
  .dash-card {
    display: flex;
    flex-direction: column;
    text-decoration: none;
    color: inherit;
    background: #ffffff;
    border: 1px solid #eaecef;
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
  }
  .dash-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    border-color: #0366d6;
    color: inherit;
    text-decoration: none;
  }
  .dash-card h3 {
    margin-top: 0;
    margin-bottom: 10px;
    font-size: 1.25em;
    color: #24292e;
  }
  .dash-card p {
    margin: 0;
    color: #586069;
    font-size: 0.95em;
    line-height: 1.5;
  }
  @media (prefers-color-scheme: dark) {
    .dash-card {
      background: #1e1e1e;
      border-color: #333;
    }
    .dash-card h3 {
      color: #e1e4e8;
    }
    .dash-card p {
      color: #959da5;
    }
    .dash-card:hover {
      border-color: #79b8ff;
    }
  }
</style>

<div class="dash-grid">

  <a href="{{ site.baseurl }}/docs/architecture/" class="dash-card">
    <h3>🏗️ 1. Architecture</h3>
    <p>High-Level Mermaid Diagram explaining the interaction between Hardware, Data, and AI pipelines.</p>
  </a>

  <a href="{{ site.baseurl }}/docs/acquisition/" class="dash-card">
    <h3>📡 2. Data Acquisition</h3>
    <p>Details on Edge recording protocols, 10s Cron logic, and resilient Cloud syncing strategies.</p>
  </a>

  <a href="{{ site.baseurl }}/docs/labeling/" class="dash-card">
    <h3>🎧 3. Expert Labeling</h3>
    <p>The core methodology using Sonic Visualiser for sub-second, multi-frequency bounding boxes.</p>
  </a>

  <a href="{{ site.baseurl }}/docs/pipeline/" class="dash-card">
    <h3>🧠 4. Preprocessing & Training</h3>
    <p>How `.svl` XML is parsed and converted directly into machine-ingestible Mel-Spectrogram features.</p>
  </a>

</div>

---

## 🔗 External Repositories

For source code, setup instructions, and deployment scripts, please refer to the specific repositories:

* 📥 **Acquisition Repo:** [bioacoustic-edge-sync](https://github.com/milanto-hery/bioacoustic-edge-sync.git)
* ⚙️ **Pipeline Repo:** [bioacoustic-detection-pipeline](https://github.com/milanto-hery/bioacoustic-detection-pipeline.git)

---

<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto Hery</a> | © 2026</p>
</div>

<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true });
</script>
