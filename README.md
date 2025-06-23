# Facial Expression Recognition using CNNs
This project demonstrates how convolutional neural networks (CNNs) can be used to recognize facial expressions from grayscale images. It compares multiple CNN architectures of varying depth and complexity to determine the best-performing model for this task.

## 📌 Project Overview

- 📂 Dataset: [FER2019 from Kaggle](https://www.kaggle.com/datasets/jonathanoheix/face-expression-recognition-dataset)
- 🎯 Goal: Classify images of faces into 7 emotion categories:
  - Angry, Disgust, Fear, Happy, Neutral, Sad, Surprise
- 🧠 Models:
  - Fully connected baseline
  - Shallow CNN (2 conv layers, 1 FC)
  - Deep CNN (4 conv layers, 2 FC)
  - Deeper CNN (5 conv layers, 2 FC)

## 🏗️ Model Architecture

All CNN models use standard layers such as:
- Convolutional layers
- Batch normalization
- Dropout for regularization
- Max-pooling for downsampling
- Fully connected layers with ReLU activations
- Softmax output for classification

Example deep model layout:
[Conv -> BN -> ReLU -> Dropout -> MaxPool] x M
[FC -> BN -> ReLU -> Dropout] x N
-> Final FC -> Softmax

## 📊 Results

| Expression | Shallow CNN | Deep CNN | Deeper CNN |
|------------|-------------|----------|-------------|
| Angry      | 32.0%       | 45.9%    | 49.7%       |
| Disgust    | 0.0%        | 0.0%     | 39.2%       |
| Fear       | 19.4%       | 24.2%    | 23.8%       |
| Happy      | 79.9%       | 84.2%    | 86.8%       |
| Sad        | 46.4%       | 49.6%    | 51.0%       |
| Surprise   | 64.4%       | 73.3%    | 81.4%       |
| Neutral    | 62.2%       | 65.8%    | 65.1%       |

- 🧪 Best test accuracy: **61.76%** using the deeper CNN model.

- 🧠 Insights
CNNs significantly outperform fully connected models for facial expression recognition.

More layers improve performance, but the gain flattens after 5 convolutional layers.

Dataset imbalance (e.g., very few "Disgust" images) affects model accuracy.

📎 References

Kaggle FER2019 Dataset: https://www.kaggle.com/datasets/jonathanoheix/face-expression-recognition-dataset

CNN theory: https://cs231n.github.io/convolutional-networks/

Alizadeh & Fazel, 2017: Convolutional Neural Networks for Facial Expression Recognition

