# DATASet_WasteClass
Multi-Source Waste Classification Dataset for Edge AI Benchmarking
## Overview
This repository contains datasets used for training and evaluating a deployment-aware edge AI framework for real-time waste classification on Raspberry Pi 4B.

## Dataset Composition
### **ImageData-1: Training Dataset**
**Source:** [Kaggle - Garbage Classification v2](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2)
- **Total Images:** 4,000 labeled RGB images
- **Classes:** 4 waste categories
  - Biological: 998 images
  - Metal: 997 images
  - Paper: 998 images
  - Plastic: 997 images
- **Purpose:** Model training and cloud-based evaluation
- **Characteristics:** Natural variability in lighting, backgrounds, object orientations, and scales


### **ImageData-2: Edge Evaluation Dataset**
**Source:** Original data collected for this research

- **Total Images:** 378 manually captured RGB images
- **Classes:** 4 waste categories
  - Biological: ~95 images
  - Metal: ~90 images
  - Paper: ~94 images
  - Plastic: ~99 images
- **Purpose:** Real-world edge device testing and Raspberry Pi benchmarking
- **Characteristics:** Practical deployment conditions with varied lighting and angles
- **Device:** Captured using mobile phone camera


## Dataset Distribution

| Class | ImageData-1 (Training) | ImageData-2 (Edge Testing) |
|-------|------------------------|---------------------------|
| Biological | 998 | ~95 |
| Metal | 997 | ~90 |
| Paper | 998 | ~94 |
| Plastic | 997 | ~99 |
| **Total** | **4,000** | **378** |

## Data Availability Statement
- **ImageData-1 (Training):** Publicly available at [Kaggle](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2)
- **ImageData-2 (Edge Testing):** Available in this repository at `/imagedata-2/`
