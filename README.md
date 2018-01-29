# Exercise_0
## Goal
* Develop your own simple Feed-Forward Neural Network in Python (CNN).
## Rquirements 
* Implement the basic layers for multi-layer percepterons and CNN
* Try to include the most common operations between layers such as convolution and max-pooling
* The code should be easy to read 
* The implementation should be as modular as possible
## Allowed to
* Use core libraries such as Numpy and Scikit-learn
## Nice to have
* Optimization on critical operations to improve performance using Cython
## Usage
* Use MNIST dataset to provide some usage examples with images

## Solution

The following classes have been implemented:
* Data Visualization - which shows random images from the MNIST data set in an m*n grid
* Load Data - reads images from the provided input path and constructs Training and Test sets with the option to specify the percentage for train and test subsets (70%, 30% by default)
* Convolution Layer - accepts a batch of images and convolve them based on the defined filter, bias, padding and stride and activation function. The "RELU" is already implemented as activation function but we could simply add "Sigmoid" and "tanh" as well. The 

