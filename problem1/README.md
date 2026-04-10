# Pneumonia Detection Using CNN

# Introduction:
This project focuses on building a Convolutional Neural Network (CNN) model to classify chest X-ray images into two categories:

1.Pneumonia.

2.Normal.

The dataset contains 5,863 JPEG images, organized into:
       
       Archive/
            │
            ├── train/
            ├── val/
            └── test/

# Objective:
To develop a deep learning model that can:

>Automatically classify chest X-ray images

>Assist in early detection of pneumonia

>Achieve high accuracy (≈89%+)

# Methodology:
1. Data Preprocessing:
   
>Images resized to (380 × 380)

>Pixel normalization (rescale = 1/255)

>Dataset loaded using ->ImageDataGenerator

2. Handling Imbalanced Dataset:

The dataset is imbalanced (Pneumonia > Normal).

Techniques used:

>Class Weights

>Data Augmentation

>Rotation

>Zoom

>Horizontal Flip

>Shift transformations

3. Model Architecture:

We used Transfer Learning with EfficientNetB4:

>Pretrained on ImageNet

>Base layers initially frozen

>Custom classification head added:

    EfficientNetB4 (Base Model)

        ↓
    Global Average Pooling

        ↓
    Batch Normalization

        ↓
    Dense (256, ReLU)

        ↓
    Dropout (0.5)

        ↓
    Dense (1, Sigmoid)


4. Loss Function:
   
>Focal Loss → handles class imbalance better than binary crossentropy

5. Training Strategy:
   
>Optimizer: Adam

>Learning Rate:

             Initial: 1e-4
             Fine-tuning: 1e-5
>Callbacks Used:

             EarlyStopping (patience = 3)
             ReduceLROnPlateau
             ModelCheckpoint

6. Fine-Tuning:
   
>Last layers of EfficientNet were unfrozen.

>Model retrained for better feature learning.

# Results & Findings:

| Metric              | Value       |
| ------------------- | ----------- |
| Training Accuracy   | ~95%        |
| Validation Accuracy | ~90–93%     |
| Test Accuracy       | **~89–92%** |

📉 Confusion Matrix Insights:

>High detection rate for Pneumonia cases.

>Some misclassification in Normal class.

>Model is slightly biased due to dataset imbalance.

📈 Observations:
>Transfer learning significantly improved performance.

>Focal loss helped reduce imbalance impact.

>Data augmentation improved generalization.

>Fine-tuning increased final accuracy.

# Conclusion:

This project successfully demonstrates that:

>CNN with transfer learning can effectively classify medical images.

>The model achieves high accuracy (~90%).

>It can assist healthcare professionals in early pneumonia detection.

