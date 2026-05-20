Final Report: Fashion-MNIST Image Classification

1. Project Title
MLP vs CNN for Fashion-MNIST Classification**

2. Problem Statement
Classify grayscale images of clothing items into 10 categories. Useful for automated inventory management and recommendation systems.

3. Dataset
- **Name:** Fashion-MNIST
- **Source:** https://github.com/zalandoresearch/fashion-mnist
- **Size:** 60,000 training images, 10,000 test images
- **Format:** 28×28 grayscale pixels (CSV format)
- **Classes:** T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle boot

4. Data Preprocessing
- Normalized pixel values to [0, 1] (divided by 255.0)
- Reshaped images to 28×28 for visualization and 1×28×28 for CNN
- Split training data into train/validation/test: 80/10/10 (48,006 / 6,000 / 5,994)

5. Model Architectures

Baseline: MLP
- Input: 784 (flattened 28×28)
- Hidden: 128 neurons with ReLU
- Output: 10 classes
- Parameters: ~101,000

Deep Learning: CNN
- Conv1: 1→32 channels, 3×3 kernel, BatchNorm, ReLU, MaxPool
- Conv2: 32→64 channels, 3×3 kernel, BatchNorm, ReLU, MaxPool
- FC1: 64×7×7 → 256, ReLU, Dropout(0.5)
- FC2: 256 → 10
- Parameters: 824,650

6. Training Setup
| Parameter | MLP | CNN |
|-----------|-----|-----|
| Optimizer | Adam | Adam |
| Learning rate | 0.001 | 0.001 |
| Batch size | 64 | 64 |
| Epochs | 20 | 20 |
| Loss function | CrossEntropyLoss | CrossEntropyLoss |

7. Results

| Model | Test Accuracy | Macro F1-Score |
|-------|---------------|----------------|
| MLP Baseline | 88.44% | 0.8832 |
| CNN | **92.98%** | **0.9298** |

Improvement: +4.54%

8. Error Analysis

Top-5 Confusions (MLP)
| True | Predicted | Count |
|------|-----------|-------|
| Shirt | T-shirt/top | 103 |
| Pullover | Coat | 102 |
| Shirt | Coat | 92 |
| Dress | Coat | 37 |
| T-shirt/top | Shirt | 35 |

Top-5 Confusions (CNN)
| True | Predicted | Count |
|------|-----------|-------|
| Dress | Coat | 60 |
| Shirt | T-shirt/top | ~40 |
| Shirt | Coat | ~35 |
| Pullover | Coat | ~30 |
| T-shirt/top | Shirt | ~25 |

Why CNN outperforms MLP
- Spatial feature extraction (edges, textures)
- Parameter sharing reduces overfitting
- BatchNorm and Dropout improve generalization

9. Limitations
- Still confuses visually similar items (Dress vs Coat, Shirt vs T-shirt/top)
- No data augmentation used
- Trained on CPU only

10. Future Improvements
- Add data augmentation (rotation, shift, zoom)
- Use pretrained models (ResNet-18)
- Implement learning rate scheduling
- Try ensemble methods

11. Conclusion
CNN achieved **92.98% accuracy**, outperforming MLP baseline (88.44%) by 4.54%. The improvement comes from CNN's ability to learn spatial features.

12. References
- Xiao, H., Rasul, K., & Vollgraf, R. (2017). Fashion-MNIST: a Novel Image Dataset for Benchmarking Machine Learning Algorithms. arXiv:1708.07747.
- PyTorch documentation: https://pytorch.org/
