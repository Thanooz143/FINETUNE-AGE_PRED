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
The training pipeline is designed to fine-tune a pretrained ResNet18 model for age prediction using a regression approach. Below is a detailed breakdown:

1. Model Initialization
The ResNet18 model is loaded with pretrained weights (weights=ResNet18_Weights.IMAGENET1K_V1 for compatibility with PyTorch versions ≥ 0.13).
Layers layer1, layer2, and layer3 are frozen to retain learned features from the pretrained model.
The fully connected layer (fc) is replaced with a single output node for regression (predicting age as a continuous variable).
2. Loss Function
Mean Squared Error (MSELoss):
Used as the loss function since it is suitable for regression tasks.
Measures the squared difference between predicted and actual ages to minimize errors.
3. Optimizer
Adam Optimizer:
Optimizes model parameters with an initial learning rate of 1e-4.
Balances efficiency and adaptability during weight updates.
4. Data Preprocessing
Input images are resized and normalized.
Dimensions are permuted to match the PyTorch format [batch_size, channels, height, width].
5. Training Loop
Epochs:
The model is trained for a user-defined number of epochs (e.g., 10 by default).
Batch Processing:
Each batch of images and labels is passed through the model for forward propagation, loss calculation, and backpropagation.
Freezing Layers:
Only layer4 and fc are trainable to focus on task-specific learning while preventing overfitting.
6. Validation
After each epoch, the model evaluates on a separate validation dataset.
The average validation loss is computed to monitor the model’s generalization.
7. Performance Tracking
Training and validation losses are printed after every epoch for easy monitoring:
plaintext
Copy code
Epoch 1/10, Training Loss: 580.8863, Validation Loss: 184.5743
8. Early Stopping (Optional)
Overfitting can be mitigated by monitoring validation loss and stopping training early if it stops improving.
Usage: To start training:
```python
train_model(model, train_loader, val_loader, criterion, optimizer, num_epochs=10, device=device)

