
# 📘 Regression with TensorFlow

## 🔍 What is Supervised Learning?

**Supervised learning** is a type of machine learning where the model learns from **labeled data** — data that has both input features (`X`) and the correct output (`y`).

There are two main types:

1. **Regression** – Predicts continuous (numeric) values  
   🔹 Example: Predicting house prices, temperature, or sales.

2. **Classification** – Predicts categorical values  
   🔹 Example: Email spam detection (spam or not spam), disease diagnosis (positive or negative).

---

## 📈 What is Regression?

**Regression** is a supervised learning technique used to predict a **continuous** output based on input features.

### ➕ Examples:
- Predicting a person’s weight based on their height.
- Forecasting sales for the next month.
- Estimating the price of a car based on age, mileage, and brand.

---

## ⚙️ How Regression Works in TensorFlow

In TensorFlow, regression can be implemented using simple models like:

```python
import tensorflow as tf

# create a model
model = tf.keras.Sequential([
    tf.keras.layers.Dense(4, input_shape=[1]),
    tf.keras.layers.Dense(1)
])

# compile the model
model.compile(loss=tf.keras.losses.mae,
              optimizer=tf.keras.optimizers.Adam(learning_rate=0.01),
              metrics=["mae"])

# train the model
epoch_number = 10
history = model.fit(tf.expand_dims(X_train, axis=-1), y_train, epochs=epoch_number)
```

---

## 🧮 Common Loss Functions for Regression

- **Mean Squared Error (MSE)**: Measures the average of the squares of the errors.
- **Mean Absolute Error (MAE)**: Measures the average of the absolute differences.

---

## ✅ Use Cases for Regression

- Predicting stock prices
- Forecasting energy consumption
- Modeling trends in data
