# CNN Architecture Documentation

## Overview

This document explains a simple Convolutional Neural Network (CNN) step-by-step. The network input is a **64 × 64 × 3** RGB image. It uses two convolution layers, two pooling layers, and three fully connected layers (including the final output).

---

# How to compute output size

For a convolution or pooling step, use:

```
Output = ((W - F + 2P) / S) + 1
```

Where:

- W = input width (or height)
- F = filter (kernel) size
- P = padding
- S = stride

Example: for Conv1 with W=64, F=5, P=0, S=1 → (64-5+0)/1 + 1 = 60.

---

# Layer-by-layer breakdown

## Input

- **Shape:** 64 × 64 × 3 (H × W × C)

## Conv1

- **Filter size:** 5 × 5
- **Stride:** 1
- **Padding:** 0 (valid)
- **Number of filters:** 10
- **Output shape:** 60 × 60 × 10
  - Calculation: (64 - 5)/1 + 1 = 60
- **Parameters:**
  - Weights = 5 × 5 × 3 × 10 = 750
  - Biases = 10
  - **Total = 750 + 10 = 760**

## Pool1

- **Type:** Pooling (3 × 3), stride = 3, padding = 0
- **Output shape:** 20 × 20 × 10
  - Downsampled from 60 × 60 by factor 3
- **Parameters:** 0 (pooling has no trainable parameters)

## Conv2

- **Filter size:** 5 × 5
- **Stride:** 1
- **Padding:** 0
- **Number of filters:** 16
- **Input channels:** 10 (from previous layer)
- **Output shape:** 16 × 16 × 16
  - Calculation: (20 - 5)/1 + 1 = 16
- **Parameters:**
  - Weights = 5 × 5 × 10 × 16 = 4,000
  - Biases = 16
  - **Total = 4,000 + 16 = 4,016**

## Pool2

- **Type:** Pooling (2 × 2), stride = 2, padding = 0
- **Output shape:** 8 × 8 × 16
- **Parameters:** 0

## Flatten

- Flatten 8 × 8 × 16 = **1024** units

## Fully Connected 1 (FC1)

- **Input units:** 1024
- **Output units:** 128
- **Parameters:**
  - Weights = 1024 × 128 = 131,072
  - Biases = 128
  - **Total = 131,072 + 128 = 131,200**

## Fully Connected 2 (FC2)

- **Input units:** 128
- **Output units:** 16
- **Parameters:**
  - Weights = 128 × 16 = 2,048
  - Biases = 16
  - **Total = 2,048 + 16 = 2,064**

## Output layer (Sigmoid)

- **Input units:** 16
- **Output units:** 1 (binary classification)
- **Activation:** Sigmoid
- **Parameters:**
  - Weights = 16 × 1 = 16
  - Bias = 1
  - **Total = 16 + 1 = 17**

---

# Parameters summary

| Layer          | Parameters  |
| -------------- | ----------- |
| Conv1          | 760         |
| Pool1          | 0           |
| Conv2          | 4,016       |
| Pool2          | 0           |
| Flatten        | 0           |
| FC1 (1024→128) | 131,200     |
| FC2 (128→16)   | 2,064       |
| Output (16→1)  | 17          |
| **Total**      | **138,057** |

---

# Shapes summary

| Layer   | Output shape |
| ------- | ------------ |
| Input   | 64 × 64 × 3  |
| Conv1   | 60 × 60 × 10 |
| Pool1   | 20 × 20 × 10 |
| Conv2   | 16 × 16 × 16 |
| Pool2   | 8 × 8 × 16   |
| Flatten | 1024         |
| FC1     | 128          |
| FC2     | 16           |
| Output  | 1            |

---

# Simple Keras implementation (example)

```python
from tensorflow.keras import Sequential
from tensorflow.keras.layers import Conv2D, MaxPooling2D, Flatten, Dense

model = Sequential([
    Conv2D(10, (5,5), strides=1, padding='valid', activation='relu', input_shape=(64,64,3)),
    MaxPooling2D(pool_size=(3,3), strides=3),
    Conv2D(16, (5,5), strides=1, padding='valid', activation='relu'),
    MaxPooling2D(pool_size=(2,2), strides=2),
    Flatten(),
    Dense(128, activation='relu'),
    Dense(16, activation='relu'),
    Dense(1, activation='sigmoid')
])

model.summary()
```

---

# Notes & tips (short)

- **Where params are used:** Most parameters are in the first big FC layer (FC1). Convolutional layers usually have far fewer parameters.
- **To reduce params:** Use Global Average Pooling or smaller fully connected layers.
- **Common improvements:** Add Batch Normalization, Dropout (for regularization), and use ReLU activations between layers.
- **Pooling vs. stride conv:** You can replace pooling with a convolution that uses stride > 1.

---

If you want, I can also:

- Provide a PyTorch version of the code
- Convert this document to PDF
- Add diagrams for each layer

Tell me which one you want next.

