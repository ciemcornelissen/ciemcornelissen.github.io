---
layout: page
title: OHSLIC Algorithm
description: Online Hyperspectral Superpixel Segmentation for UAV Phenotyping
img: assets/img/projects/model_ohslic.png
importance: 2
category: research
---

## Online Hyperspectral SLIC (OHSLIC)

OHSLIC is a computationally efficient superpixel segmentation algorithm specifically designed for processing hyperspectral imagery from UAV platforms in real-time.

### The Problem

UAV-based hyperspectral imaging generates massive data volumes (hundreds of spectral bands per pixel), making real-time processing infeasible with traditional segmentation methods. Agricultural phenotyping requires timely analysis, not post-processing days later.

### Algorithm Innovation

OHSLIC adapts the classic SLIC (Simple Linear Iterative Clustering) algorithm for:
- **Online processing**: Processes data as it streams from the sensor
- **Hyperspectral efficiency**: Handles hundreds of spectral bands without computational explosion
- **Memory constraints**: Operates within limited onboard computing resources

The algorithm achieves superpixel segmentation of individual plant phenotypes directly during flight operations.

### Performance

- **200x faster** than batch processing methods on hyperspectral data
- Enables real-time phenotype extraction during UAV missions
- Successfully deployed in large-scale vineyard monitoring campaigns
- Preserves spectral fidelity while achieving spatial coherence

### Technical Approach

- Spectral distance metrics optimized for high-dimensional data
- Incremental clustering that updates with each scan line
- Adaptive bandwidth selection for varying ground sampling distances

**Related Publication:** [Online Hyperspectral Phenotype Segmentation for UAVs](https://openaccess.thecvf.com/) (WACV 2025)

### Impact

This algorithm enables precision agriculture at scale by making UAV hyperspectral analysis practical for operational deployment rather than just research demonstrations.
