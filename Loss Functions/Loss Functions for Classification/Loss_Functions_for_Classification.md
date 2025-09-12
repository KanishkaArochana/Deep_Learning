
# 📘 Loss Functions for Classification

## ❓ What is a Loss Function?

A **loss function** is a method of evaluating how well your classification algorithm models your dataset. If predictions are far from the actual results, the loss function will output a higher number. It helps in:
- Measuring the error between predicted and actual values.
- Optimizing model weights during training via backpropagation.

---

## 🔢 Types of Loss Functions for Classification

### 1️⃣ Binary Cross Entropy
- **Use Case:** Binary classification problems (2 classes).
- **Formula:**

  \[
  \text{Loss} = -[y \cdot \log(\hat{y}) + (1 - y) \cdot \log(1 - \hat{y})]
  \]

- **Explanation:**
  - \( y \): true label (0 or 1)
  - \( \hat{y} \): predicted probability (between 0 and 1)
- **Application:** Used when output layer has a single neuron with sigmoid activation.

---

### 2️⃣ Categorical Cross Entropy
- **Use Case:** Multi-class classification problems (more than 2 classes) where target labels are **one-hot encoded**.
- **Formula:**

  \[
  \text{Loss} = -\sum_{i=1}^{C} y_i \cdot \log(\hat{y}_i)
  \]

- **Explanation:**
  - \( C \): number of classes
  - \( y_i \): true one-hot encoded label for class \( i \)
  - \( \hat{y}_i \): predicted probability for class \( i \)
- **Application:** Used with a softmax activation function in the output layer.

---

### 3️⃣ Sparse Categorical Cross Entropy
- **Use Case:** Multi-class classification problems where target labels are **integer encoded** instead of one-hot encoded.
- **Equivalent To:** Categorical Cross Entropy, but more memory efficient.
- **Explanation:**
  - Input label is a class index (e.g., 0, 1, 2, ...)
  - No need for one-hot encoding.
- **Application:** Used with softmax output but with sparse integer labels.

---

## ✅ Summary Table

| Loss Function                | Classification Type     | Label Format        | Activation Function |
|-----------------------------|--------------------------|---------------------|----------------------|
| Binary Cross Entropy        | Binary (2 classes)       | 0 or 1              | Sigmoid              |
| Categorical Cross Entropy   | Multi-class              | One-hot encoded     | Softmax              |
| Sparse Categorical Cross Entropy | Multi-class         | Integer encoded     | Softmax              |
