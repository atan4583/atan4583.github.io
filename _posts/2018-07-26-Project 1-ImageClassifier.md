---
title: "Project-Develope an Image Classifier with Deep Learning"
date: 2018-07-26 00:00:00 +0000
tags: [Deep Learning]
categories: [Project]
excerpt: Use a pre-trained deep learning model to train an image classifier to recognize different species of flowers, which can be exported for use in applications like a smart phone app.
mathjax: "true"
thumbnail: "/images/Project1-imgClassifier/flowers.jpg"
---

# Develop an AI Application
Build a flower image classifier with a Pytorch pre-trained deep learning model. This project is part of the deliverables for my [AI Programming with python Nanodegree](https://www.udacity.com/course/ai-programming-python-nanodegree--nd089) (AIPND) with Udacity.

## Dataset
The data set contains images of flowers from 102 different species in [this dataset](https://s3.amazonaws.com/content.udacity-data.com/nd089/flower_data.tar.gz) from Udacity AIPND program. Below is example images from the dataset.

![png](/images/Project1-imgClassifier/samples.png)

Visit [here](http://www.robots.ox.ac.uk/~vgg/data/flowers/102/index.html) to read more about this dataset.

The dataset is split into three parts, training, validation, and testing. During training, we applied transformations such as random scaling, cropping, and flipping, to help the network generalize better and lead to better performance. The validation and testing sets were used to measure the model's performance on data not seen by the model during training.

The input data was resized to 224x224 pixels to enable us to use a Pytorch pre-trained model to train the flower image classifier.

## Process
We used one of the pretrained models from `torchvision.models` to get the image features. Built and trained a new feed-forward classifier using those features, as summarized by the following steps:

- Load and preprocess the image dataset
- Load a [pre-trained network](http://pytorch.org/docs/master/torchvision/models.html)
- Define a new, untrained feed-forward network as a classifier, using ReLU activations and dropout
- Train the classifier layers using backpropagation using the pre-trained network to get the features
- Track the loss and accuracy on the validation set to determine the best hyperparameters
- Use the trained classifier to predict image content

We first worked through a Jupyter notebook to implement the steps to build the classifier. After that we converted the notebook code into a pair of command line python applications, with one for use in training a new network and save the model as a checkpoint file (.pt), and the other, utilizing the checkpoint file to predict the class for an input flower image.

## Tool
Jupter Notebook (Python)

## Programming libraries
torch, torchvision, numpy, PIL, python

## Artifact
- Image Classifier Project.ipynb
- train.py
- predict.py
- imageClassifier.pt

See [code here](https://github.com/atan4583/aipnd-project)
