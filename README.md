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
* Convolution Layer - accepts a batch of images and convolve them based on the defined filter, bias, padding and stride and activation function. The "RELU" is already implemented as activation function but we could simply add "Sigmoid" and "tanh" as well. The "backward_pass" function of this class calculates the gradients that are necessary to update kernel and bias parameters. pad_img function provides the possibility of padding images.
* Pool Layer - Accepts a batch of images that are already convolved by a previous convolution layer together with the window size for pooling, pooling method(average or max) and stride and do the pooling. The "backward_pass" function of this class back propagates the gradients through the pooling layer in order to be able to compute the gradients of the layers that are located before the current pooling layer. For max pooling, within each sliding window, only the max element is going to be updated by the corresponding gradient that has been received from the next layer. For average pooling, within each sliding window, the corresponding gradient that has been received from the next layer is going to be distributed equally.
* Fully Connected Layer - is adding a fully connected layer of n nodes. To implement this class, I used the class that I implemented for Convolution Layer considering each fully connected node as a filter with the size of the previous layer.
* Softmax Layer - is using the softmax formula to be able to interprete the output as the probability of each class
* Optimization Layer (Not Completed) - 

## How Convolution Layer works
### Forward Pass
* The snapshot below (taken from http://cs231n.github.io/convolutional-networks/) could show the forward pass of convolution layer class
<td>
<img src="images\CNN_conv.png">
<td>

### Backward Pass
 * The snapshots below (i.e., taken from https://medium.com/@2017csm1006/forward-and-backpropagation-in-convolutional-neural-network-4dfa96d7b37e) show how to calculate gradients with respect to weights and inputs in the back propagation process:
<td>
<img src="images\bp1.jpeg">
<td>
<td>
<img src="images\bp2.png">
<td>
<td>
<img src="images\bp3.png">
<td>
<td>
<img src="images\bp4.jpeg">
<td>
<td>
<img src="images\bp5.png">
<td>
<td>
<img src="images\bp6.jpeg">
<td>
<td>
<img src="images\bp7.jpeg">
<td>

## How Pooling Layer works
* The snapshot below (taken from http://cs231n.github.io/convolutional-networks/) shows the forward pass of Pooling (i.e., max pooling) layer class
<td>
<img src="images\max_pool_fp.png">
<td>

* For average pooling, instead of max function, we would use average function on each sliding window
