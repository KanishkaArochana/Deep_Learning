
# 📘 Types of Neural Networks

Neural networks are computing systems inspired by the biological neural networks of the human brain. They are widely used in artificial intelligence for tasks like classification, prediction, and more.

---

## 1. 🤖 Artificial Neural Networks (ANN)

**Use Case**: Works well with **tabular format data** (structured data such as rows and columns in spreadsheets or databases).

### 🧠 Structure:
- Composed of **input layer**, **hidden layers**, and **output layer**.
- Each layer contains **neurons** that apply **activation functions** to produce an output.

### ✅ Applications:
- Predictive analytics
- Fraud detection
- Customer churn prediction

---

## 2. 🧠 Convolutional Neural Networks (CNN)

**Use Case**: Designed to process **visual data** such as **images** and **videos**. Commonly used for tasks like **image classification** and **object detection**.

### 🧩 Layers in CNN:

1. ### 🌀 Convolutional Layer
   - Extracts **features** from the input image using **filters/kernels**.
   - Detects edges, colors, shapes, and other patterns.

2. ### 🧯 Pooling Layer
   - Performs **downsampling** (reducing the spatial size).
   - Helps in reducing **computational complexity** and overfitting.
   - Common types: **Max Pooling**, **Average Pooling**

### ✅ Applications:
- Face recognition
- Self-driving cars (object detection)
- Medical imaging (e.g., tumor detection)

---

## 3. 🔁 Recurrent Neural Networks (RNN)

**Use Case**: Suitable for **sequential data** like **text**, **speech**, and **time series**. Used in tasks involving **contextual memory**.

### 🔄 How it Works:
- Has a **loop mechanism** that allows information to persist.
- Maintains a **hidden state** that captures historical data from previous inputs in the sequence.

### ✅ Applications:
- Natural Language Processing (NLP)
  - Language translation
  - Text auto-completion
  - Sentiment analysis
- Speech recognition
- Time series forecasting
