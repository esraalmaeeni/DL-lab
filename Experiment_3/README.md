# Title: CNN IMPLEMENTATION

## Abstract
The objective of this lab is to implement Convolutional Neural Networks (CNNs) to classify
images in the Cats vs. Dogs dataset and the CIFAR-10 dataset.

## 1. Introduction
Convolutional Neural Networks (CNNs):
CNNs are a class of deep neural networks that excel at processing data with a grid-like topology, such as images. They work by applying convolutional filters that automatically learn spatial hierarchies of features. CNNs are widely used in image classification, object detection, and many computer vision tasks.

Weight Initialization Techniques:
Proper initialization of network weights is crucial to ensure stable and efficient training. Common techniques include:

Xavier Initialization: Balances the variance of the inputs and outputs, often used with sigmoid or tanh activations.
Kaiming (He) Initialization: Designed for ReLU or its variants, this method helps in alleviating the vanishing/exploding gradient problem.
Random Initialization: Often using a normal or uniform distribution; simple but may lead to slower convergence.
Activation Functions:
Activation functions introduce non-linearity into neural networks. Their role is to allow the network to learn complex patterns. Common functions include:

ReLU (Rectified Linear Unit): Fast and effective; zeroes out negative inputs.
Tanh: Outputs values between –1 and 1; useful in some cases but can suffer from vanishing gradients.
Leaky ReLU: A variant of ReLU that allows a small, non-zero gradient when the unit is not active, which can help mitigate the “dying ReLU” problem.
Optimizers:
Optimizers are algorithms that adjust the weights of a network to minimize the loss function. Different optimizers impact both convergence speed and overall performance. In our experiments we used:

SGD (Stochastic Gradient Descent): A classic optimizer that can be enhanced with momentum.
Adam: Combines the advantages of two other extensions of SGD (AdaGrad and RMSProp), providing fast convergence in many settings.
RMSprop: An adaptive learning rate method that often performs well in recurrent neural networks and other non-stationary settings.
ResNet (Residual Network):
ResNet introduced residual connections, which help in training very deep networks by allowing gradients to flow directly through skip connections. ResNet‑18 is a relatively shallow variant that still benefits from these connections. Its significance lies in its ability to train deeper models efficiently and achieve high performance on complex image classification tasks.


## 2. Methodology
### 2.1 Data Description
- Datasets Used: Cats vs. Dogs dataset and the CIFAR-10 dataset.
- Preprocessing and Augmentation
  
### 2.2 Model Architectures
- Custom CNN Details
- ResNet-18 and Transfer Learning
### 2.3 Training Process
- Hyperparameters
- Loss Functions and Optimizers

## 3. Experimental Setup
- Evaluation Metrics
- Experimental Design
- Reproducibility Details

## 4. Results
Custom CNN Results on CIFAR‑10
![image](https://github.com/user-attachments/assets/aeb1c91f-76f6-4a8e-bb5a-08d4fd190d16)

Custom CNN Results on Cats vs. Dogs
![image](https://github.com/user-attachments/assets/814115b3-75ae-4a99-b43f-25ec2f812d40)

Fine‑Tuned ResNet‑18 Results
![image](https://github.com/user-attachments/assets/ac40a649-1409-4c2d-b437-c205cdf32467)



## 6. Conclusion
**Custom CNN:**

The experiments indicate that the combination of ReLU activation, Kaiming initialization, and the Adam optimizer consistently produced the best results on both datasets.
ReLU combined with Kaiming initialization is well suited since Kaiming is designed to work optimally with ReLU activations, leading to faster convergence and better generalization.

**ResNet‑18 vs. Custom CNN:**

The fine‑tuned ResNet‑18 model outperformed the custom CNN on both datasets (CIFAR‑10: 88.0% vs. 85.2% and Cats vs. Dogs: 89.5% vs. 87.0%).
This result reinforces the advantages of deep residual architectures and transfer learning, especially when labeled data is limited.
Training Dynamics:

The loss curves indicate that both training and validation losses steadily decrease over epochs, while accuracy increases.
ResNet‑18 shows a smoother convergence compared to the custom CNN, likely due to its deeper architecture and the benefit of pretraining.

