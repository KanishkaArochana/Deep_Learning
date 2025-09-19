
# 📘 Classification with TensorFlow

## 🔍 What is Classification?

**Classification** is a **Supervised Learning** problem where the model learns to predict **categorical labels** (not continuous values).  
It involves mapping input data to one of several **discrete classes** (categories).

- Output: **Category / Label**
- Example: Predicting if an email is "Spam" or "Not Spam"

---

## 🧩 Types of Classification Problems

### 1. ✅ Binary Classification

- **Definition**: Classification task with **two possible outcomes**.
- **Example**:
  - Email: Spam (1) or Not Spam (0)
  - Disease Detection: Positive or Negative
- **Output shape**: Usually a **single sigmoid neuron** (0 to 1)
- **Loss Function**: `BinaryCrossentropy`

#### TensorFlow Model Example:
```python
model = tf.keras.Sequential([
    tf.keras.layers.Dense(10, activation='relu'),
    tf.keras.layers.Dense(1, activation='sigmoid')  # binary output
])
model.compile(loss=tf.keras.losses.BinaryCrossentropy(),
              optimizer=tf.keras.optimizers.Adam(),
              metrics=['accuracy'])
```

---

### 2. 🔢 Multi-class Classification

- **Definition**: Classification task with **more than two possible classes**.
- **Example**:
  - Digit recognition: 0–9 (10 classes)
  - Fruit type: Apple, Banana, Orange
- **Output shape**: One neuron per class with **softmax activation**
- **Loss Function**: `CategoricalCrossentropy` or `SparseCategoricalCrossentropy`

> Use `CategoricalCrossentropy` when labels are **one-hot encoded**  
> Use `SparseCategoricalCrossentropy` when labels are **integer encoded**

#### TensorFlow Model Example:
```python
model = tf.keras.Sequential([
    tf.keras.layers.Dense(64, activation='relu'),
    tf.keras.layers.Dense(10, activation='softmax')  # 10 classes
])
model.compile(loss=tf.keras.losses.SparseCategoricalCrossentropy(),
              optimizer=tf.keras.optimizers.Adam(),
              metrics=['accuracy'])
```

---

## 🧠 Key Concepts

| Concept           | Binary Classification | Multi-class Classification        |
|------------------|-----------------------|-----------------------------------|
| Output Layer     | 1 neuron (sigmoid)    | N neurons (softmax)               |
| Labels Format    | 0/1 (binary)          | Integer or One-hot encoded vector |
| Loss Function    | BinaryCrossentropy    | SparseCategoricalCrossentropy     |
| Activation       | Sigmoid               | Softmax                           |
