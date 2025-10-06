
# Normalization in Deep Learning

## 1. What is Normalization?
**Normalization** is the process of scaling numerical data into a specific range, typically **0 to 1**, to make all features contribute equally during training.  
- **Example:** For each column, values are scaled between 0 and 1.  

**Formula (Min-Max Normalization):**  
\[
x_{norm} = \frac{x - x_{min}}{x_{max} - x_{min}}
\]

---

## 2. What is Standardization?
**Standardization** transforms data so that it has:  
- Mean (**μ**) = 0  
- Standard deviation (**σ**) = 1  

**Formula:**  
\[
x_{std} = \frac{x - \mu}{\sigma}
\]

---

## 3. Importance of Normalization in Deep Learning
- **Faster convergence:** Helps the model find optimal parameters quickly.  
- **Better performance:** Prevents some features from dominating others due to larger values.  
- **Less epochs needed:** Speeds up training.  

---

# Batch Normalization (BN)

## 1. What is Batch Normalization?
**Batch Normalization** is a technique to normalize the inputs of each layer in a neural network **for each mini-batch**, not just the raw dataset.  

It keeps the **mean close to 0** and **variance close to 1** within each mini-batch, making training more stable and faster.

---

## 2. Why Use Batch Normalization?
- **Stabilizes learning:** Reduces the effect of internal covariate shift (changes in data distribution across layers during training).  
- **Faster training:** Allows higher learning rates without instability.  
- **Regularization effect:** Reduces overfitting in some cases.  
- **Improved performance:** Leads to better accuracy and convergence.

---

## 3. How Batch Normalization Works
For each mini-batch:
1. **Calculate mean**  
\[
\mu_B = \frac{1}{m} \sum_{i=1}^m x_i
\]
2. **Calculate variance**  
\[
\sigma_B^2 = \frac{1}{m} \sum_{i=1}^m (x_i - \mu_B)^2
\]
3. **Normalize**  
\[
\hat{x_i} = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \epsilon}}
\]
4. **Scale & shift** (learnable parameters)  
\[
y_i = \gamma \hat{x_i} + \beta
\]  

Where:
- **γ (gamma)** = scaling factor (learned during training)  
- **β (beta)** = shifting factor (learned during training)  
- **ε** = small constant to avoid division by zero  

---

## 4. Benefits Summary
- Reduces internal covariate shift  
- Makes training more stable  
- Speeds up convergence  
- Can act as a form of regularization  
