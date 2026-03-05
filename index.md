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

<div style="display: flex; gap: 20px; flex-wrap: wrap; justify-content: space-between;">

  <a href="docs/architecture.html" style="text-decoration: none; color: inherit; flex: 1 1 45%; border: 1px solid #ccc; padding: 15px; border-radius: 8px; box-shadow: 2px 2px 10px rgba(0,0,0,0.1);">
    <h3>🏗️ 1. Architecture</h3>
    <p>High-Level Mermaid Diagram explaining the interaction between Hardware, Data, and AI pipelines.</p>
  </a>

  <a href="docs/acquisition.html" style="text-decoration: none; color: inherit; flex: 1 1 45%; border: 1px solid #ccc; padding: 15px; border-radius: 8px; box-shadow: 2px 2px 10px rgba(0,0,0,0.1);">
    <h3>📡 2. Data Acquisition</h3>
    <p>Details on Edge recording protocols, 10s Cron logic, and resilient Cloud syncing strategies.</p>
  </a>

  <a href="docs/labeling.html" style="text-decoration: none; color: inherit; flex: 1 1 45%; border: 1px solid #ccc; padding: 15px; border-radius: 8px; box-shadow: 2px 2px 10px rgba(0,0,0,0.1);">
    <h3>🎧 3. Expert Labeling</h3>
    <p>The core methodology using Sonic Visualiser for sub-second, multi-frequency bounding boxes.</p>
  </a>

  <a href="docs/pipeline.html" style="text-decoration: none; color: inherit; flex: 1 1 45%; border: 1px solid #ccc; padding: 15px; border-radius: 8px; box-shadow: 2px 2px 10px rgba(0,0,0,0.1);">
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