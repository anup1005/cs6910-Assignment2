# cs6910-Assignment2
## About the Dataset
iNaturalist 12k is a subset of the larger iNaturalist dataset that contains around 12,000 observations of over 4,300 plant and animal species.

## Libraries used
Pytorch and torchvision


## Part A
Building  a small CNN model consisting of 5convolution layers. Each convolution layer would be followed by an activation and a max-pooling layer. 
After 5 such conv-activation-maxpool blocks, you should have one dense layer followed by the output layer containing 10 neurons for each of the 10 classes). The input layer should be compatible with the images in the iNaturalist dataset dataset.
The code should be flexible such that the number of filters, size of filters, and activation function of the convolution layers and dense layers can be changed. You should also be able to change the number of neurons in the dense layer.

## Part B
In most DL applications, instead of training a model from scratch, you would use a model pre-trained on a similar/related task/dataset.I have used Resnet50model.
