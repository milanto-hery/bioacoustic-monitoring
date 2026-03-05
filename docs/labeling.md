---
layout: default
title: Expert Labeling
parent: Home
nav_order: 3
permalink: /docs/labeling/
---

<a href="{{ site.baseurl }}/" class="back-link">← Back to dashboard

---

# 🎧 Expert labeling (the showcase)

The integrity of any supervised machine learning architecture inherently relies on the absolute precision of its ground truth data. A structured approach to annotating the bioacoustic data is crucial for training a high-performance computer vision / ai model to parse spectrograms. 

We exclusively utilize **Sonic visualiser** for precise, expert-level labeling. This enables robust metadata generation that transcends simple time-stamping by explicitly delineating frequency bandwidths.

## The granular methodology

A strict labeling protocol must be maintained across all global annotators. Here are the exact standard operating procedures to execute precision labeling:

### Step 1: Spectrogram tuning (Fft settings)

1. **Import audio:** Open the 10-second `.wav` files downloaded via our cloud sync architecture from google drive directly into sonic visualiser.
2. **Add spectrogram:** Navigate to `Pane > Add Spectrogram` or execute `Shift + G`. 
3. **Configure fft constants:** Customize the settings (color scale, window size) to emphasize the target frequency ranges of the specific fauna. We standardize on a window size of `1024` or `2048` and an overlap of `50%` for optimal temporal and frequency resolution.

![Spectrogram settings]({{ site.baseurl }}/assets/spectrogram-setup.png)

### Step 2: Region layer creation

Standard point timestamps are insufficient for robust model training. We require explicit bounding boxes.

**Initialize layer:** Navigate to `Layer > Add New Time-Value Layer` to unlock the necessary annotation geometry.

### Step 3: Precise time-frequency boxing

This is the core of the labeling showcase. Analysts must encompass the entire acoustic signal without capturing excessive background noise, as that would dilute the target feature space during mel-spectrogram generation.

**Execute annotations:** Click and drag to draw boxes mapping the exact *frequency boundaries* (Y-axis) and *time durations* (X-axis) of the target acoustic events. Be sure to label both positive calls and distinct hard-negative background noises when instructed.

![Frequency-time boxes]({{ site.baseurl }}/assets/labelling-boxes.png)

### Step 4: Svl export 

Why `.svl` over simple `.csv`? The sonic visualiser xml (`.svl`) inherently maintains the complex structural relationship of our 2d region layers, avoiding the data flattening and parsing errors associated with standard csv conversions.

**Finalize export:** Export the annotation layer as an `.svl` file. It is a critical strict requirement that the `.svl` filename matches the source audio `.wav` file exactly.

---

<br>
<a href="{{ site.baseurl }}/docs/acquisition/" class="back-link">← Previous</a>
<a href="{{ site.baseurl }}/docs/pipeline/" class="next-link">Next →</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline repo</a></small></p>
</div>
