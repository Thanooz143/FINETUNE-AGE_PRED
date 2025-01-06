download model from - https://drive.google.com/drive/folders/14FbhmPiuO6TDgxoJU6npzBOJXlpYPK0r?usp=drive_link
![image](https://github.com/user-attachments/assets/996dbc61-e228-4218-919b-955a41b521c8)
                                                       # **Age Prediction Using Pretrained ResNet18**
                                                       
This repository implements an age prediction system using a pretrained ResNet18 model, fine-tuned for regression. It includes training, validation, and testing pipelines, along with preprocessing steps and prediction visualization for single images.

Features
Pretrained ResNet18 Model: Leverages transfer learning for age prediction with optimized fine-tuning.
Custom Training: Fine-tunes only specific layers (layer4 and fc) to prevent overfitting and accelerate training.
Regression Task: Predicts a single continuous output, representing the age of individuals.
Validation & Error Metrics: Evaluates model performance using MSE (Mean Squared Error) and RMS error.
Image Testing Pipeline: Predicts the age of any external image and visualizes the result.

