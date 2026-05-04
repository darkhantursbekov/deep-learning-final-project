Project Proposal: Fashion-MNIST Image Classification
1. Project Title
MLP vs CNN for Fashion-MNIST Classification
2. Problem Statement
Classify grayscale images of clothing items into 10 categories.  
This is useful for automated inventory management and recommendation systems.  
The model will predict one class per image.
3. Dataset
Name: Fashion-MNIST
Source: https://www.kaggle.com/zalando-research/fashionmnist
Size: 60,000 training images, 10,000 test images
Format: 28×28 grayscale pixels, CSV format
Classes: 10 (T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle boot)

4. Planned Method
Baseline: 3-layer MLP with ReLU activation (input 784, hidden 128, output 10)
Deep learning model: CNN with Conv2D, MaxPooling, Dropout, and BatchNorm
Loss function: CrossEntropyLoss
Evaluation metrics: Accuracy, F1-score, Confusion Matrix
Data split: Train 80%, Validation 10%, Test 10% (from original training set)

5. Expected Challenges
Overfitting without regularization (dropout/batchnorm)
Class confusion (e.g., Shirt vs T-shirt/top look similar)
Training time on CPU
