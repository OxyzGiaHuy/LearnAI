# 1. Introduction
For these problems, even elite programmers would struggle to code up solutions from scratch. The reasons can vary. Sometimes the program that we are looking for follows a pattern that changes over time, so there is no fixed right answer

At other times, the relationship (say between pixels, and abstract categories) may be too 
complicated, requiring thousands or millions of computations and following unknown principles.

Machine learning is the study of algorithms that can learn from experience. As a machine learning 
algorithm accumulates more experience, typically in the form of observational data or interactions 
with an environment, its performance improves.

## 1.1. A Motivating Example
In the currently dominant approach to machine learning, we do not attempt to design a system explicitly 
to recognize wake words. Instead, we define a flexible program whose behavior is determined by a number 
of parameters. Then we use the dataset to determine the best possible parameter values, i.e., those that 
improve the performance of our program with respect to a chosen performance measure.

Once the parameters are fixed, we call the program a model. And the “meta-program” that uses our dataset 
to choose the parameters is called a learning algorithm.

# 1.2 Key Components

The data that we can learn from.
A model of how to transform the data.
An objective function that quantifies how well (or badly) the model is doing.
An algorithm to adjust the model’s parameters to optimize the objective function.

## 1.2.1. Data
In order to work with data usefully, we typically need to come up with a suitable numerical representation. 
Each example (or data point, data instance, sample) typically consists of a set of attributes called features 
(sometimes called covariates or inputs), based on which the model must make its predictions. In supervised 
learning problems, our goal is to predict the value of a special attribute, called the label (or target), 
that is not part of the model’s input.

In such cases, when every sample is characterized by the same number of numerical features, we say that the 
inputs are fixed-length vectors and we call the (constant) length of the vectors the dimensionality of the data.

However, not all data can easily be represented as fixed-length vectors. While we might expect microscope images to come from standard equipment, we cannot expect images mined from the Internet all to have the same resolution or shape.

One major advantage of deep learning over traditional methods is the comparative grace with which modern models can handle varying-length data