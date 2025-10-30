---
layout: page
title: LISA Framework
description: Light-Invariant Spectral Autoencoder for precision viticulture
img: assets/img/projects/AE.png
importance: 1
category: research
---

## Light-Invariant Spectral Autoencoder (LISA)

LISA is a domain-adversarial deep learning framework designed to overcome the fundamental challenge of illumination variance in hyperspectral imaging for agricultural applications.

### The Challenge

Field-deployed optical sensing systems face a critical problem: data captured under different lighting conditions (morning sun, afternoon, cloudy, lab-controlled) look spectrally different even for identical samples. This "domain shift" severely degrades the performance of standard machine learning models when deployed in real-world conditions.

### Our Solution

LISA employs domain-adversarial learning to force the model to learn illumination-invariant features. The network is trained to:
1. Accurately predict grape quality (Brix and acidity levels)
2. Be unable to distinguish between different lighting conditions

This adversarial approach ensures the learned representations are robust to environmental changes.

### Key Results

- **20% improvement** in generalization compared to baseline models
- Successfully deployed in real vineyards for in-field grape quality assessment
- Part of a complete IoT-enabled robotic system for precision viticulture
- Published in **IEEE Internet of Things Journal** (2025)

### Applications

- Non-destructive grape quality prediction
- Real-time yield mapping
- Spatially-resolved vineyard management
- Harvest optimization

**Related Publication:** [In-Field Mapping of Grape Yield and Quality with Illumination-Invariant Deep Learning](https://ieeexplore.ieee.org/) (IEEE IoT Journal, 2025)
