# Neural Network from Scratch - MNIST Classification



![image](https://github.com/user-attachments/assets/fd16d9fa-0875-4875-bdf5-2fb821dd4332)




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



![image](https://github.com/user-attachments/assets/751678b4-b046-4e77-8e27-1afbbea69c49)



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



![image](https://github.com/user-attachments/assets/8aebb8fa-4cf5-44bd-ba27-b30dfc5b8fa8)



## Dropout Regularization

To prevent overfitting, dropout regularization was integrated into the network. During training, dropout randomly deactivates a subset of neurons to ensure the network does not become too reliant on any single feature. The dropout probability was experimented with, and a value of 0.5 was found to be most effective.


![image](https://github.com/user-attachments/assets/2e96406d-ec19-42e4-b9c2-8047cfe4d450)



## Results

### Batch Size Experiment

Different batch sizes were tested to determine their impact on accuracy. The batch size of 128 provided the best results, balancing training efficiency and model accuracy.

| Batch Size | Train Accuracy | Validation Accuracy | Test Accuracy | Epoch |
|------------|----------------|---------------------|---------------|-------|
| 16         | 10.47%         | 10.31%              | 10.28%        | 1     |
| 32         | 85.41%         | 84.47%              | 85.64%        | 7     |
| 64         | 87.45%         | 86.91%              | 87.18%        | 13    |
| **128**    | **93.04%**     | **91.86%**          | **92.32%**    | **45**|
| 256        | 91.51%         | 90.61%              | 90.99%        | 90    |
| 512        | 89.05%         | 88.70%              | 88.92%        | 100   |
| 1024       | 69.67%         | 70.36%              | 69.45%        | 100   |
| 2048       | 26.86%         | 27.62%              | 27.33%        | 100   |

![image](https://github.com/user-attachments/assets/d2b2a336-8fbf-4f24-ba34-aec8afa3ae8e)



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
