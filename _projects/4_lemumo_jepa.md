---
layout: page
title: Le MuMo JEPA
description: Multi-modal self-supervised representation learning with learnable fusion tokens
img: assets/img/publication_preview/lemumojepa_paper.png
importance: 1
category: research
---

## Le MuMo JEPA

Le MuMo JEPA is a self-supervised framework that learns unified representations from RGB images and aligned companion modalities (e.g., camera-aligned LiDAR depth, thermal) without requiring any manual labels.

### The Challenge

Autonomous perception systems rely on multiple sensor modalities — cameras, LiDAR, thermal — yet most multi-modal fusion methods depend on large annotated datasets that are expensive and time-consuming to collect. Furthermore, naively concatenating modality tokens inside a transformer leads to quadratic attention costs that scale poorly with the number of sensors.

### Our Solution

Le MuMo JEPA introduces **learnable fusion tokens** that act as a latent bottleneck between modality-specific patch stems inside a shared Vision Transformer:

1. **Cross-modal fusion tokens** — a set of tokens equal in number to the spatial patches aggregate information from spatially corresponding RGB and companion-modality patches through cross-attention
2. **Pruned fusion** — after the initial cross-modal attention layer, modality-specific tokens are dropped, forcing all cross-modal information into the shared fusion-token grid and reducing attention cost by ~9×
3. **SIGReg objective** — Sketched Isotropic Gaussian Regularization applied to the joint multi-modal CLS embedding, removing the need for stop-gradients, teacher-student networks, or negative pairs

### Key Results

- **Strong performance-efficiency trade-offs** across Waymo (RGB + LiDAR), nuScenes (RGB + LiDAR), and FLIR ADAS (RGB + Thermal) benchmarks
- Frozen patch probes support dense **depth estimation**, **semantic segmentation**, and **CenterNet-style 3D object detection** from a single pretrained encoder
- ~9× attention cost reduction compared to full multi-modal token concatenation, with minimal representation quality loss
- Accepted at **CVPR 2026 Workshop on Unified Robotic Vision with Cross-Modal Sensing and Alignment (URVIS)**

### Applications

- Autonomous driving perception
- Multi-sensor robotic navigation
- Dense 3D scene understanding from frozen representations
- Efficient multi-modal pretraining for resource-constrained deployment

**Paper:** [Le MuMo JEPA: Multi-Modal Self-Supervised Representation Learning with Learnable Fusion Tokens](https://arxiv.org/abs/2603.24327) (CVPR 2026 URVIS Workshop)

**Code:** [github.com/ciemcornelissen/le-mumo-jepa](https://github.com/ciemcornelissen/le-mumo-jepa)
