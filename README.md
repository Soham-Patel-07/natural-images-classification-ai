# Natural Images Classification

A deep learning project for classifying natural images into 8 categories using transfer learning with MobileNetV2.

## Overview

This project implements an image classification system for the MSc Computer Science module in Artificial Intelligence and Machine Vision. The model classifies natural images into 8 categories using a Convolutional Neural Network (CNN) with transfer learning.

## Dataset

- **Source**: [Kaggle Natural Images Dataset](https://www.kaggle.com/datasets/prasunroy/natural-images)
- **Total Images**: ~8,699
- **Categories**: 8 classes (airplane, car, cat, dog, fruit, person, etc.)
- **Image Size**: 224x224 pixels
- **Split**: 80% training, 20% validation

## Model Architecture

- **Base Model**: MobileNetV2 (pre-trained on ImageNet)
- **Transfer Learning**: Frozen base model with custom classification head
- **Custom Layers**:
  - GlobalAveragePooling2D
  - Dense (256 units, ReLU)
  - Dropout (0.5)
  - Output Dense (8 units, Softmax)

## Training Configuration

- **Optimizer**: Adam (learning rate: 0.0001)
- **Loss**: Categorical Crossentropy
- **Epochs**: 10
- **Batch Size**: 32
- **Data Augmentation**: Rotation, shift, shear, zoom, horizontal flip

## Results

- Training accuracy and loss plots
- Validation accuracy and loss plots
- Confusion matrix for performance analysis

## Images

![Confusion Matrix](Screenshot/Confusion%20matrix.png)

## Files

| File | Description |
|------|-------------|
| `Code/natural_images_classification.py` | Main Python script for training |
| `Code/Natural_Images_Classification.ipynb` | Jupyter notebook version |
| `transfer_learning_natural_images.h5` | Trained model weights |
| `Screenshot/` | Training progress and confusion matrix visualizations |
| `Report/` | Project report (PDF/DOCX) |

## Requirements

```
tensorflow
keras
numpy
matplotlib
seaborn
scikit-learn
```

## Usage

1. Mount Google Drive and extract dataset
2. Run the training script
3. Model will be saved as `transfer_learning_natural_images.h5`

## Course Information

- **Module**: Artificial Intelligence and Machine Vision
- **Course**: MSc Computer Science
- **University**: University of East London
- **Completed**: May 2025