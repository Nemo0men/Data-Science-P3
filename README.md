# FloodNet: High-Resolution Semantic Segmentation

### UAV-Based Aerial Imagery Analysis for Post-Disaster Response

[](https://pytorch.org/)
[](https://github.com/qubvel/segmentation_models.pytorch)
[](https://www.google.com/search?q=https://github.com/BinaLab/FloodNet-Challenge-EARTH-2021)

## 📌 Project Overview

This project focuses on the automated detection of flooded regions using high-resolution aerial imagery from the **FloodNet** dataset. Captured via Unmanned Aerial Vehicles (UAVs) following Hurricane Harvey, this data provides ultra-high spatial detail that satellites often miss due to cloud cover or resolution limits.

The goal was to build a segmentation pipeline capable of breaking the **0.70 Mean IoU** threshold for binary flood detection, providing a reliable tool for emergency responders to identify submerged infrastructure.

-----

## 🔍 Exploratory Data Analysis (EDA)

### The Class Imbalance Problem

Initial EDA revealed a severe **Long-Tail Distribution**. Background pixels (grass, trees, and non-flooded structures) outnumbered flooded areas by over 100:1.

**Key takeaway:** Standard "Pixel Accuracy" is a biased metric for this task. A model could achieve 90% accuracy by predicting "Dry" for every pixel while completely failing the disaster response mission.

### Label Engineering

To strengthen the signal-to-noise ratio, we consolidated the original 10 semantic classes into a binary task:

  * **Target (1):** Building-Flooded, Road-Flooded, Water.
  * **Background (0):** All other categories.

-----

## 🛠 Technical Implementation

### Architecture Evolution

We moved from a baseline **U-Net** to **DeepLabV3+** with a **ResNet101** encoder. The switch was motivated by the need for Atrous Spatial Pyramid Pooling (ASPP), which allows the model to capture multi-scale context—essential for distinguishing between small flooded building pockets and large open water bodies.

### Hyperparameters & Optimization

| Parameter | Value | Justification |
| :--- | :--- | :--- |
| **Resolution** | 768 x 768 | Preserves high-detail drone features. |
| **Loss Function** | DiceCELoss | Dice (0.7) + CE (0.3) to handle extreme imbalance. |
| **Weight Decay** | 1e-3 | Mitigates overfitting observed in initial runs. |
| **LR Scheduler** | ReduceLROnPlateau | Settles "jitter" to allow for fine-tuned convergence. |

-----

## 📉 Addressing Bias and Uncertainty

### Bias Mitigation

By using **Dice Loss**, we explicitly addressed the model's inherent bias toward the majority "Non-Flood" class. Dice loss penalizes the model based on spatial overlap, ensuring that a small flooded building is as mathematically significant as a massive dry field.

### Uncertainty Reduction

We identified high "jitter" in the validation loss curves as a sign of optimization uncertainty. The implementation of a **Learning Rate Scheduler** (Factor: 0.2, Patience: 4) allowed the model to "slow down" and refine organic boundaries once it reached the 0.67 IoU plateau.

-----

## 🚀 Results

  * **Metric Breakthrough:** The combination of DeepLabV3+ and the LR scheduler successfully pushed the validation IoU toward the **0.70 benchmark**.
  * **Qualitative Improvement:** Visual validation showed significantly sharper boundaries on flooded roads compared to the "blocky" artifacts produced by the U-Net baseline.

-----

## 🔭 Future Research (Next Steps)

1.  **Multi-Modal Data Fusion:** Incorporating **Digital Elevation Models (DEM)**. Since water seeks the lowest point, elevation data would help the model distinguish between dark shadows and water where visual textures are identical.
2.  **Test-Time Augmentation (TTA):** Ensembling flipped and rotated predictions during inference to smooth out noisy masks and reduce aleatoric uncertainty.
3.  **Domain Adaptation:** Testing the model on diverse geographical regions (beyond Texas/Harvey) to ensure the features generalize to different soil types and urban architectures.

-----

**Author:** Nemo Kim  
**Course:** UVA Data Science Project  
**Date:** April 2026
