---
layout: page
title: Preprocessing & Training
parent: Home
nav_order: 4
permalink: /pipeline/
---

<a href="{{ site.baseurl }}/">← Back to Dashboard</a>

---

# 🧠 Preprocessing & Training Matrix

The fundamental innovation of the Bioacoustic Monitoring Framework's AI Pipeline lies in its ability to directly ingest complex XML structures. 

Instead of forcing annotators into rigid bounding-box `.csv` pipelines that strip away essential frequency logic, the Preprocessing Node parses the raw Sonic Visualiser output and transforms those geometries into pristine features for Convolutional Neural Networks (CNNs).

## Semantic XML Parsing

The pipeline algorithm utilizes a specialized Python function dedicated to cleanly reading `.svl` structure. 

### Why not standard `.csv` annotations?

Standard bioacoustic pipelines frequently flatten the data via CSV files simply marking `start_time` and `end_time`. 

By contrast, the Bioacoustic pipeline extracts four critical parameters from the complex XML:
1. `time` (Start in seconds)
2. `duration` (Total duration in seconds)
3. `lower_frequency` (Bottom boundary in Hz)
4. `upper_frequency` (Top boundary in Hz)

This ensures that the exact region of the acoustic anomaly—and *only* that region—is targeted by the deep learning engine. 

## The Mel-Spectrogram Engine

Raw audio waveform arrays (.wav) contain massive amounts of noisy, redundant data, which is suboptimal for standard Deep Learning classification topologies. Therefore, the pipeline applies a rigorous feature extraction layer.

1. **Extraction Logic**: After the Python node parses the `.svl` boundary variables, the algorithm slices the corresponding `.wav` audio. 
2. **Frequency Shift**: It converts those specific slices of 1D amplitude-time data into robust 2D **Mel-Spectrograms** corresponding exactly to the regions of interest (as well as defined background noise for hard-negative structural samples).

## Convolutional Neural Network (CNN)

These localized Mel-Spectrogram arrays (representing Time x Frequency bins) serve as the direct input features for the core model. 

By feeding the Neural Architecture these concentrated representations, the model learns the explicit temporal-frequency features of target acoustic events without wasting computational layers sifting through irrelevant background noise outside of the bounds labeled by the Sonic Visualiser experts. 

The implementation supports advanced optimization techniques such as Adam optimization with learning rate decay, generating predictive evaluations measured via intersection-over-union (IoU) on multi-dimensional bounding boxes.

---

<br>
<a href="{{ site.baseurl }}/">↖️ Return to Dashboard</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto Hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition Repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline Repo</a></small></p>
</div>