# Sign Language MNIST Classification with PyTorch

## Project Overview
This project implements a Convolutional Neural Network (CNN) using PyTorch to classify images of American Sign Language (ASL) letters. The goal is to accurately identify ASL letters (excluding 'J' and 'Z', which require motion) from static images provided in the Sign Language MNIST dataset.

## Dataset
The dataset used is the Sign Language MNIST, which consists of 28x28 grayscale images of ASL letters. Each image represents a single letter (A-Y, excluding J and Z).

- **`sign_mnist_train.csv`**: Training data.
- **`sign_mnist_test.csv`**: Testing data.

## Technologies Used
- **PyTorch**: Deep learning framework for building and training the CNN model.
- **Pandas**: For data loading and manipulation (CSV files).
- **NumPy**: For numerical operations, especially with image data.
- **Matplotlib & Seaborn**: For data visualization (loss/accuracy plots, sample predictions, confusion matrix).
- **Torchvision**: For image transformations (`ToTensor`, `Normalize`).
- **Torchmetrics**: For advanced metric calculation, specifically the Confusion Matrix.
- **MLxtend**: For plotting the Confusion Matrix.

## Model Architecture
The model is a custom Convolutional Neural Network (`SignLanguageModel`) defined with:
- Two convolutional blocks, each consisting of `Conv2d` layers followed by `ReLU` activation and `MaxPool2d`.
- A `Flatten` layer to convert the 2D feature maps into a 1D vector.
- A final `Linear` layer for classification into 25 output classes (representing A-Y, with 'J' and 'Z' skipped, but preserving indices 0-24).

## Results
Achieved a train accuracy of 100% and a test accuracy of 95.71%.
- **Loss and Accuracy Plots**: Visualizations of training and testing loss and accuracy across epochs to observe model convergence and performance.
- **Sample Predictions**: A grid of example images from the test set, showing the model's prediction versus the true label, highlighted in green (correct) or red (incorrect).
- **Confusion Matrix**: A detailed confusion matrix showing the performance of the classifier for each ASL letter. The 'J (Skipped)' row/column indicates that this class was not part of the training data.

_Note: Due to the nature of the dataset, class 'J' (index 9) and 'Z' are not present, as they typically involve motion and are not part of static ASL image datasets._

## Future Work
- Experiment with different CNN architectures or pre-trained models.
- Implement data augmentation techniques to improve generalization.
- Explore techniques for handling class imbalance if any.
- Deploy the model as a web application for real-time sign language recognition.
