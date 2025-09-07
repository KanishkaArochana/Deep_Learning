
# 📘 TensorFlow vs NumPy in Deep Learning

## ❓ Why Not Use NumPy for Deep Learning?
NumPy is a powerful numerical library, but it lacks key features required for efficient deep learning:

- ❌ **No GPU Support**  
  NumPy runs only on CPU. Deep learning models are computationally expensive and require parallel processing, which is best handled by GPUs.

- ❌ **No Automatic Differentiation**  
  Deep learning requires gradient calculation (backpropagation). NumPy doesn't support auto-grad, which means you must compute gradients manually.

- ❌ **No Built-in Neural Network Layers**  
  TensorFlow has built-in layers (Dense, Conv2D, etc.) for building models. NumPy doesn’t provide this abstraction.

---

## ✅ Why Use TensorFlow?
- ✅ **GPU/TPU Acceleration**
- ✅ **Automatic Differentiation**
- ✅ **High-Level APIs (Keras)**
- ✅ **Scalable and Production-Ready**

---

## 🔢 What Are Tensors?
A **Tensor** is a multi-dimensional array — generalization of scalars, vectors, and matrices.

### Tensor Rank Examples:

| Tensor | Description | Example Shape |
|--------|-------------|---------------|
| 0D     | Scalar      | `()` |
| 1D     | Vector      | `(3,)` |
| 2D     | Matrix      | `(3, 4)` |
| 3D     | 3D Tensor (e.g. image) | `(3, 4, 5)` |
| nD     | n-dimensional array | `(d1, d2, ..., dn)` |

👉 Tensors are the core data structure in TensorFlow, similar to NumPy arrays but with GPU/TPU support and automatic differentiation.

**Visual Example:**
```
Scalar -> Vector -> Matrix -> Tensor
```

---

## 🚀 TensorFlow GPU Support

### ✅ GPU Support Features:
- TensorFlow automatically detects and uses available GPUs.
- Use `tf.config.list_physical_devices('GPU')` to check GPU availability.
- Internally uses **CUDA (NVIDIA)** and **cuDNN** for computation acceleration.

**Example: Check for GPU**
```python
import tensorflow as tf
print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
```

---

## 🧠 Summary
- NumPy is limited to CPU and lacks deep learning tools.
- TensorFlow supports tensors, auto-grad, and GPU acceleration.
- Tensors are the fundamental units of data in deep learning models.
