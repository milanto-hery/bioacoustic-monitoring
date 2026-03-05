---
layout: page
title: Data Acquisition
parent: Home
nav_order: 2
permalink: /acquisition/
---

<a href="{{ site.baseurl }}/">← Back to Dashboard</a>

---

# 📡 Data Acquisition

The data acquisition process stands as the foundation of the Bioacoustic Monitoring Framework. Operating on the extreme edge requires resilient, autonomous systems that can record and sync high-fidelity audio continuously without human intervention or failure modes.

<details open>
  <summary><b>🛠 Technical Hardware Specs (Raspberry Pi Setup)</b></summary>
  <br>
  <ul>
    <li><b>Board:</b> Raspberry Pi (Model 3B+ or 4 recommended for minimal power draw vs. necessary compute power)</li>
    <li><b>Microphone:</b> High-fidelity USB or I2S generic bioacoustic mic</li>
    <li><b>OS:</b> Raspberry Pi OS Lite (Debian-based, Headless to save resources)</li>
    <li><b>Dependencies:</b> <code>arecord</code>, <code>sox</code>, <code>rclone</code>, <code>cron</code></li>
    <li><b>Power:</b> 5V / 3A reliable power supply (battery pack + solar panel for remote edge deployment)</li>
  </ul>
</details>

## 🕒 The Cron-Job Logic: 10-Second Bursts

### Why 10-Second Bursts?

Instead of recording a continuous hours-long `.wav` file, the edge node relies on a heavily optimized bash script orchestrated by Linux `cron`. This strategy guarantees **10-second audio bursts**. 

This engineering choice is critical for several reasons:

1. **Avoids Total Data Loss:** In a harsh jungle environment with unstable power, if the Raspberry Pi loses power unexpectedly, a continuous recording script would result in a massive corrupted file representing an entire day's lost work. With 10-second bursts, the maximum data loss is only 10 seconds.
2. **Computational Load & Storage Allocation:** Smaller files are instantly written to the local SD storage with a minimal memory footprint.
3. **Analyst Workflow Compatibility:** Expert annotators cannot efficiently navigate a 12-hour audio file in Sonic Visualiser. Discrete 10-second chunks allow global teams to distribute the workload cleanly and assign granular analysis files to each expert.

## ☁️ Continuous Sync Architecture

The edge node possesses limited onboard storage, making an automated offloading procedure mandatory.

* **Technology:** The framework leverages `rclone`, effectively mapping remote cloud directories to the physical device.
* **Mechanism:** Upon the completion of an audio burst collection, a concurrent background process verifies local disk space and executes a secure pipeline straight to **Google Drive** (`rclone copy /local GoogleDrive:/Bioacoustics`).
* **Resilience:** This procedure ensures that analytical teams working in major research centers have immediate access to acoustic data captured just moments before in disparate rainforests around the globe.

---

<br>
<a href="{{ site.baseurl }}/labeling/">➡️ Next: Expert Labeling</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto Hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition Repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline Repo</a></small></p>
</div>