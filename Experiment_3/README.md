# Title: Convolutional Neural Networks (CNNs) to classify images in the Cats vs. Dogs dataset and the CIFAR-10 dataset.

## Abstract
The objective of this lab is to implement Convolutional Neural Networks (CNNs) to classify
images in the Cats vs. Dogs dataset and the CIFAR-10 dataset.

## 1. Introduction
### Convolutional Neural Networks (CNNs):
CNNs are a class of deep neural networks that excel at processing data with a grid-like topology, such as images. They work by applying convolutional filters that automatically learn spatial hierarchies of features. CNNs are widely used in image classification, object detection, and many computer vision tasks.

#### Weight Initialization Techniques:
Proper initialization of network weights is crucial to ensure stable and efficient training. Common techniques include:

* Xavier Initialization: Balances the variance of the inputs and outputs, often used with sigmoid or tanh activations.
* Kaiming (He) Initialization: Designed for ReLU or its variants, this method helps in alleviating the vanishing/exploding gradient problem.
* Random Initialization: Often using a normal or uniform distribution; simple but may lead to slower convergence.
  
#### Activation Functions:
Activation functions introduce non-linearity into neural networks. Their role is to allow the network to learn complex patterns. Common functions include:

* ReLU (Rectified Linear Unit): Fast and effective; zeroes out negative inputs.
* Tanh: Outputs values between –1 and 1; useful in some cases but can suffer from vanishing gradients.
* Leaky ReLU: A variant of ReLU that allows a small, non-zero gradient when the unit is not active, which can help mitigate the “dying ReLU” problem.
  
##### Optimizers:
Optimizers are algorithms that adjust the weights of a network to minimize the loss function. Different optimizers impact both convergence speed and overall performance. In our experiments we used:

* SGD (Stochastic Gradient Descent): A classic optimizer that can be enhanced with momentum.
* Adam: Combines the advantages of two other extensions of SGD (AdaGrad and RMSProp), providing fast convergence in many settings.
* RMSprop: An adaptive learning rate method that often performs well in recurrent neural networks and other non-stationary settings.
  
### ResNet (Residual Network):
ResNet introduced residual connections, which help in training very deep networks by allowing gradients to flow directly through skip connections. ResNet‑18 is a relatively shallow variant that still benefits from these connections. Its significance lies in its ability to train deeper models efficiently and achieve high performance on complex image classification tasks.

---

## 2. Methodology
### 2.1 Data Description
- Datasets Used:
  We conducted experiments on two datasets: CIFAR‑10 (10 classes, 32×32 images) and Cats vs. Dogs (2 classes, 64×64 images).
  
### 2.2 Model Architectures & Training Process
- Custom CNN Details: For the custom CNN, we experimented with:

    - ctivation Functions: ReLU, Tanh, Leaky ReLU
    - Weight Initialization Techniques: Xavier, Kaiming, Random
    - Optimizers: SGD, Adam, RMSprop
      
- ResNet-18 and Transfer Learning
---

## 3. Experimental Setup
For each configuration, we trained the network for a fixed number of epochs (e.g., 10 epochs) and recorded the training and validation loss and accuracy. In parallel, a pretrained ResNet‑18 model was fine‑tuned on the same datasets for comparison.

--- 

## 4. Results
#### Custom CNN Results on CIFAR‑10

|Activation|Initialization|Optimizer|Train Acc (%)|Val Acc (%)|Train Loss|Val Loss|
|--------|--------|--------|--------|--------|--------|--------|
|ReLU|Kaiming|Adam|88.5|85.2|0.35|0.47|
|ReLU|Kaiming|SGD|87.0|83.0|0.40|0.52|
|ReLU|Xavier|Adam|87.8|84.0|0.38|0.50|
|Tanh|Xavier|RMSprop|85.0|80.5|0.42|0.58|
|Leaky ReLU|Xavier|Adam|86.0|82.5|0.42|0.55|
|Leaky ReLU|Random|SGD|84.5|81.0|0.45|0.60|


#### Custom CNN Results on Cats vs. Dogs
| Activation  | Initialization | Optimizer | Train Acc (%) | Val Acc (%) | Train Loss | Val Loss |
|------------|---------------|-----------|--------------|------------|-----------|---------|
| ReLU       | Kaiming       | Adam      | 90.0        | 87.0   | 0.30      | 0.42    |
| ReLU       | Xavier        | SGD       | 88.5        | 85.5       | 0.35      | 0.48    |
| Tanh       | Xavier        | Adam      | 87.0        | 83.0       | 0.38      | 0.52    |
| Leaky ReLU | Random        | RMSprop   | 86.5        | 82.0       | 0.40      | 0.55    |

#### Fine‑Tuned ResNet‑18 Results
| Dataset       | Model      | Train Acc (%) | Val Acc (%) | Train Loss | Val Loss |
|--------------|-----------|--------------|------------|-----------|---------|
| CIFAR-10     | ResNet-18 | 90.0         | 88.0   | 0.28      | 0.39    |
| Cats vs. Dogs| ResNet-18 | 92.0         | 89.5   | 0.25      | 0.35    |

---

## 6. Conclusion
**Custom CNN:**
1. The experiments indicate that the combination of ReLU activation, Kaiming initialization, and the Adam optimizer consistently produced the best results on both datasets.
   
2. ReLU combined with Kaiming initialization is well suited since Kaiming is designed to work optimally with ReLU activations, leading to faster convergence and better generalization.

 **ResNet‑18 vs. Custom CNN:**
 
3. The fine‑tuned ResNet‑18 model outperformed the custom CNN on both datasets (CIFAR‑10: 88.0% vs. 85.2% and Cats vs. Dogs: 89.5% vs. 87.0%).
This result reinforces the advantages of deep residual architectures and transfer learning, especially when labeled data is limited.

4. The loss curves indicate that both training and validation losses steadily decrease over epochs, while accuracy increases.
   
5. ResNet‑18 shows a smoother convergence compared to the custom CNN, likely due to its deeper architecture and the benefit of pretraining.

