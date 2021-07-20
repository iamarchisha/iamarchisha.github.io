---
layout: "post"
title: "How to Implement a Multilayer Perceptron"
date: "2021-07-19 10:34"
excerpt: "An explanation of perceptron and a very simple way to implement it from scratch using Python."
comments: true
---
We are going to implement a multilayer perceptron for a very simple XOR (exclusive OR logic) gate. The reason for choosing this particular problem statement is to fully understand the mathematics that goes on behind the scenes. Not only will this help understand the mathematics required to build a multilayer perceptron from scratch but will also help in creating a simple workflow in Python.

## Problem Statement
The truth table for logical XOR gate looks like this:
|X|Y|Output|
|:---:|:---:|:---:|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|
Interpreting this table in the form that can be fed as input ot our multilayer percptron: `X` and `Y` act as the inputs to to model and the `Output` act as the values that the model must predict when given a set of inputs. From looking at the table we can also infer that the outputs for these data points are not linearly separable.

## Perceptron Architecture
Each of the values from `X` and `Y` will be given to the input layer. This implies that there will be 2 neurons in the input layer to accept these values. This layer will be fully connected with the hidden layer. A fully connected layer means that all the weights from one layer are being passed to the next layer. In this case, weights from each of the neurons in the input layer will pass the weights `W11` and `W12` to the 1st and 2nd neuron in the hidden layer. Similarly, weights `W21` and `W22` will be passed from the 2nd neuron in the input layer to the 2 neurons of the hidden layer. To know more about dense layers aka fully-connected layer, you can check out this [blog](https://towardsdatascience.com/the-basic-building-block-of-neural-networks-a9b2e8f5c056).

<div class="fig figcenter fighighlight">
  <img src="/images/multilayer_perceptron/perceptron_1.PNG">
  <div class="figcaption"><br> Change in number of misclassifications as the perceptron fits the data for every epoch with the information from feature set 1.<br>
  </div>
</div>

## Activation Function
https://machinelearningmastery.com/choose-an-activation-function-for-deep-learning/
https://towardsdatascience.com/activation-functions-neural-networks-1cbd9f8d91d6
