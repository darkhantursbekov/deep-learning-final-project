Week 2 Report

Date: 2026-05-04

This weeks, the dataset was divided in training, validation,and test datasets in the ratio of 80 10 10. Data preprocessing being completed, the baselines model based on a multilayers perceptron with architecture 784 to 128 to 10 was developed.

Model training was conducted for 20 epocha with the Adam optimizer, having a learning rate of 0.001, and a batch size of 64. The models was tested on the test set; loss curves and a confusion matrix were also drawn. In addition,error analysis was carried out to see what mistakes were made most often.

The test accuracy of the models 88.44 percent. Macro and weighted F1 scores are equal to 0.8832, meaning that the model performs equally well with each class.

According to the confusion matrix, the model most often makes error between visually similars classes. The highest number of mistakes is related to classes Shirt and T shirt top – 103 errors,and Pullover and Coat – 102 mistakes. Class Shirt turned out to be one of most difficult to classify since it was classified as T-shirt top and Coat most often.

In summary,even though the MLP model was relatively simples and lacked the ability to extract spatial features, its showed decent performance. Accuracy on validation remained stable on about 88% to 89%, with some overfitting seen beyond epoch 15.

For the upcoming week, the objective is to build a CNN by using layers such as Conv2D, MaxPooling, and Dropout. The performance of the CNN model would then be benchmarked against that of the MLP models, aiming for an accuracy higher than 92%.
