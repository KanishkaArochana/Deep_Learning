
# Data Augmentation

## What is Data Augmentation?
Data Augmentation is a technique to artificially increase the diversity of a dataset by creating modified versions of existing data.  
For example, a single image can be transformed in different ways such as:  
- **Zoom**  
- **Rotate**  
- **Crop**  
- **Add noise**  
- **Blur**  
- **Flip**  
- **Change brightness/contrast**  

It is most commonly used in **Computer Vision tasks** (especially in **CNN models**) to improve model performance.  

---

## Why Use Data Augmentation?
1. **Increase Data** – Helps create more training samples without collecting new data.  
2. **Better Generalization** – Model can handle variations in real-world situations.  
3. **Prevent Overfitting** – Reduces the risk of the model memorizing the training data.  
4. **Handle Different Conditions** – The model can adapt to changes like lighting, angle, zoom, and noise.  

---

## Example in Computer Vision (CNN)
```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator

datagen = ImageDataGenerator(
    rotation_range=20,
    width_shift_range=0.2,
    height_shift_range=0.2,
    zoom_range=0.2,
    horizontal_flip=True
)
```

---

✅ **Summary:**  
Data Augmentation is an essential step in deep learning, especially in computer vision, to make models more robust and capable of recognizing patterns in diverse real-world scenarios.  
