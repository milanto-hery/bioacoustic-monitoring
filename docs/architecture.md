---
layout: page
title: Architecture
parent: Home
nav_order: 1
permalink: /docs/architecture/
---

<a href="{{ site.baseurl }}/">← Back to Dashboard</a>

---

# 🏗️ System Architecture

The overarching system architecture dictates the flow of raw acoustic signals from edge hardware, through resilient remote storage, and ultimately into the advanced Neural Network framework.

```mermaid
graph TD
    classDef hardware fill:#ffad66,stroke:#e67e22,stroke-width:2px,color:#000
    classDef data fill:#66b3ff,stroke:#2980b9,stroke-width:2px,color:#000
    classDef ai fill:#85e085,stroke:#27ae60,stroke-width:2px,color:#000

    A[Raspberry Pi Mic]:::hardware -->|Cron Job 10s Recording| B(Local Storage):::hardware
    B -->|rclone Sync| C[(Google Drive)]:::data
    C -->|Fetch Data| D[Sonic Visualiser Labeling]:::data
    D -->|.svl XML Annotations| E[Data Preprocessing]:::ai
    E -->|Mel-Spectrogram Generation| F[Neural Net Pipeline]:::ai
    F -->|Inference & Detect| G((Acoustic Events)):::ai
```

<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true });
</script>

### Flow Breakdown

1. **Hardware Tier (Orange):** Represents the robust, remote data collection. The Raspberry Pi system is programmed to constantly ingest acoustics without human intervention.
2. **Data Tier (Blue):** Involves the secure transmission and structured labeling of that data. Google Drive acts as the remote bridge between the physical jungle and the data scientists' desks. Sonic Visualiser enables expert manual verification.
3. **AI Tier (Green):** The automated engine. Preprocessing pipelines convert human-readable `.svl` annotations into machine-readable Mel-Spectrogram features, feeding them directly into Convolutional Neural Networks for acoustic event detection.

---

<br>
<a href="{{ site.baseurl }}/docs/acquisition/">➡️ Next: Data Acquisition</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto Hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition Repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline Repo</a></small></p>
</div>
