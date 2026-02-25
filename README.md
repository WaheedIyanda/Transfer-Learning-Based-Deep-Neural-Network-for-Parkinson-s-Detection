# 🧠 Deep Transfer Learning for Parkinson’s Disease Detection

## 📌 Overview

This project presents a deep learning framework for detecting Parkinson’s disease from digital motor drawings (spiral and wave patterns).

Due to limited dataset size, a transfer learning strategy was implemented using a pretrained ResNet18 model, followed by progressive fine-tuning and task-specific specialization.

---

## 🎯 Objective

The goal of this project was to:

- Develop a deep learning model for Parkinson’s disease classification  
- Address small dataset challenges using data augmentation  
- Apply transfer learning for improved generalization  
- Build specialist models for spiral and wave drawings  

---

## 🏗 Methodology

### 1️⃣ Data Preparation & Augmentation

To reduce overfitting, extensive augmentation was applied to the training data:

- Random rotations  
- Affine transformations  
- Perspective distortions  
- Spatial shifts  

---

### 2️⃣ Transfer Learning Backbone

A ResNet18 model pretrained on ImageNet was used as the base architecture.

Steps:
- Replaced the final classification layer  
- Trained on a combined spiral and wave dataset  
- Fine-tuned deeper layers (layer4)  

**Mixed Test Accuracy:** 80.00%

---

### 3️⃣ Specialist Models

#### 🌀 Spiral Specialist

- Initialized from fine-tuned backbone  
- Fine-tuned on spiral-only dataset  
- Unfroze layer4 and fully connected layer  

**Spiral Test Accuracy:** 90.00%

---

#### 🌊 Wave Specialist

- Initialized from general backbone  
- Fine-tuned on wave-only dataset  
- Progressive unfreezing (layer3 + layer4 + fc)

**Wave Test Accuracy:** 73.33%

---

## 📊 Results Summary

| Model | Dataset | Test Accuracy |
|-------|----------|---------------|
| General Backbone | Mixed | 80.00% |
| Spiral Specialist | Spiral | 90.00% |
| Wave Specialist | Wave | 73.33% |

---

## 🛠 Tech Stack

- Python  
- PyTorch  
- Torchvision  
- Google Colab  
- Transfer Learning (ResNet18)
