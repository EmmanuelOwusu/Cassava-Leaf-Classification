# Cassava-Leaf-Classification
This is a project done on classifying cassava leaf diseases.


## Data Preprocessing

The image size used is 224x224. We used horizontal flip, random resized crop,
center crop and random rotation on the images as a form of data augmentation.


## Models

We tried a lot of pretrained models. We also ensemble a lot of these models and
the outputs were quit good.
Comparing with other models, Resnext101-32x8d gives the best accuracy
(90%) in the public leader board. (it was 89% during validation test), see
Section 4: Table 1. The model is pretrained and we just remove the last layer
(the classifier)and add two additional fully connected layers and a Relu function
in between. The first layer takes 2048 inputs and 128 output, the second layer
has 128 input and 5 outputs(5 is the number of classes). Model parameters: We
initialize learning Rate(LR) with 0.0001 and use LR scheduler to find the best
LR for each epoch.
