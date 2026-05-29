# Tiny ImageNet Benchmark

## Overview

This project benchmarks three state-of-the-art convolutional neural network architectures using transfer learning and fine-tuning on the Tiny ImageNet dataset.

The objective was not only to maximize classification accuracy, but to investigate how different pretrained architectures behave under identical training conditions.

Architectures evaluated:

- MobileNetV2
- ResNet50
- EfficientNetB0

The project focuses on model efficiency, generalization, computational cost and architecture behavior.

---

## Dataset

Dataset: Tiny ImageNet

Characteristics:

- 200 classes
- 100,000 training images
- 10,000 validation images
- RGB images

Images were resized to:

```text
96x96
```

to balance feature extraction quality and computational efficiency.

---

## Objective

The goal of this benchmark was to answer the following question:

> Which architecture provides the best balance between accuracy, efficiency and computational cost on Tiny ImageNet?

Rather than evaluating a single model, the project compares multiple architectures under the same experimental setup.

---

## Methodology

All models followed the same workflow:

1. Load ImageNet pretrained weights
2. Train custom classification head
3. Fine-tune selected backbone layers
4. Evaluate validation performance

To ensure a fair comparison, all architectures were trained using the same general pipeline.

---

## Experimental Setup

Configuration:

```text
Image Size: 96x96
Batch Size: 64
Optimizer: Adam
Mixed Precision: Enabled
Transfer Learning: Yes
Fine-Tuning: Yes
Data Augmentation: Yes
Early Stopping: Yes
Learning Rate Scheduling: Yes
```

Data augmentation included:

- Random Flip
- Random Rotation
- Random Zoom
- Random Contrast

---

## Models Evaluated

### MobileNetV2

Lightweight architecture optimized for efficiency and low computational cost.

---

### ResNet50

Deep residual architecture designed for strong feature extraction and large-scale image recognition tasks.

---

### EfficientNetB0

Modern architecture focused on balancing depth, width and resolution while maintaining computational efficiency.

---

## Results

| Model | Validation Accuracy | Validation Loss |
|---------|---------:|---------:|
| MobileNetV2 | 67.69% | 1.2911 |
| ResNet50 | 61.59% | 1.5682 |
| EfficientNetB0 | 59.91% | 1.7078 |

---

## Best Model

### MobileNetV2

MobileNetV2 achieved the best overall performance.

```text
Validation Accuracy: 67.69%
Validation Loss: 1.2911
```

The model provided the strongest balance between:

- accuracy
- training stability
- computational efficiency
- generalization

---

## Architecture Analysis

### MobileNetV2

The lightweight architecture adapted extremely well to the experimental setup.

Its lower complexity allowed efficient feature extraction while maintaining strong validation performance.

---

### ResNet50

ResNet50 achieved competitive performance but did not surpass MobileNetV2.

This suggests that the additional complexity of the architecture was not fully exploited under the current constraints.

Possible contributing factors:

- reduced image resolution
- partial fine-tuning
- increased computational complexity

---

### EfficientNetB0

Although EfficientNetB0 is a highly optimized architecture, it produced the lowest validation accuracy in this benchmark.

This result suggests that the model may require a different fine-tuning strategy or training configuration to fully exploit its potential on Tiny ImageNet.

---

## Key Findings

### 1. Efficient Architectures Can Outperform Larger Models

MobileNetV2 outperformed both ResNet50 and EfficientNetB0 despite being the lightest architecture evaluated.

---

### 2. Bigger Models Are Not Automatically Better

The benchmark demonstrated that model complexity alone does not guarantee superior performance.

Architecture selection should always consider:

- dataset characteristics
- computational cost
- image resolution
- deployment constraints

---

### 3. Performance Must Be Evaluated Holistically

The best model is not necessarily the most complex one.

Effective model selection requires balancing:

- accuracy
- efficiency
- stability
- training cost

---

## Skills Demonstrated

- Deep Learning
- Transfer Learning
- Fine-Tuning
- TensorFlow / Keras
- Experimental Design
- Benchmarking
- Architecture Comparison
- Mixed Precision Training
- Performance Analysis
- Model Evaluation

---

## Conclusion

This project demonstrates a complete transfer learning benchmark using three major CNN architectures on Tiny ImageNet.

Beyond comparing validation accuracy, the benchmark provides practical insights into architecture behavior, computational efficiency and model selection.

The most important conclusion was that MobileNetV2 delivered the best overall tradeoff between performance and efficiency, outperforming heavier architectures under the same experimental conditions.

The project highlights a key machine learning engineering principle:

> The best model is not always the largest model, but the model that best fits the problem constraints.
