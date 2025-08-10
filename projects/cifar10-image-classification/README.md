# CIFAR-10 Image Classification 🖼️

An advanced convolutional neural network for multi-class image classification using PyTorch and the CIFAR-10 dataset, featuring modern deep learning techniques.

## 🎯 Project Overview

This project implements a sophisticated CNN architecture to classify color images into 10 different categories. The model incorporates advanced techniques like batch normalization, dropout, and data augmentation to achieve robust performance on natural images.

## 📊 Dataset Information

- **Dataset:** CIFAR-10 (Canadian Institute For Advanced Research)
- **Training samples:** 50,000 images
- **Test samples:** 10,000 images
- **Image dimensions:** 32×32×3 (RGB color)
- **Classes:** 10 categories

## Model Architecture

![CNN Architecture](../assets/cifar10_architecture.png)

### Network Structure:

```
Input (3×32×32)
    ↓
Conv2D(3→32, 3×3) → ReLU → BatchNorm2D
    ↓
Conv2D(32→64, 3×3) → ReLU → MaxPool2D(2×2) → BatchNorm2D
    ↓
Flatten → Linear(12544→512) → ReLU → Dropout(0.5)
    ↓
Linear(512→10) → Output
```

**Architecture Highlights:**

- **Deep Feature Extraction:** Progressive channel expansion (3→32→64)
- **Regularization:** Batch normalization and dropout for better generalization
- **Efficient Design:** Strategic pooling to reduce spatial dimensions
- **Modern Techniques:** ReLU activation throughout the network

**Parameters:** ~6.4M trainable parameters

### Training Enhancements

- **Progress Tracking:** tqdm integration for real-time training progress
- **Model Checkpointing:** Automatic saving/loading of best model weights
- **Advanced Optimization:** Adam optimizer with weight decay (1e-4)
- **Learning Rate:** 0.001 for stable convergence

## Training Configuration

- **Optimizer:** Adam (lr=0.001, weight_decay=1e-4)
- **Loss Function:** CrossEntropyLoss
- **Batch Size:** 64
- **Epochs:** 10
- **Device:** CUDA preferred for faster training

## 📈 Results

### Performance Metrics

- **Final Training Accuracy:** 77.14%
- **Final Test Accuracy:** 77.63%
- **Trainig Time:** ~20 min
- **Model Size:** ~25MB

### Training Curves

![Training Curves](../assets/cifar10_training_curves.png)

The training curves demonstrate:

- Steady loss reduction over epochs
- Good generalization (train/test gap)
- Effective regularization preventing overfitting

### Sample Predictions

![Sample Predictions](../assets/cifar10_predictions.png)

Visual evaluation showing model's ability to correctly classify diverse object categories with confidence scores.

## 🧠 What I Learned

**Deep Learning Concepts:**

- Impact of batch normalization on training dynamics
- Dropout as a regularization technique
- Data augmentation for improved generalization
- Color image processing vs. grayscale

**PyTorch Advanced Features:**

- Model state persistence and loading
- Complex transformation pipelines
- GPU acceleration and memory management
- Progress tracking and user experience

**Computer Vision Insights:**

- Natural image classification challenges
- Feature hierarchy in deep networks
- Importance of data preprocessing
- Trade-offs between model complexity and performance

## Comparison with Benchmarks

| Model          | Test Accuracy | Parameters | Training Time |
| -------------- | ------------- | ---------- | ------------- |
| Basic CNN      | ~60%          | 1M         | ~10 min       |
| **This Model** | **77.63%**    | **6.4M**   | **~20 min**   |
| ResNet-18      | ~95%          | 11M        | ~30 min       |

## 📚 References

- [CIFAR-10 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)
- [Batch Normalization Paper](https://arxiv.org/abs/1502.03167)
- [Dropout: A Simple Way to Prevent Neural Networks from Overfitting](https://jmlr.org/papers/v15/srivastava14a.html)
- [PyTorch Vision Documentation](https://pytorch.org/vision/)

---

_Advanced computer vision project demonstrating modern CNN techniques and best practices_
