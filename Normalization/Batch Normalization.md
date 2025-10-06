
# **Batch Normalization (BN) – Documentation**

## **1. Introduction**
Batch Normalization is a deep learning technique that normalizes the inputs of each layer within a mini-batch during training.  
It helps speed up learning, stabilize the training process, and acts as a form of regularization.

---

## **2. Purpose of Batch Normalization**
BN is mainly used for:

- **Faster Convergence** – Reduces the number of epochs required for training.
- **Stabilizes Training** – Minimizes oscillations in gradients.
- **Regularization** – Acts as a mild regularizer, reducing overfitting.

---

## **3. Why Use Batch Normalization?**
### Problem:
- **Internal Covariate Shift** (often referred to as *Input Covariance Shift*)  
  - During training, the distribution of inputs to a layer keeps changing as parameters of previous layers update.
  - This forces each layer to constantly adapt to new input distributions, slowing down learning.

### Solution:
- **Batch Normalization**  
  - Keeps the distribution of activations more stable during training.
  - Normalizes activations to have a **mean of 0** and **standard deviation of 1** for each mini-batch.

---

## **4. Mathematical Process**
For each mini-batch:
1. **Calculate Mean**  
   \[
   \mu_B = \frac{1}{m} \sum_{i=1}^m x_i
   \]

2. **Calculate Variance**  
   \[
   \sigma_B^2 = \frac{1}{m} \sum_{i=1}^m (x_i - \mu_B)^2
   \]

3. **Normalize**  
   \[
   \hat{x}_i = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \epsilon}}
   \]  
   (\(\epsilon\) is a small value to avoid division by zero)

4. **Scale & Shift** *(learnable parameters)*  
   \[
   y_i = \alpha \cdot \hat{x}_i + \beta
   \]  

---

## **5. Scaling (\(\alpha\)) and Shifting (\(\beta\))**
- **\(\alpha\) (Gamma)** – Controls the scale of normalized values.  
  - If \(\alpha > 1\), outputs are stretched.  
  - If \(\alpha < 1\), outputs are compressed.
- **\(\beta\) (Beta)** – Controls the shift (offset).  
  - Allows the network to reintroduce a non-zero mean if needed.

Both \(\alpha\) and \(\beta\) are **trainable parameters** that get updated through **backpropagation**, just like weights and biases.

---

## **6. How Each Neuron Gets \(\alpha\) and \(\beta\)**
- In **fully connected layers**, each neuron has its own **\(\alpha\) and \(\beta\)** values.
- In **convolutional layers**, each **feature map** (channel) has a single \(\alpha\) and \(\beta\) shared across spatial locations.
- These parameters are updated every training step.

---

## **7. Key Benefits**
✅ Faster training.  
✅ Reduces sensitivity to initialization.  
✅ Helps avoid vanishing/exploding gradients.  
✅ Provides mild regularization (reducing dropout need).

---

## **8. Visual Summary**
**Problem:** Input distribution keeps shifting → slows learning.  
**BN Solution:** Normalize → Scale (\(\alpha\)) → Shift (\(\beta\)) → Stable and faster training.
