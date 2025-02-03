# Title: Neural Network for Binary Classification


## Abstract
his notebook demonstrates the implementation of a simple neural network to classify linearly separable data into two classes. The neural network consists of a single-layer perceptron using the sigmoid activation function and is trained using gradient descent.




## 2. Methodology
### 1. Data Generation
The dataset consists of 100 points split equally between two classes:
Class 0: Centered around (-1, -1)
Class 1: Centered around (1, 1)
The dataset is visualized using a scatter plot.
### 2. Neural Network Implementation
The network consists of:
Input layer: Two features (x₁, x₂)
Output layer: Single neuron with a sigmoid activation function
Weight Initialization:
Weights and biases are randomly initialized.
Activation Function:
The sigmoid function is used for classification.
Loss Function:
Mean Squared Error (MSE) is used to measure the performance of the network.
### 3. Training the Neural Network
The network is trained using Gradient Descent, adjusting the weights and biases iteratively.
Training runs for 10,000 epochs, with loss values printed every 1000 epochs.
### 4. Testing the Neural Network
The model is tested on new data points to check classification probabilities.
The output values are converted into binary class predictions (0 or 1).
### 5. Visualizing the Decision Boundary
A contour plot is generated to visualize the network’s decision boundary overlaid on the dataset.
