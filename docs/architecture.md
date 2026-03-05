---
layout: default
title: Architecture
parent: Home
nav_order: 1
permalink: /docs/architecture/
---

<a href="{{ site.baseurl }}/" class="back-link">← Back to dashboard</a>

---

# 🏗️ System architecture

The overarching system architecture dictates the flow of raw acoustic signals from edge hardware, through resilient remote storage, and ultimately into the advanced neural network framework.

<div class="mermaid">
graph TD
    classDef hardware fill:#ffad66,stroke:#e67e22,stroke-width:2px,color:#000
    classDef data fill:#66b3ff,stroke:#2980b9,stroke-width:2px,color:#000
    classDef ai fill:#85e085,stroke:#27ae60,stroke-width:2px,color:#000

    A[Raspberry pi mic]:::hardware -->|Cron job 10s recording| B(Local storage):::hardware
    B -->|rclone Sync| C[(Google drive)]:::data
    C -->|Fetch data| D[Sonic visualiser labeling]:::data
    D -->|.svl xml annotations| E[Data preprocessing]:::ai
    E -->|Mel-spectrogram generation| F[Neural net pipeline]:::ai
    F -->|Inference & detect| G((Acoustic events)):::ai
</div>


### Flow breakdown

1. **Hardware tier (Orange):** Represents the robust, remote data collection. The raspberry pi system is programmed to constantly ingest acoustics without human intervention.
2. **Data tier (Blue):** Involves the secure transmission and structured labeling of that data. Google drive acts as the remote bridge between the physical jungle and the data scientists' desks. Sonic visualiser enables expert manual verification.
3. **Ai tier (Green):** The automated engine. Preprocessing pipelines convert human-readable `.svl` annotations into machine-readable mel-spectrogram features, feeding them directly into convolutional neural networks for acoustic event detection.

---

<br>
<a href="{{ site.baseurl }}/docs/acquisition/">➡️ class="next-link">Next: Data acquisition</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline repo</a></small></p>
</div>
