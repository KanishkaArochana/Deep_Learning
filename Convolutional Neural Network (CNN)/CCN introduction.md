
# **Convolutional Neural Network (CNN) Documentation**

## **1. Why Can’t We Use a Normal Neural Network for Image Processing?**

A normal neural network (Fully Connected Network) is **not ideal** for image processing because:

1. **High number of parameters**  
   - Images have many pixels (e.g., 256×256×3 = 196,608 values).  
   - A fully connected layer connects each pixel to every neuron, leading to **millions of weights** → slow training and high memory usage.

2. **Loss of spatial relationships**  
   - In images, nearby pixels are related (edges, shapes).  
   - A normal NN flattens images into a vector, **losing spatial patterns**.

3. **Overfitting risk**  
   - Too many parameters → network memorizes training data instead of generalizing.

4. **No translation invariance**  
   - A normal NN doesn’t recognize that the same object shifted slightly is still the same object.

✅ CNNs solve these problems by **sharing weights** and **preserving spatial structure**.

---

## **2. What is a Convolutional Neural Network (CNN)?**

A **Convolutional Neural Network** is a type of deep learning model designed for **image recognition and processing**.  
It uses **convolutional layers** to extract spatial features (edges, textures, shapes) and learns **hierarchical patterns**.

---

## **3. CNN Architecture**

A typical CNN consists of the following layers:

### **1. Input Layer**
- Accepts the image (e.g., 32×32×3 for RGB image).

---

### **2. Convolutional Layer**
- Applies **filters (kernels)** that slide over the image to detect patterns.
- **Operation:**  
  \( Feature\ Map = Image * Filter \) (where * is convolution)
- Example: Detect edges, corners, textures.
- **Benefits:** Fewer parameters (weight sharing) & preserves spatial info.

---

### **3. Activation Function (ReLU)**
- Applies non-linearity after convolution.
- Formula: \( f(x) = \max(0, x) \)
- Removes negative values, making model faster and preventing saturation.

---

### **4. Pooling Layer (Subsampling)**
- Reduces size of feature maps → less computation.
- Types:
  - **Max Pooling**: Takes max value from a region.
  - **Average Pooling**: Takes average value.
- Example: 2×2 max pooling halves width & height.

---

### **5. Fully Connected Layer (Dense Layer)**
- Flattens pooled features into a vector.
- Connects to neurons for classification.
- Example: In digit recognition, output size = 10 for digits 0–9.

---

### **6. Output Layer**
- Uses **Softmax** (for classification) to output probabilities for each class.

---

## **4. Example CNN Flow**
1. **Input:** 32×32×3 image  
2. **Conv Layer:** 28×28×8 (8 filters)  
3. **ReLU**  
4. **Max Pooling:** 14×14×8  
5. **Conv Layer:** 10×10×16  
6. **ReLU**  
7. **Max Pooling:** 5×5×16  
8. **Flatten** → 400 values  
9. **Fully Connected Layer** → 120 neurons  
10. **Output Layer** → e.g., 10 neurons for classification

---

## **5. Key Advantages of CNN**
- **Fewer parameters** than normal NN.
- **Learns local patterns** and builds to complex ones.
- **Translation invariance** (detects objects anywhere).
- **Better accuracy** in image classification, detection, segmentation.
