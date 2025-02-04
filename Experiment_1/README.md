# TITLE: MNIST Dataset Processing with NumPy

## Overview
This Jupyter Notebook provides a streamlined approach to loading, processing, and visualizing the MNIST dataset using NumPy and Matplotlib. The dataset consists of handwritten digit images (0-9) and corresponding labels. This implementation enables efficient loading and normalization of the dataset for further machine learning tasks.

## Abstract
The objective of this lab is to provide a streamlined approach to loading, processing, and visualizing the MNIST dataset using NumPy. 

## 1. Introduction
The dataset consists of handwritten digit images (0-9) and corresponding labels. This implementation enables efficient loading and normalization of the dataset for further machine learning tasks.

#### Features
- *Dataset Handling*: Reads MNIST images and labels from raw binary files.
- *Data Normalization*: Scales pixel values to the range [0,1] for better model performance.
- *Visualization*: Displays multiple sample images with their corresponding labels.

## Code Highlights
### Loading MNIST Data
```python
import numpy as np

def load_mnist_images(file_path):
    """Load MNIST image file in ubyte format."""
    with open(file_path, 'rb') as f:
        magic_number = int.from_bytes(f.read(4), 'big')
        if magic_number != 2051:
            raise ValueError(f"Invalid magic number {magic_number}, expected 2051")
        num_images = int.from_bytes(f.read(4), 'big')
        num_rows = int.from_bytes(f.read(4), 'big')
        num_cols = int.from_bytes(f.read(4), 'big')
        images = np.frombuffer(f.read(), dtype=np.uint8).reshape(num_images, num_rows * num_cols)
    return images / 255.0  # Normalize to [0, 1]
```

### Visualizing the Dataset
```python
import matplotlib.pyplot as plt
fig, axes = plt.subplots(4, 4, figsize=(10, 10))

for i, ax in enumerate(axes.flat):
    img = x_train[i].reshape(28, 28)
    ax.imshow(img, cmap='gray')
    ax.set_title(f"Label: {y_train[i]}")
    ax.axis('off')  # Hide axes

plt.show()
```

