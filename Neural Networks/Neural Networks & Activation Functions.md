# 🧠 Neural Networks & Activation Functions – Documentation

## 📌 1. What is a Neuron?
A **neuron** is the fundamental building block of a neural network. It is a computational unit inspired by biological neurons. It:

- Takes one or more input values.
- Applies weights and bias to inputs.
- Passes the result through an **activation function**.
- Produces an output.

**Mathematically:**  
`Output = ActivationFunction(W·X + b)`

Where:
- **W** = weights  
- **X** = input  
- **b** = bias

---

## 📌 2. What is a Neural Network?
A **Neural Network** is a collection of interconnected **artificial neurons** arranged in layers:

- **Input Layer**: Takes raw data as input.
- **Hidden Layers**: Perform computations and feature extraction.
- **Output Layer**: Produces the final prediction.

Neural networks are used in tasks like image recognition, natural language processing, and classification problems.

---

## 📌 3. What is an Activation Function?
An **activation function** defines the output of a neuron given an input or set of inputs. It introduces **non-linearity** into the model, allowing the network to learn complex patterns.

---

## ⚙️ 4. Common Artificial Neuron Activation Functions

### 🔹 1. Sigmoid Function
- **Formula:**  
  `f(x) = 1 / (1 + e^(-x))`
- **Range:** (0, 1)
- **Use Case:** Binary classification (2 classes)
- **Examples:**
  - Spam vs. Not Spam  
  - Rain vs. No Rain  
  - Dog vs. Cat  

✅ Smooth gradient  

✅ Graph:

![Sigmoid Graph](https://upload.wikimedia.org/wikipedia/commons/8/88/Logistic-curve.svg)


---

### 🔹 2. Tanh (Hyperbolic Tangent) Function
- **Formula:**  
  `f(x) = tanh(x) = (e^x - e^(-x)) / (e^x + e^(-x))`
- **Range:** (-1, +1)
- **Use Case:** Situations where outputs can be positive or negative
- **Advantage:** Stronger gradients than Sigmoid for negative inputs

✅ Centered at zero 

✅ Graph: 

![Tanh Graph](https://upload.wikimedia.org/wikipedia/commons/c/cb/Activation_tanh.svg)

---

### 🔹 3. ReLU (Rectified Linear Unit)
- **Formula:**  
  `f(x) = max(0, x)`
- **Range:** [0, ∞)
- **Use Case:** Default in most deep learning models (fast and simple)

✅ Efficient and widely used  

✅ Graph:

![ReLU Graph](https://upload.wikimedia.org/wikipedia/commons/6/6c/Rectifier_and_softplus_functions.svg)


---

### 🔸 Leaky ReLU (Solution to Dying ReLU)
- **Formula:**  
  ```
  f(x) = {
      x      if x > 0
      α·x    if x ≤ 0
  }
  ```
  Typically: α = 0.01

- Allows a small gradient when `x < 0`

✅ Helps avoid dying ReLU  
✅ Retains simplicity of ReLU


✅ Graph:
![Leaky ReLU Graph](https://upload.wikimedia.org/wikipedia/commons/f/fe/Activation_prelu.svg)


---

### 🔹 4. Softmax Function
- **Formula:**  
  `Softmax(z_i) = e^(z_i) / Σ e^(z_j)`
- **Range:** (0, 1), and all outputs sum to 1
- **Use Case:** Multi-class classification problems
- **Examples:**
  - Classifying among Dog, Cat, Rabbit
  - Digit recognition (0–9)

✅ Converts outputs into probabilities  
✅ Good for final layer in multi-class models


✅ Graph:

![Softmax Graph](https://upload.wikimedia.org/wikipedia/commons/5/5f/Softmax-function.svg)



---

## ✅ Summary Table

| Activation Function | Output Range | Use Case                    | Issues               |
|---------------------|--------------|-----------------------------|----------------------|
| Sigmoid             | (0, 1)       | Binary classification       | Vanishing gradient   |
| Tanh                | (-1, 1)      | Positive/negative outputs   | Vanishing gradient   |
| ReLU                | [0, ∞)       | Default for hidden layers   | Dying ReLU           |
| Leaky ReLU          | (-∞, ∞)      | Fix for ReLU issue          | Slight complexity    |
| Softmax             | (0, 1), sum=1| Multi-class classification  | Slower, soft output  |