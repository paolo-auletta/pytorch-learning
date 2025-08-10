# EMNIST Digit Classification 🔢

A convolutional neural network implementation for handwritten digit recognition using PyTorch and the Extended MNIST dataset.

## 🎯 Project Overview

This project implements a custom CNN architecture to classify handwritten digits (0-9) from the EMNIST dataset. The model achieves robust performance through careful architecture design and proper training procedures.

## 📊 Dataset Information

- **Dataset:** EMNIST (Extended Modified National Institute of Standards and Technology)
- **Split:** Digits (0-9)
- **Training samples:** 240,000 images
- **Test samples:** 40,000 images
- **Image dimensions:** 28×28 grayscale
- **Classes:** 10 (digits 0-9)

## Model Architecture

![CNN Architecture](../assets/emnist_architecture.png)

### Network Structure:

```
Input (1×28×28)
    ↓
Conv2D(1→2, 5×5) → ReLU → MaxPool2D(2×2)
    ↓
Conv2D(2→4, 3×3) → Sigmoid → MaxPool2D(2×2)
    ↓
Flatten → Linear(100→10) → Output
```

**Layer Details:**

- **Layer 1:** 1→2 channels, 5×5 kernel, ReLU activation, 2×2 max pooling
- **Layer 2:** 2→4 channels, 3×3 kernel, Sigmoid activation, 2×2 max pooling
- **Classifier:** Fully connected layer (100→10 classes)

**Parameters:** ~1,274 total trainable parameters

## Training Configuration

- **Optimizer:** Adam (lr=0.01)
- **Loss Function:** CrossEntropyLoss
- **Batch Size:** 32
- **Epochs:** 3
- **Device:** CUDA if available, otherwise CPU

## 📈 Results

### Performance Metrics

- **Final Training Accuracy:** 97.72%
- **Final Test Accuracy:** 97.75%
- **Training Time:** ~3 minutes
- **Model Size:** ~5KB

### Confusion Matrix

![Confusion Matrix](../assets/emnist_confusion_matrix.png)

The confusion matrix reveals:

- Strong performance across all digit classes
- Minimal confusion between similar digits (6/9, 3/8)
- Consistent classification accuracy

## 🧠 What I Learned

**Technical Skills:**

- PyTorch model definition and training loops
- Convolutional layer design and feature extraction
- Loss function selection and optimization strategies
- Model evaluation with confusion matrices

**Machine Learning Concepts:**

- CNN architecture principles for image classification
- Training/validation split importance
- Activation function selection (ReLU vs Sigmoid)
- Batch processing and gradient optimization

**Software Engineering:**

- Clean code structure and documentation
- Modular design for reusability
- Proper error handling and device management

## 📚 References

- [EMNIST: Extending MNIST to handwritten letters](https://arxiv.org/abs/1702.05373)
- [PyTorch Documentation](https://pytorch.org/docs/)
- [Convolutional Neural Networks for Visual Recognition](http://cs231n.github.io/)

---

_Part of my PyTorch learning journey - exploring computer vision fundamentals_
