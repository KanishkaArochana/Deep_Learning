# Gradient Descent Algorithm Documentation

## Overview
Gradient Descent is an optimization algorithm used to minimize the cost (loss) function in machine learning models by adjusting the weights and biases in the direction of the negative gradient.

---

## Problem with Gradient Descent
When the dataset is very large:
- **Example**: 100,000 records with 200 parameters
  - Gradient calculations per iteration = `100,000 × 200 = 20,000,000`
- **Issues**:
  - Requires **high computing power**.
  - Consumes **more memory**.
  - Slower training time.

---

## Types of Gradient Descent

### 1. Stochastic Gradient Descent (SGD)
- **Definition**: Updates the weights and biases using only **one random sample** from the training set at each iteration.
- **Process**:
  1. Select a random record from the dataset.
  2. Calculate the gradient for that single record.
  3. Update weights immediately.
- **Advantages**:
  - Fast updates.
  - Can escape local minima due to randomness.
- **Disadvantages**:
  - High variance in updates.
  - Convergence can be noisy.

---

### 2. Batch Gradient Descent
- **Definition**: Uses the **entire dataset** to calculate the gradient before updating the weights.
- **Process**:
  1. Feed the whole dataset into the model.
  2. Calculate the average gradient for all records.
  3. Update weights once per epoch.
- **Advantages**:
  - Stable and precise updates.
- **Disadvantages**:
  - Very slow for large datasets.
  - Requires high memory.

---

### 3. Mini-batch Gradient Descent
- **Definition**: Divides the dataset into **small batches** and updates the weights after processing each batch.
- **Process**:
  1. Split dataset into batches (e.g., batch size = 32, 64, 128).
  2. For each batch:
     - Calculate the gradient.
     - Update weights.
- **Advantages**:
  - Faster than batch gradient descent.
  - More stable than stochastic gradient descent.
  - Efficient GPU usage.
- **Disadvantages**:
  - Batch size must be tuned for best results.

---

## Summary Table

| Type                     | Data Used per Update | Speed     | Stability     | Memory Usage | Best Use Case |
|--------------------------|----------------------|-----------|---------------|--------------|---------------|
| Stochastic GD            | 1 record             | Fastest   | Low           | Very Low     | Very large datasets, online learning |
| Batch GD                 | All records          | Slowest   | High          | High         | Small datasets |
| Mini-batch GD            | Small batch          | Medium    | Medium-High   | Medium       | Large datasets, deep learning |
