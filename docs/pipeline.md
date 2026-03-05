---
layout: default
title: Preprocessing & Training
parent: Home
nav_order: 4
permalink: /docs/pipeline/
---

<a href="{{ site.baseurl }}/" class="back-link">← Back to dashboard</a>

---

# 🧠 Preprocessing & training matrix

The fundamental innovation of the bioacoustic monitoring framework's ai pipeline lies in its ability to directly ingest complex xml structures. 

Instead of forcing annotators into rigid bounding-box `.csv` pipelines that strip away essential frequency logic, the preprocessing node parses the raw sonic visualiser output and transforms those geometries into pristine features for convolutional neural networks (cnns).

## Semantic xml parsing

The pipeline algorithm utilizes a specialized python function dedicated to cleanly reading `.svl` structure. 

### Why not standard `.csv` annotations?

Standard bioacoustic pipelines frequently flatten the data via csv files simply marking `start_time` and `end_time`. 

By contrast, the bioacoustic pipeline extracts four critical parameters from the complex xml:
1. `time` (Start in seconds)
2. `duration` (Total duration in seconds)
3. `lower_frequency` (Bottom boundary in hz)
4. `upper_frequency` (Top boundary in hz)

This ensures that the exact region of the acoustic anomaly—and *only* that region—is targeted by the deep learning engine. 

## The mel-spectrogram engine

Raw audio waveform arrays (.wav) contain massive amounts of noisy, redundant data, which is suboptimal for standard deep learning classification topologies. Therefore, the pipeline applies a rigorous feature extraction layer.

1. **Extraction logic**: After the python node parses the `.svl` boundary variables, the algorithm slices the corresponding `.wav` audio. 
2. **Frequency shift**: It converts those specific slices of 1d amplitude-time data into robust 2d **mel-spectrograms** corresponding exactly to the regions of interest (as well as defined background noise for hard-negative structural samples).

## Convolutional neural network (cnn)

These localized mel-spectrogram arrays (representing time x frequency bins) serve as the direct input features for the core model. 

By feeding the neural architecture these concentrated representations, the model learns the explicit temporal-frequency features of target acoustic events without wasting computational layers sifting through irrelevant background noise outside of the bounds labeled by the sonic visualiser experts. 

The implementation supports advanced optimization techniques such as adam optimization with learning rate decay, generating predictive evaluations measured via intersection-over-union (iou) on multi-dimensional bounding boxes.

---

<br>
 ↖️ Return to dashboard</a>

---
<div align="center">
  <p>Created by <a href="https://milanto-hery.github.io" target="_blank">Milanto hery</a> | © 2026</p>
  <p><small>📥 <a href="https://github.com/milanto-hery/bioacoustic-edge-sync.git">Acquisition repo</a> | ⚙️ <a href="https://github.com/milanto-hery/bioacoustic-detection-pipeline.git">Pipeline repo</a></small></p>
</div>
