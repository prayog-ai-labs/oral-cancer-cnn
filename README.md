# Oral Cancer Classification using Deep Learning

This repository presents a comprehensive deep learning–based study for **oral cancer histopathological image classification**, focusing on distinguishing **Normal Oral Epithelium** from **Oral Squamous Cell Carcinoma (OSCC)**.

Multiple convolutional neural network (CNN) architectures were implemented and compared, including:
- A Custom CNN trained from scratch
- VGG16 (Transfer Learning)
- ResNet50 (Transfer Learning)
- InceptionResNetV2 (Transfer Learning)

All experiments were conducted using **Google Colab with GPU acceleration** and a publicly available histopathology dataset.

---

## 1. Project Objectives

- Perform exploratory data analysis (EDA) on oral cancer histopathology images
- Build and evaluate a **baseline custom CNN**
- Apply **transfer learning** using multiple pretrained architectures
- Compare model performance using standard classification metrics
- Analyze the effectiveness of transfer learning on small medical imaging datasets

---

## 2. Dataset Description

The project uses a publicly available histopathological image dataset containing normal oral epithelium and OSCC images.

### Dataset Details
- **Modality:** Histopathological images (H&E stained)
- **Magnification:** 100×
- **Classes:**
  - Normal Oral Cavity Histopathological Images
  - OSCC Histopathological Images
- **Characteristics:**
  - High-resolution images
  - Texture-rich patterns typical of histopathology
  - Balanced class distribution
  - Limited dataset size (suitable for transfer learning)

### Dataset Citation (Required)

> Rahman, Tabassum Yesmin (2019).  
> *A histopathological image repository of normal epithelium of Oral Cavity and Oral Squamous Cell Carcinoma*.  
> **Mendeley Data**, Version 1.  
> DOI: https://doi.org/10.17632/ftmp4cvtmb.1

---

## 3. Methodology

### 3.1 Data Preprocessing
- Images resized to **224 × 224**
- Pixel normalization (rescale 1/255)
- Data augmentation:
  - Rotation
  - Zoom
  - Width/height shifts
  - Horizontal flip

### 3.2 Training Strategy
- Train/validation split: **80% / 20%**
- Early stopping based on validation loss
- Best model checkpoint saved
- Same evaluation protocol across all models

### 3.3 Evaluation Metrics
Models were evaluated on **training, validation, and test sets** using:
- Accuracy
- Precision
- Recall
- F1-score

---

## 4. Implemented Models

### 4.1 Custom CNN
- Built from scratch using stacked convolution and pooling layers
- Serves as a baseline model
- Learns all features directly from the dataset

### 4.2 VGG16 (Transfer Learning)
- Pretrained on ImageNet
- Deep and uniform convolutional architecture
- Fully connected classification head added
- Backbone frozen during training

### 4.3 ResNet50 (Transfer Learning)
- Residual connections for stable deep learning
- Strong feature reuse
- Better convergence and generalization

### 4.4 InceptionResNetV2 (Transfer Learning)
- Combines inception modules with residual connections
- Multi-scale feature extraction
- Best-performing model in this study

---

## 5. Model Comparison Summary

| Model | Training from Scratch | Transfer Learning | Generalization | Overall Rank |
|----|----|----|----|----|
| Custom CNN | Yes | No | Limited | 4 |
| VGG16 | No | Yes | Good | 3 |
| ResNet50 | No | Yes | Very Good | 2 |
| InceptionResNetV2 | No | Yes | Excellent | 1 |

### Key Observations
- Transfer learning significantly outperforms training from scratch
- Custom CNN is useful as a baseline but struggles with limited data
- VGG16 improves performance but is computationally heavy
- ResNet50 provides a strong balance between performance and efficiency
- InceptionResNetV2 achieves the best accuracy and generalization due to multi-scale feature extraction

---

## 6. Results and Conclusion

- **InceptionResNetV2** achieved the highest overall performance across all evaluation metrics.
- **ResNet50** performed competitively with slightly lower accuracy but better efficiency.
- **VGG16** provided a solid early transfer learning baseline.
- **Custom CNN** demonstrated the limitations of training deep models from scratch on small medical datasets.

This study highlights the **importance of transfer learning for medical image classification**, especially when dataset size is limited and texture-based features dominate.

---

## 7. Repository Structure

├── Oral_Cancer_EDA.ipynb
├── Oral_Cancer_Classification_using_Custom_CNN.ipynb
├── Oral_Cancer_Classification_using_VGG16.ipynb
├── Oral_Cancer_Classification_using_ResNet50.ipynb
├── Oral_Cancer_InceptionResNetV2.ipynb
├── MODEL_COMPARISON_REPORT.md
└── README.md

---

## 8. Acknowledgements

We acknowledge the dataset author for making the oral cancer histopathology dataset publicly available and enabling reproducible research in medical image analysis.