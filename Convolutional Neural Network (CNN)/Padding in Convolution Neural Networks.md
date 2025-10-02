
# **Padding in Convolutional Neural Networks (CNNs)**

## **1. What is Padding?**
Padding is the process of adding extra pixels (usually zeros) around the border of an input image before applying a convolution operation.  
These extra pixels do not carry original image information but help control how the convolution works.

---

## **2. Why Use Padding?**

- **Preserve Information at Borders**  
  Without padding, pixels at the edge of an image are used fewer times in convolution, causing loss of information.

- **Control Output Size**  
  Padding can help maintain the same spatial dimensions after convolution instead of shrinking the feature map.

- **Better Feature Learning**  
  Padding allows filters to be applied to corner and border pixels more effectively.

---

## **3. Types of Padding**

### **1. Valid Padding (No Padding)**
- No extra pixels are added around the image.  
- The output feature map becomes **smaller** than the input.  
- Formula:  
  \[
  O = \frac{(W - K)}{S} + 1
  \]
  Where:  
  - \( O \) = Output size  
  - \( W \) = Input size  
  - \( K \) = Kernel size  
  - \( S \) = Stride  

---

### **2. Same Padding (Zero Padding)**
- Extra pixels (usually zeros) are added around the border.  
- Output feature map size is **the same** as input size.  
- Formula for padding size (\( P \)):  
  \[
  P = \frac{(S - 1) \times W - S + K}{2}
  \]
  Where:  
  - \( P \) = Padding size per side  
  - \( W \) = Input size  
  - \( K \) = Kernel size  
  - \( S \) = Stride  

---

## **4. How to Determine Padding Size (P)**

1. **For SAME Padding**:  
   If stride \( S = 1 \):
   \[
   P = \frac{K - 1}{2}
   \]
   Example:  
   - Kernel size = 3  
   - Stride = 1  
   \[
   P = \frac{3 - 1}{2} = 1
   \]  

2. **For VALID Padding**:  
   - \( P = 0 \) (no padding).

---

## **5. Summary Table**

| Padding Type   | Padding Size (P) | Output Size | Purpose |
|----------------|------------------|-------------|---------|
| Valid Padding  | 0                | Smaller     | Reduce size, no extra border info |
| Same Padding   | Formula-based    | Same as input | Preserve size, avoid losing edge info |
