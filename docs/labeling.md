---
layout: page
title: Expert Labeling
parent: Home
nav_order: 3
---

<a href="../index.html">← Back to Dashboard</a>

---

# 🎧 Expert Labeling (The Showcase)

The integrity of any supervised machine learning architecture inherently relies on the absolute precision of its ground truth data. A structured approach to annotating the bioacoustic data is crucial for training a high-performance computer vision / AI model to parse spectrograms. 

We exclusively utilize **Sonic Visualiser** for precise, expert-level labeling. This enables robust metadata generation that transcends simple time-stamping by explicitly delineating frequency bandwidths.

## The Granular Methodology

A strict labeling protocol must be maintained across all global annotators. Here are the exact standard operating procedures to execute precision labeling:

### Step 1: Spectrogram Tuning (FFT Settings)

1. **Import Audio:** Open the 10-second `.wav` files downloaded via our cloud sync architecture from Google Drive directly into Sonic Visualiser.
2. **Add Spectrogram:** Navigate to `Pane > Add Spectrogram` or execute `Shift + G`. 
3. **Configure FFT Constants:** Customize the settings (color scale, window size) to emphasize the target frequency ranges of the specific fauna. We standardize on a Window size of `1024` or `2048` and an overlap of `50%` for optimal temporal and frequency resolution.

> *[Screenshot Placeholder: Spectrogram Settings]*

### Step 2: Region Layer Creation

Standard point timestamps are insufficient for robust model training. We require explicit bounding boxes.

1. **Initialize Layer:** Navigate to `Layer > Add New Time-Value Layer` to unlock the necessary annotation geometry.

### Step 3: Precise Time-Frequency Boxing

This is the core of the labeling showcase. Analysts must encompass the entire acoustic signal without capturing excessive background noise, as that would dilute the target feature space during Mel-Spectrogram generation.

1. **Execute Annotations:** Click and drag to draw boxes mapping the exact *frequency boundaries* (Y-axis) and *time durations* (X-axis) of the target acoustic events. Be sure to label both positive calls and distinct hard-negative background noises when instructed.

> *[Screenshot Placeholder: Frequency-Time Boxes]*

### Step 4: SVL Export 

Why `.svl` over simple `.csv`? The Sonic Visualiser XML (`.svl`) inherently maintains the complex structural relationship of our 2D region layers, avoiding the data flattening and parsing errors associated with standard CSV conversions.

1. **Finalize Export:** Export the annotation layer as an `.svl` file. It is a critical strict requirement that the `.svl` filename matches the source audio `.wav` file exactly.

---

<br>
<a href="pipeline.html">➡️ Next: Preprocessing & Training Pipeline</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto Hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition Repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline Repo</a></small></p>
</div>