---
layout: default
title: Data Acquisition
parent: Home
nav_order: 2
permalink: /docs/acquisition/
---

<a href="{{ site.baseurl }}/" class="back-link">← Back to dashboard

---

# 📡 Data acquisition

The data acquisition process stands as the foundation of the bioacoustic monitoring framework. Operating on the extreme edge requires resilient, autonomous systems that can record and sync high-fidelity audio continuously without human intervention or failure modes.

<details open>
  <summary><b>🛠 Technical hardware specs (Raspberry pi setup)</b></summary>
  <br>
  <ul>
    <li><b>Board:</b> Raspberry pi (Model 3B+ or 4 recommended for minimal power draw vs. necessary compute power)</li>
    <li><b>Microphone:</b> High-fidelity usb or i2s generic bioacoustic mic</li>
    <li><b>Os:</b> Raspberry pi os lite (Debian-based, headless to save resources)</li>
    <li><b>Dependencies:</b> <code>arecord</code>, <code>sox</code>, <code>rclone</code>, <code>cron</code></li>
    <li><b>Power:</b> 5V / 3A reliable power supply (battery pack + solar panel for remote edge deployment)</li>
  </ul>
</details>

## 🕒 The cron-job logic: 10-second bursts

### Why 10-second bursts?

Instead of recording a continuous hours-long `.wav` file, the edge node relies on a heavily optimized bash script orchestrated by linux `cron`. This strategy guarantees **10-second audio bursts**. 

This engineering choice is critical for several reasons:

1. **Avoids total data loss:** In a harsh jungle environment with unstable power, if the raspberry pi loses power unexpectedly, a continuous recording script would result in a massive corrupted file representing an entire day's lost work. With 10-second bursts, the maximum data loss is only 10 seconds.
2. **Computational load & storage allocation:** Smaller files are instantly written to the local sd storage with a minimal memory footprint.
3. **Analyst workflow compatibility:** Expert annotators cannot efficiently navigate a 12-hour audio file in sonic visualiser. Discrete 10-second chunks allow global teams to distribute the workload cleanly and assign granular analysis files to each expert.

## ☁️ Continuous sync architecture

The edge node possesses limited onboard storage, making an automated offloading procedure mandatory.

* **Technology:** The framework leverages `rclone`, effectively mapping remote cloud directories to the physical device.
* **Mechanism:** Upon the completion of an audio burst collection, a concurrent background process verifies local disk space and executes a secure pipeline straight to **Google drive** (`rclone copy /local GoogleDrive:/Bioacoustics`).
* **Resilience:** This procedure ensures that analytical teams working in major research centers have immediate access to acoustic data captured just moments before in disparate rainforests around the globe.

---

<br>
<a href="{{ site.baseurl }}/" class="back-link">← Previous</a>
<a href="{{ site.baseurl }}/docs/labeling/" class="next-link">Next →</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline repo</a></small></p>
</div>
