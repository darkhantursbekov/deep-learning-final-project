Week 3 Report

Completed Tasks
- Used CNN model with 2 convolutions, BatchNorm, and Dropout
- Trained model for 20 epochs
- Conducted tests on the testing dataset
- Compared model performance with MLP
- Produced loss graphs and confusion matrices

Model Structure

| Layer Type | Parameters |
|------------|-------------|
| Conv1      | 1 → 32, 3x3, padding=1         |
| BatchNorm1 | 32          |
| ReLU       | Activation             |
| Max Pool   | 2x2               |
| Conv2      | 32 → 64, 3x3, padding=1         |
| BatchNorm2 | 64              |
| ReLU       | Activation             |
| Max Pool   | 2x2               |
| FC1        | 64x7x7 → 256           |
| Dropout    | 0.5                 |
| FC2        | 256 → 10        |
Total number of parameters:** 824,650

Training Parameters
- Optimizer: Adam (lr=0.001)
- Loss Function: CrossEntropyLoss
- Batch Size: 64
- Epochs: 20
- Train/Validation/Test split: 48,006 / 6,000 / 5,994

Results

| Metric             | MLP Baseline | CNN         | Gain        |
|--------------------|--------------|-------------|-------------|
| Test Accuracy (%)  | 88.44        | 92.98       | +4.54       |
| Macro F1-Score     | 0.8832       | 0.9298      | +0.0466     |

Top-5 Confusion Pairs (CNN)

| True Category       | Predicted Category | Count |
|--------------------|--------------------|-------|
| Dress              | Coat               | 60    |
| Shirt              | T-shirt/top        | ~40   |
| Shirt              | Coat               | ~35   |
| Pullover           | Coat               | ~30   |
| T-shirt/top        | Shirt              | ~25   |

Observations
- CNN far outperforms MLP because of its ability to extract spatial features
- Both architectures demonstrate similar types of errors (Shirt → T-shirt/top, Dress → Coat)
- Error count is reduced with CNN
- BatchNorm and Dropout techniques prevent overfitting

Visualizations
- Training/validation loss curves: `results/cnn_loss_curves.png`
- Confusion matrix: `results/cnn_confusion_matrix.png`

Plan for Week 4
- Prepare final report with complete comparison
- Create presentation slides
- Upload all materials to GitHub
