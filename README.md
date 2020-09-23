# Cassava-Leaf-Classification
This  repository contains a project done on classifying cassava leaf diseases.


## Data

The dataset can be found at https://www.kaggle.com/c/cassava-disease/data.

## Data Preprocessing

The image size used is 224 x 224. 

I applied horizontal flip, random resized crop,
center crop and random rotation on the images(Dataset) as a form of Data Augmentation.


## Models

I tried a lot of pretrained models. I also ensemble a lot of these models and
the outputs were  good.

Comparing with other models, Resnext101-32x8d gives the best accuracy
(91%) on training set. (The accuracy  was 90% during validation test). 

The model is pretrained and I just remove the last layer
(the classifier) and add two additional fully connected layers and a Relu function
in between. The first layer takes 2048 inputs and 128 output, the second layer
has 128 input and 5 outputs (where 5 is the number of classes). 

  * ### Model parameters: 

I initialize the  Learning Rate (LR) with  0.0001 and used LR scheduler to find the best
learning rate  for each epoch.

## Results and Findings

A number of pre-trained models have been performed such as: ResNet101,  ResNet152, DenseNet 121 , and EfficientNet and VGG19. 

These Models recorded accuracies between 83% and 86%. 

I ensemble ResNet101 and VGG19 and obtained an accuracy of 86% on the
validation set.

I implemented these models using  pytorch.

## Conclusion

In conclusion, I observed that Adam optimizer performed better other than optimizers like Stochastic Gradient Descent(SGD) and on all the models. 

Se_Resnext-10132x4d  performed well but was quit slow. 

Using learning rate scheduler helped me a lot to obtained a good accuracy.

Increasing the number of epochs usually improve the accuracy of train data, however it usually results in over-fitting. 

I then limited my number of epochs to be between 25-30 and also validated on the training set.

I again observed that Cross Entropy Loss performed better than Negative Log Likelihood Loss (NLL Loss) on all our models.


I believe that when this model is deployed, it will help in detecting cassava leave disease. 

This will help farmers to increase their productivity and earn much money

This willagain reduce food scarcity in various commuinities.


## Reference 

FAO. Cassava diseases in africa: a major threat to food security, September 2009. 

URL http://www.fao.org/emergencies/resources/documents/resources-detail/en/c/171103/
