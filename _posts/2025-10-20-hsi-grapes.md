---
layout: post
title: "In-Field Grape Quality Mapping with Illumination-Invariant AI"
date: 2025-10-20 09:00:00
description: "Our new robotic system uses domain-adversarial learning to overcome changing sunlight, enabling robust, real-time mapping of grape yield, sugar, and acidity."
tags: hyperspectral-imaging precision-agriculture deep-learning computer-vision robotics
categories: research
thumbnail: assets/img/blog/2025-10-20-hsi-grapes/exampleScan.png
giscus_comments: true
related_posts: true
toc:
  sidebar: left
---

Hyperspectral imaging is a powerful tool for seeing the invisible qualities of crops, like the sugar content in grapes. But taking this technology from the controlled lab to a real-world vineyard has one massive obstacle: the sun. A model trained on a sunny morning fails on a cloudy afternoon because the changing light completely alters the data.

Our latest paper introduces an end-to-end robotic system that tackles this problem. At its core is a novel deep learning framework called the **Light-Invariant Spectral Autoencoder (LISA)**, which learns to see a grape's intrinsic properties, regardless of the lighting conditions.

This post explains the core challenge, how our adversarial AI works, and how we integrated it into a field robot that generates real-time, high-resolution maps of grape yield and quality.

We're thrilled to announce our paper has been accepted to the IEEE Internet of Things Journal in a special issue on Intelligent IoT for Sustainable Agriculture! You can [read the full preprint on arXiv](https://arxiv.org/abs/2510.04864) or access the [published version](https://doi.org/10.1109/JIOT.2025.3617805).

---

## The Problem: Sunlight is a Domain Shift

Hyperspectral sensors are extremely sensitive. The same grape bunch will produce dramatically different spectral data depending on the time of day, cloud cover, and shadows. This "domain shift" is the primary reason why HSI systems have struggled to move from the lab to reliable field autonomy.

First, let's look at the visual difference. We created a unique dataset by imaging the exact same grape bunches under three distinct lighting conditions. The change is not subtle.

{% include figure.liquid loading="eager" path="assets/img/blog/2025-10-20-hsi-grapes/dataSetICCV.png" class="img-fluid rounded z-depth-1" zoomable=true %}
<div class="caption">
    The visual appearance of a single grape bunch changes dramatically across our three domains. From left to right: controlled lab lighting, natural morning sun, and natural afternoon sun.
</div>

This isn't just a cosmetic effect; it represents a fundamental shift in the data the sensor captures. A standard AI model sees these as three completely different objects. The graph of their spectral signatures makes this problem crystal clear.

{% include figure.liquid loading="eager" path="assets/img/blog/2025-10-20-hsi-grapes/spectralsignatures.png" class="img-fluid rounded z-depth-1" zoomable=true %}
<div class="caption">
    The plot of the raw spectral data confirms the challenge. Both the intensity and shape of the signature change with illumination, creating a "domain shift" that confuses conventional models and makes robust prediction impossible without a specialized solution.
</div>

The traditional fix is frequent, manual calibration using a white reference panel. For a robot designed for continuous, autonomous operation, this stop-and-go process is impractical and defeats the purpose of automation. We needed a data-driven solution.

---

## Our Solution: Learning to Ignore the Sun with LISA

Instead of relying on physical calibration, we designed an AI model that learns illumination-invariance directly from the data. LISA is a **domain-adversarial autoencoder**. Here's the concept in simple terms:

1.  **A Feature Extractor:** This is the main part of the model. Its job is to look at the raw hyperspectral data and extract a compact, meaningful representation (a latent vector).
2.  **Two Competing Goals:** We give this extractor two jobs.
    *   **Task Predictor:** Tries to predict the grape's quality (Brix and Acidity) from the features. This forces the features to be useful.
    *   **Domain Discriminator:** Tries to guess the lighting condition (e.g., "Lab" vs. "Field") from the same features.

During training, we reward the Feature Extractor for helping the Task Predictor succeed while simultaneously "fooling" the Domain Discriminator. This adversarial process forces the model to learn a representation that is highly predictive of grape quality but contains no information about the illumination. It learns the grape's true signature.

{% include figure.liquid loading="eager" path="assets/img/blog/2025-10-20-hsi-grapes/AE.png" class="img-fluid rounded z-depth-1" zoomable=true %}
<div class="caption">
    The architecture of our Light-Invariant Spectral Autoencoder (LISA). The adversarial process between the Task Predictor and Domain Discriminator forces the shared features (z) to become illumination-invariant.
</div>

---

## An End-to-End System for Yield and Quality

LISA is the core of our complete, IoT-enabled robotic system. The platform integrates two key analytical modules that run in real-time on the robot's edge computer:

1.  **Yield Estimation:** A YOLOv11 model detects grape bunches, and a 2D CNN regression model estimates their weight from the hyperspectral data.
2.  **Quality Assessment:** Our LISA framework analyzes the pixels within each detected bunch to predict the average Brix and Acidity.

All predictions are fused with GPS data to create georeferenced data points. As the robot moves through the vineyard, it streams this information, building a detailed, spatially-resolved map of both crop quantity and quality.

{% include figure.liquid loading="eager" path="assets/img/blog/2025-10-20-hsi-grapes/IoTsystemArcitecture.png" class="img-fluid rounded z-depth-1" zoomable=true %}
<div class="caption">
    Our integrated robotic platform during in-field data acquisition. The system combines a mobile base, a robotic arm for sensor positioning, a hyperspectral camera, and GPS.
</div>

---

## From Data Points to Actionable Maps

The final output is not just a single prediction, but a comprehensive map that reveals in-field variability. This allows growers to move from manual, sparse sampling to data-driven management.

Our system successfully identifies individual bunches and provides granular predictions. In our tests, **the LISA module improved quality prediction generalization by over 20%** compared to baseline models that were not robust to illumination changes. The full pipeline achieved a recall of 0.82 for bunch detection and an R² of 0.76 for weight estimation.

{% include figure.liquid loading="eager" path="assets/img/blog/2025-10-20-hsi-grapes/exampleScan.png" class="img-fluid rounded z-depth-1" zoomable=true %}
<div class="caption">
    An example of the system's live output. Each detected bunch is annotated with its ID, estimated weight (W), and predicted quality (Brix and Acidity), ready to be mapped.
</div>

---

## What this means for Precision Viticulture

- **Robust Autonomy:** By solving the illumination problem at the algorithmic level, we reduce the need for impractical hardware or manual calibration steps.
- **High-Resolution Insights:** The system provides data at the per-bunch level, far more detailed than what is possible with traditional methods.
- **Actionable Data:** Growers can use these maps for targeted interventions like differential harvesting, zone-specific irrigation, or optimized fertilization.

While there are still steps to take in testing across more varieties and seasons, this work represents a significant move towards truly autonomous, field-deployable HSI systems.

---

**Paper Citation:**  
Cornelissen, C., De Coninck, S., Willekens, A., Leroux, S., & Simoens, P. (2025). In-Field Mapping of Grape Yield and Quality with Illumination-Invariant Deep Learning. *IEEE Internet of Things Journal*. [https://doi.org/10.1109/JIOT.2025.3617805](https://doi.org/10.1109/JIOT.2025.3617805)

**Preprint:** [arXiv:2510.04864](https://arxiv.org/abs/2510.04864)
