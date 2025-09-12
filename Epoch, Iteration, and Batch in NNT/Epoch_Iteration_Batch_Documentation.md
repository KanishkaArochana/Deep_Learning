# 📄 Epoch, Iteration, and Batch in Neural Network Training

## 🔁 Epoch

-   **Definition**: One **Epoch** is when the entire training dataset is
    passed **forward and backward** through the neural network **once**.
-   **Example**: If your training dataset has 35,000 samples, then 1
    epoch means the model has seen all 35,000 samples once.
-   **Note**: More epochs generally help the model learn better, but too
    many can lead to overfitting.

------------------------------------------------------------------------

## 🔄 Iteration

-   **Definition**: An **Iteration** refers to **one update** of the
    model's weights after processing a **single batch** of data.
-   **Relation to Epoch**:

```{=html}
<!-- -->
```
    Iterations per Epoch = Total Samples ÷ Batch Size

-   **Example with Your Data**:
    -   Dataset size: **35,000 samples**
    -   Batch size: **1,000**
    -   Iterations per epoch = **35**
    -   This means in one epoch, weights are updated **35 times**.

------------------------------------------------------------------------

## 📦 Batch

-   **Definition**: A **Batch** is a subset of the training dataset. It
    is used to feed data into the model in manageable chunks instead of
    the whole dataset at once.
-   **Why Use Batches?**
    -   Efficient memory usage
    -   Smoother gradient descent (less noisy than single-sample
        updates)
    -   Faster training compared to using the entire dataset at once
        (especially on GPUs)

------------------------------------------------------------------------

## 🔗 Relationship Summary

If we train a model with: - **Dataset size**: 35,000 samples\
- **Batch size**: 1,000\
- **Epochs**: 5

Then: - Each **Epoch** contains **35 Iterations** (35,000 / 1,000) -
Over **5 Epochs**, the model undergoes **175 Iterations**

------------------------------------------------------------------------

## 📘 Quick Definitions

  ------------------------------------------------------------------------------
  Term            Definition
  --------------- --------------------------------------------------------------
  **Epoch**       One full pass of the dataset through the model

  **Iteration**   One update of weights (after one batch)

  **Batch**       A subset of the dataset used in one iteration
  ------------------------------------------------------------------------------
