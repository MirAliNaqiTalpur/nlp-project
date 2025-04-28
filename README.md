# Crop Disease Diagnostician

## Overview
The Crop Disease Diagnostician is a multimodal system designed to diagnose crop diseases using natural language processing (NLP) and computer vision. It integrates textual farmer queries (e.g., "My wheat leaves have brown spots") and crop images to provide accurate disease diagnoses, focusing on wheat diseases as a case study. This project leverages the Qwen2.5-VL-3B-Instruct model to process multimodal inputs, aiming to support smallholder farmers by democratizing access to diagnostic expertise.

## Dataset
The dataset used is a subset of the Crop Disease Domain Multimodal (CDDM) dataset (Liu et al., 2023), focusing on wheat:
- **Size**: 5,929 images across 4 classes (Healthy, Leaf Rust, Stripe Rust, Septoria Leaf Spot).
- **Classes**:
  - Healthy: 1,524 images
  - Leaf Rust, Stripe Rust, Septoria Leaf Spot: 4,405 images combined.
- **Source**: Web-sourced images (e.g., Kaggle) and private field survey data, annotated by agricultural experts.
- **Note**: The dataset is not included in this repository due to its size. It can be accessed from the original CDDM dataset source or Kaggle.

## Methodology
- **Model**: Qwen2.5-VL-3B-Instruct
  - Processes multimodal inputs (textual queries + images).
  - Uses Vision Transformer (ViT) with window attention for computational efficiency.
  - Pre-trained on 4.1 trillion tokens, including visual knowledge data (e.g., flora identification).
- **Processing**:
  - Text: Tokenized queries (max 128 tokens).
  - Images: 224x224 pixel tensors, processed by the visual encoder.
  - Cross-modal attention aligns text and image features for diagnosis.
- **Evaluation**:
  - Test set: 80 samples (20 per class) with image + 3 questions.
  - Metrics: Plant Identification Accuracy, Disease Diagnosis Accuracy.
  - Conducted on Google Colab due to local computational constraints.

## Results
- **Plant Identification Accuracy**: 50.00%
- **Disease Diagnosis Accuracy**: 18.75%
- **Analysis**:
  - Moderate success in plant identification, but challenges in distinguishing subtle disease symptoms.
  - Limited fine-tuning and small dataset impacted performance.
  - Multimodal approach shows potential over single-modality systems.

## Web Application

The Crop Disease Diagnostician is deployed through a simple web application where farmers can upload images and enter queries to receive disease diagnosis suggestions. Below is a screenshot of the web application interface:

![Web Application Screenshot](../images/webapp.png)

The web app provides a user-friendly interface for farmers to interact with the system, allowing them to easily upload images of their crops and ask diagnostic questions.

---

