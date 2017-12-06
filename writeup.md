# Traffic sign classifier
## Introduction
This project aims to get a hands on experience using TensorFlow to build convolutional and fully connected neural networks.

The data used is the The German Traffic Sign Recognition Benchmark, GTSRB. the data set was divided into training, validation sets.

## Data overview
Data consists of 43 classes of different traffic signs. Following is a sample of the data.

![alt text](/resources/sample.PNG "Sample of the data being processed")

## Data preprocessin
The main preprocessing step is to shuffle the training data. More preprocessing steps were tested, but all of them led to lower accuracy results. Images were converted to gray scale, but it was no use, as convnets will do something similar if needed in its filters. Also images were normalized, but it seemed not useful, as well. 

## LeNet
The architecture from lenet was used in this submission. The same one used in the previous excercises. Many modifications were tested, like adding more convnets layers, or use the results from the layer 1 with the layer 2 for the fully connected layer like the following image.

![alt text](/resources/2-stages-into-fc.PNG "Two Stages into FC")

## Struggles
All the previous methods were no use, until Aman, my mentor suggested to look into the training accuracy and compare it with the validation accuracy and see if the problem is over fitting or underfitting. This made me realize that the model is deep enough and we need some generalization.

## Overfitting
I have tested two methods for generalization, dropouts, and reguralization term. The first one did not enhance the validation accuracy as requested, but lowered the training accuracy. 

I have moved to regularization, added all weights with a scalar, and combined them to the loss. After some trial, the best value for the scalar was found, and the validation accuracy was around 93% - 95%.

## Testing on New Images
The model was tested on new five images obtained from the original GTSRB data from their website. the accuracy was 100%, even with some odd samples.

![alt text](/resources/newImages.PNG "New Images")
