# Cassava-Leaf-Classification
This is a project done on classifying cassava leaf diseases.


## Data Preprocessing

The image size used is 224x224. We used horizontal flip, random resized crop,
center crop and random rotation on the images as a form of data augmentation.


## Models

We tried a lot of pretrained models. We also ensemble a lot of these models and
the outputs were quit good.
Comparing with other models, Resnext101-32x8d gives the best accuracy
(90%). (It was 89% during validation test). The model is pretrained and we just remove the last layer
(the classifier) and add two additional fully connected layers and a Relu function
in between. The first layer takes 2048 inputs and 128 output, the second layer
has 128 input and 5 outputs(5 is the number of classes). Model parameters: We
initialize learning Rate(LR) with 0.0001 and use LR scheduler to find the best
LR for each epoch.

## Results and Findings

 We introduce the results of some of the models used. A number
of pre-trained models have been performed such as: ResNet101 ResNet152,DenseNet 121 , and EfficientNet and VGG19. These Models recorded accuracies
between 83% and 86%. Table 1 describes the Models with high accuracies.
We ensemble ResNet101 and VGG19 and obtained as accuracy of 86% on the
validation set. We implemented these models using only pytorch

## Conclusion

In conclusion, we observed that Adam optimizer performed better other than op-
timizers like Stochastic Gradient Descent(SGD) and on all the models. Se Resnext101-
32x4d also performed well but was quit slow. Using learning rate scheduler
helped us a lot to obtained a good accuracy on the Public Leader Board. In-
creasing the number of epochs usually improve the accuracy of train data, how-
ever we will usually end up with over-fitting. We then limited our number of
epochs to be between 25-30 and also validated on the training set showed by
the table. We again observed that Cross Entropy Loss performed better than
Negative Log Likelihood Loss(NLL Loss) on all our models.
We believe that when our model is deployed, it will help in detecting cassava
leave disease. This will help farmers increase their productivity and earn much
money.
