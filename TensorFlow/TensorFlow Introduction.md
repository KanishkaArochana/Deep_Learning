
# Transfer Learning

## What is Transfer Learning?  
Transfer Learning is a machine learning technique where a **pre-trained model** (trained on a large dataset) is reused to train a **new model** for a different but related task.  

Instead of training from scratch, the model starts with learned features and adapts them to the new problem.  

**Example Models:**  
- **Xception** – Image classification tasks.  
- **VGG16 / VGG19** – General image recognition.  
- **ResNet (ResNet50, ResNet101)** – Object detection and classification.  
- **InceptionV3** – Image classification and feature extraction.  
- **BERT** – Natural Language Processing tasks like text classification.  
- **GPT** – Text generation and summarization.  
- **YOLO** – Object detection in images/videos.  

---

## Advantages  
- **Faster Training** – Needs fewer epochs to achieve good performance.  
- **Works with Small Datasets** – Effective even if the new dataset is small.  
- **Better Accuracy** – Benefits from features learned from large, high-quality datasets.  
- **Lower Computational Cost** – Reduces required computing power compared to training from scratch.  

---

## How it Works  
1. **Select a Pre-trained Model** (e.g., Xception, ResNet, VGG, BERT).  
2. **Freeze** initial layers to keep already-learned features.  
3. **Replace** the final layer(s) to match the new task (e.g., number of output classes).  
4. **Fine-tune** only the last few layers (or more if needed).  
