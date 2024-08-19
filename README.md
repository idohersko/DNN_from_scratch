# Neural Network from Scratch - MNIST Classification

This project showcases the development of a neural network built from scratch to classify handwritten digits using the MNIST dataset. The aim was to deeply understand the inner workings of neural networks by implementing both forward and backward propagation, experimenting with various configurations, and optimizing performance.

## Table of Contents

1. [Overview](#overview)
2. [Setup](#setup)
3. [Training Process](#training-process)
4. [Dropout Regularization](#dropout-regularization)
5. [Results](#results)
6. [Conclusion](#conclusion)

## Overview

In this project, I built a fully connected neural network from the ground up and applied it to the MNIST dataset. The objective was to gain a deeper insight into how neural networks function and how they can be fine-tuned to achieve optimal performance. The project involved experimenting with different network architectures, batch sizes, learning rates, and regularization techniques like dropout.

## Setup

To set up the neural network:

- The MNIST dataset is loaded using Keras, with the data split into training and test sets by default.
- The training set is further split, with 80% used for training and 20% for validation.
- The dataset is normalized by dividing pixel values by 255.
- Input data is flattened, and labels are one-hot encoded.
- The neural network consists of 4 layers (excluding the input layer) with sizes: 20, 7, 5, 10.
- The network is trained with a learning rate of 0.009, for 100 epochs, and a batch size of 128.

## Training Process

The training process involves:

1. Initializing network parameters.
2. Splitting data into training and validation sets.
3. Calculating the number of batches based on the batch size.
4. Iterating over the epochs:
   - Forward propagation through the network.
   - Backward propagation to compute gradients.
   - Updating network parameters.
   - Recording training and validation costs at regular intervals.
   - Implementing early stopping based on validation cost.

## Dropout Regularization

To prevent overfitting, dropout regularization was integrated into the network. During training, dropout randomly deactivates a subset of neurons to ensure the network does not become too reliant on any single feature. The dropout probability was experimented with, and a value of 0.5 was found to be most effective.

## Results

### Batch Size Experiment

Different batch sizes were tested to determine their impact on accuracy. The batch size of 128 provided the best results, balancing training efficiency and model accuracy.

### Dropout Experiment

Dropout probabilities ranging from 0.1 to 0.9 were tested. A dropout probability of 0.5 was identified as optimal, improving the model's generalization on unseen data.

### Final Experiment

Four configurations were tested, combining batch normalization and dropout:

| Experiment | Batch Size | Epochs | Batchnorm | Dropout | Train Accuracy | Validation Accuracy | Test Accuracy |
|------------|------------|--------|-----------|---------|----------------|---------------------|---------------|
| 1          | 128        | 43     | No        | No      | 89.39%         | 88.81%              | 88.77%        |
| 2          | 128        | 46     | No        | Yes, 0.5| 89.43%         | 89.20%              | 89.27%        |
| 3          | 128        | 31     | Yes       | No      | 83.31%         | 83.66%              | 83.74%        |
| 4          | 128        | 19     | Yes       | Yes, 0.5| 67.89%         | 67.67%              | 67.10%        |

## Conclusion

Experiment 2, featuring a batch size of 128, 46 epochs, and a dropout probability of 0.5, delivered the best performance with a test accuracy of 89.27%. The use of batch normalization, although slightly increasing the computation time, did not yield better results in this context. This project provided valuable insights into the practical implementation and optimization of neural networks for image classification tasks.

## Author

- Elran Oren – 205965908
- Ido Hersko - 204809867
