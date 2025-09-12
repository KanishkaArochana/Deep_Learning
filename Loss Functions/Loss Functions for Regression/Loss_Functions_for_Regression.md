# 📘 Loss Functions for Regression

## 🔍 What is a Loss Function?

A **loss function** is a mathematical function used to measure the difference between the predicted values by a model and the actual values in a dataset.  
In regression tasks, loss functions help in **evaluating how well a model is performing** and guide the optimization process (e.g., during gradient descent).

---

## 📉 Common Loss Functions for Regression

### 1. **Mean Squared Error (MSE)**

**Formula:**  
\[
\text{MSE} = \frac{1}{n} \sum_{i=1}^{n}(y_i - \hat{y}_i)^2
\]

- Calculates the **average of the squared differences** between actual and predicted values.
- **Sensitive to outliers** – large errors are penalized more heavily.
- Works well when **noise is minimal**.
- Commonly used in linear regression and many other algorithms.

**⚠️ Note:**  
MSE does **not handle noise points well** (outliers can skew results significantly).

---

### 2. **Mean Absolute Error (MAE)**

**Formula:**  
\[
\text{MAE} = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|
\]

- Calculates the **average of the absolute differences** between actual and predicted values.
- **Less sensitive to outliers** than MSE.
- Provides a more **robust evaluation** in noisy datasets.
- The error is **linearly penalized**.

---

### 3. **Huber Loss**

**Formula:**  
\[
L_\delta(y, \hat{y}) = 
\begin{cases}
\frac{1}{2}(y - \hat{y})^2 & \text{for } |y - \hat{y}| \leq \delta \\
\delta \cdot (|y - \hat{y}| - \frac{1}{2}\delta) & \text{otherwise}
\end{cases}
\]

- **Combination of MSE and MAE**:
  - Acts like MSE when the error is small (less than δ).
  - Acts like MAE when the error is large (more than δ).
- **Balances sensitivity** and **robustness**.
- Used when the dataset has **moderate noise**.

---

## ✅ Summary Table

| Loss Function | Handles Noise? | Penalizes Outliers | Type          |
|---------------|----------------|--------------------|---------------|
| MSE           | ❌ No           | ❗ High             | Quadratic     |
| MAE           | ✅ Yes          | ➖ Medium           | Linear        |
| Huber Loss    | ✅ Yes          | ⚖ Balanced         | Mixed (MSE + MAE) |