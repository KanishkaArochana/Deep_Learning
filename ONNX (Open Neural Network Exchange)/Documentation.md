# ONNX (Open Neural Network Exchange)

## What is ONNX?
ONNX (Open Neural Network Exchange) is an open-source format for representing machine learning models.  
It enables interoperability between different deep learning frameworks such as:

- PyTorch
- TensorFlow
- Keras
- Caffe2
- MXNet

With ONNX, you can train a model in one framework and deploy it in another.

---

## Key Features
- **Framework Interoperability**: Transfer models between frameworks without retraining.  
- **Pre-trained Model Sharing**: Share and reuse models across tools.  
- **Hardware Compatibility**: Run models on various hardware backends.  
- **Optimization Support**: Support for inference optimizations like quantization, pruning, and fusion.  

---

## ONNX Model Optimization
ONNX models can be optimized to improve performance and reduce size during inference.

### 1. Quantization
Quantization is the process of reducing the precision of the numbers used to represent a model's parameters.  
It helps:
- Reduce model size  
- Speed up inference  
- Decrease memory usage  

#### Types of Quantization
- **Post-Training Quantization (PTQ)**  
  Quantize a model after training using calibration data.  
- **Quantization-Aware Training (QAT)**  
  Simulates quantization during training to improve accuracy after deployment.  

#### Common Data Types
- float32 → int8 or uint8  
- float32 → float16  

---

## ONNX Quantization Tools
- **ONNX Runtime**: Includes built-in support for quantization.  
- **ONNX Quantization Toolkit (`onnxruntime.quantization`)**  

```python
from onnxruntime.quantization import quantize_dynamic, QuantType

quantized_model = quantize_dynamic(
    model_input="model.onnx",
    model_output="model_quant.onnx",
    weight_type=QuantType.QInt8
)
```

---

## Example Workflow
1. Train a model in PyTorch  
2. Export to ONNX format using `torch.onnx.export()`  
3. Apply quantization using ONNX Runtime  
4. Deploy the quantized model on edge devices  

---

## Benefits of Using ONNX + Quantization

| Feature           | Benefit                          |
|-------------------|----------------------------------|
| Interoperability  | Cross-framework model use        |
| Efficiency        | Faster inference, smaller size   |
| Portability       | Easy deployment on various devices |
