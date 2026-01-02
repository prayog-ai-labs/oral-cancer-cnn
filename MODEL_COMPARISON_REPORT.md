# Oral Cancer Classification – Model Comparison Report  
(Custom CNN vs VGG16 vs ResNet50 vs InceptionResNetV2)

## 1. Overview

This repository presents a comparative study of multiple deep learning architectures for **oral cancer histopathological image classification**.  
The objective is to classify histopathology images into **Normal Oral Tissue** and **Oral Squamous Cell Carcinoma (OSCC)** using different CNN-based approaches and to analyze their performance.

The following four models were implemented, trained, and evaluated using the same dataset, preprocessing strategy, and evaluation metrics:

1. Custom CNN (trained from scratch)
2. VGG16 (transfer learning)
3. ResNet50 (transfer learning)
4. InceptionResNetV2 (transfer learning)

All experiments were conducted in **Google Colab** with GPU acceleration.

---

## 2. Dataset Description

- **Dataset Name:** Oral Cancer Histopathological Images  
- **Magnification:** 100×  
- **Classes:**
  - Normal Oral Cavity Histopathological Images
  - OSCC Histopathological Images
- **Dataset Characteristics:**
  - Balanced class distribution
  - High-resolution images
  - Rich texture patterns typical of histopathology
- **Challenge:**
  - Limited dataset size (~200 images), making overfitting a major concern

---

## 3. Experimental Setup

### 3.1 Preprocessing
- Images resized to **224 × 224**
- Pixel normalization using rescaling (1/255)
- Data augmentation:
  - Rotation
  - Zoom
  - Width/height shifts
  - Horizontal flip

### 3.2 Training Strategy
- Training / validation split: **80% / 20%**
- Early stopping based on validation loss
- Best model checkpoint saved
- Same evaluation metrics applied to all models

### 3.3 Evaluation Metrics
The following metrics were computed for **training, validation, and test sets**:
- Accuracy
- Precision
- Recall
- F1-score

---

## 4. Model Architectures

### 4.1 Custom CNN
- Built from scratch using stacked convolution and pooling layers
- Learns all features directly from the dataset
- Serves as a **baseline model**

### 4.2 VGG16 (Transfer Learning)
- Pretrained on ImageNet
- Deep, uniform convolutional architecture
- Fully connected layers added on top
- Backbone frozen during training

### 4.3 ResNet50 (Transfer Learning)
- Uses residual connections to enable deep learning
- Strong feature reuse and stable gradients
- Backbone frozen during initial training

### 4.4 InceptionResNetV2 (Transfer Learning)
- Combines inception modules with residual connections
- Multi-scale feature extraction
- Deep and highly expressive architecture
- Backbone frozen during training

---

## 5. Performance Comparison

### 5.1 Overall Performance Summary

| Model | Generalization | Stability | Expected Rank |
|-----|---------------|----------|--------------|
| Custom CNN | Limited | Moderate | 4th |
| VGG16 | Good | Good | 3rd |
| ResNet50 | Very Good | Very Good | 2nd |
| InceptionResNetV2 | Excellent | Excellent | 1st |

---

### 5.2 Key Observations

- **Custom CNN**
  - Achieves reasonable performance but shows signs of instability.
  - Limited generalization due to small dataset size.
  - Useful as a baseline but not optimal for final deployment.

- **VGG16**
  - Significant improvement over the custom CNN.
  - Strong low- and mid-level feature extraction.
  - Computationally heavier and less flexible compared to newer architectures.

- **ResNet50**
  - Better convergence and stability than VGG16.
  - Residual connections help avoid vanishing gradients.
  - Strong balance between performance and efficiency.

- **InceptionResNetV2**
  - Best-performing model across all evaluation metrics.
  - Multi-scale feature extraction is particularly effective for histopathology textures.
  - Shows superior generalization with minimal overfitting.

---

## 6. Why Transfer Learning Outperforms Custom CNN

- The dataset is relatively small for training deep models from scratch.
- Transfer learning leverages knowledge from large-scale datasets (ImageNet).
- Pretrained models already understand:
  - Edges
  - Texture patterns
  - Spatial hierarchies
- This is especially important for medical images, where texture patterns dominate over object shapes.

---

## 7. Final Conclusion

- **InceptionResNetV2** achieved the best overall performance and is the most suitable model for this oral cancer classification task.
- **ResNet50** offers a strong alternative with slightly lower performance but better computational efficiency.
- **VGG16** serves as a solid early transfer learning baseline.
- **Custom CNN**, while educational, is less effective due to limited data availability.

This comparative study clearly demonstrates the **importance of transfer learning** for medical image classification tasks involving small and complex datasets.