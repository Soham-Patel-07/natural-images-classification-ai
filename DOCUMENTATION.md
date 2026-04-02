# Natural Images Classification - Documentation

## Project Overview

This project is part of the MSc Computer Science program, specifically for the **Artificial Intelligence and Machine Vision** module. The goal was to build a natural image classifier capable of distinguishing between 8 different categories of images.

## Dataset Description

**Source**: [Kaggle Natural Images Dataset](https://www.kaggle.com/datasets/prasunroy/natural-images)

The dataset contains approximately **8,699 images** across 8 categories:
- Airplane
- Car
- Cat
- Dog
- Fruit
- Person
- (2 additional classes)

### Dataset Details
- **Format**: JPEG/PNG images
- **Preprocessing**: Resized to 224x224 pixels
- **Data Split**: 80% training, 20% validation

## Technical Implementation

### Model Architecture
The project uses **Transfer Learning** with **MobileNetV2** as the base model:
1. **Base Model**: MobileNetV2 (pre-trained on ImageNet)
2. **Feature Extraction**: Global Average Pooling
3. **Custom Classifier**: 
   - Dense layer (256 units, ReLU activation)
   - Dropout (0.5 for regularization)
   - Output layer (8 units, Softmax for classification)

### Data Augmentation
Applied to improve model generalization:
- Rotation range: 20°
- Width shift: 20%
- Height shift: 20%
- Shear range: 20%
- Zoom range: 20%
- Horizontal flip: enabled
- Fill mode: nearest

### Training Configuration
- **Optimizer**: Adam (learning rate: 0.0001)
- **Loss Function**: Categorical Crossentropy
- **Epochs**: 10
- **Batch Size**: 32

## Project Structure

```
D:\New folder\Code\AI\
├── Code/
│   ├── natural_images_classification.py     # Main training script
│   └── Natural_Images_Classification.ipynb  # Jupyter notebook
├── Screenshot/
│   ├── Confusion matrix.png                  # Model performance visualization
│   ├── Training Progress.png                # Training/validation curves
│   └── Sample Images from each Category.png # Dataset preview
├── Report/
│   ├── AI Natural Image report.pdf          # Project report (PDF)
│   └── AI Natural Image report.docx         # Project report (Word)
├── transfer_learning_natural_images.h5      # Trained model file
└── README.md                                 # Project README
```

## Dependencies

| Package | Purpose |
|---------|---------|
| TensorFlow | Deep learning framework |
| Keras | Neural network API |
| NumPy | Numerical computing |
| Matplotlib | Visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Metrics (confusion matrix) |

## Results

The model produces:
1. **Training/Validation Accuracy Curves** - Shows model learning progress
2. **Training/Validation Loss Curves** - Shows loss reduction over epochs
3. **Confusion Matrix** - Displays classification performance per class

## Usage

1. Upload dataset to Google Drive
2. Run the Python script or Jupyter notebook
3. Model training will begin automatically
4. Trained model saved as `transfer_learning_natural_images.h5`

## Academic Information

- **Module**: Artificial Intelligence and Machine Vision
- **Course**: MSc Computer Science
- **University**: University of East London
- **Completed**: May 2025
- **Purpose**: Coursework assignment for AI & Machine Vision module

## Author Notes

- This project was developed using Google Colab
- The model uses transfer learning for efficient training with limited data
- MobileNetV2 was chosen for its balance of accuracy and computational efficiency