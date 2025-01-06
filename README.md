# **Age Prediction Using Pretrained ResNet18**
![image](https://github.com/user-attachments/assets/996dbc61-e228-4218-919b-955a41b521c8)
download model from - https://drive.google.com/drive/folders/14FbhmPiuO6TDgxoJU6npzBOJXlpYPK0r?usp=drive_link   

This repository implements an age prediction system using a pretrained ResNet18 model, fine-tuned for regression. It includes training, validation, and testing pipelines, along with preprocessing steps and prediction visualization for single images.

### Features:

1.**Pretrained ResNet18 Model**: Leverages transfer learning for age prediction with optimized fine-tuning.

2.**Custom Training**: Fine-tunes only specific layers (layer4 and fc) to prevent overfitting and accelerate training.

3.**Regression Task**: Predicts a single continuous output, representing the age of individuals.

4.**Validation & Error Metrics**: Evaluates model performance using MSE (Mean Squared Error) and RMS error.

5.**Image Testing Pipeline**: Predicts the age of any external image and visualizes the resulT

Prerequisites:
Python 3.x,
PyTorch,
torchvision,
numpy,
matplotlib,
tqdm,
OpenCV,
# Training Pipeline
Model Initialization:
Fine-tune ResNet18 by freezing earlier layers and modifying the fully connected layer for single-output regression.

Training and Validation:

Implements a custom training loop with MSELoss and Adam optimizer.
Monitors training and validation loss to detect overfitting.
Usage: To start training:
```python
train_model(model, train_loader, val_loader, criterion, optimizer, num_epochs=10, device=device)

