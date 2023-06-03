## Overview

The goal of this project was to implement a Coteaching approach using two models to address the challenge of noisy labels. By leveraging the disagreement between the models, a smaller subset of potentially cleaner labels could enhance the robustness of the trained model. 

The model architecture implements a CNN model with multiple convolutional layers and batch normalization. It applies leaky ReLU activation, pooling, and dropout operations to extract features from input images and generate predictions.

### Dataset

This model uses a modified version of [CIFAR100-NoisyLabel](https://www.kaggle.com/c/cifar100-image-classification-with-noisy-labels/data)


## Results
![Alt text](/l_curve4_6_w_10.png "Loss Curve")

## Thoughts 

The model begins to overfit the data after ~12 epochs, data augmentation, such as image transforms and flips may help, label smoothing and weight decay may help.

The primary issue of the model is overfitting the noisy labels, in which traditional methods of regularization don't help immensely. Implementing confidence weighting would help the model train, or revising the Coteaching solution. One idea adjacent to this is to build a self resistance learning model that uses adoption of confident samples to learn.

# References
https://github.com/yeachan-kr/pytorch-coteaching/
