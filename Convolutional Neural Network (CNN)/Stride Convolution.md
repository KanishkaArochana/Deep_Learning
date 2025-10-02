
# Stride in Convolution

## 1. What is Stride?
- **Stride** is the number of pixels the convolution filter (kernel) moves each time it slides over the input image or feature map.  
- In simple words, it’s **"how far the filter jumps"** when scanning the image.  
- Stride is denoted by **S**.

---

## 2. Why use Stride?
- To **control the size** of the output feature map.  
- A **larger stride** means:
  - Smaller output feature map (more downsampling).
  - Less computation (faster processing).
- A **smaller stride** means:
  - Larger output feature map (more details preserved).
  - More computation (slower).

---

## 3. Stride = 1
- **S = 1** means the filter moves **1 pixel at a time**:
  - **Left to right** → move 1 pixel each step.
  - **Top to bottom** → move 1 pixel each step.
- This preserves **maximum spatial details** in the output.
- Output size is slightly smaller than the input (unless padding is applied).

---

## 4. Stride > 1
- **Example:** S = 2 → Filter moves **2 pixels at a time**.
- This **skips** some input pixels and reduces output size.  
- **Problem:**  
  - If the stride causes a non-integer coverage (e.g., 2.5 → 2), some pixels are **missed**.  
  - This loss of pixel information can **reduce feature extraction quality** and cause the model to miss important patterns.

---

## 5. Formula for Output Size
If:
- \( n \) = input size (height/width)  
- \( f \) = filter size  
- \( p \) = padding size  
- \( s \) = stride  

Then:
\[
\text{Output size} = \frac{n - f + 2p}{s} + 1
\]

⚠️ **If the result is not an integer, some pixels are ignored.**

---

## Summary Table

| Stride (S) | Effect | Pros | Cons |
|------------|--------|------|------|
| 1 | Moves 1 pixel at a time | Preserves details | More computation |
| 2 | Moves 2 pixels at a time | Faster, smaller output | Skips pixels, loses details |
| >2 | Large jumps | Very fast | High information loss |
