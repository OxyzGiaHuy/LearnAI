# 1. Introduction
For some problems, even elite programmers would struggle to _code from scratch_. The reasons can vary. Sometimes the program that we are looking for follows a pattern that changes over time, so there is no fixed right answer

At other times, the relationship (say between pixels, and abstract categories) may be too complicated, requiring thousands or millions of computations and following unknown principles.

Machine learning is the study of algorithms that can learn from experience. As a machine learning algorithm accumulates more experience, typically in the form of observational data or interactions with an environment, its performance improves.

## 1.1. A Motivating Example
In the currently dominant approach to machine learning, we do not attempt to design a system explicitly to recognize wake words. Instead, we define a flexible program whose behavior is determined by a number of parameters. Then we use the dataset to determine the best possible parameter values, i.e., those that improve the performance of our program with respect to a chosen performance measure.

Once the parameters are fixed, we call the program a model. And the _meta-program_ that uses our dataset to choose the parameters is called a learning algorithm.

![Fig 1](https://d2l.ai/_images/ml-loop.svg)

## 1.2 Key Components

* The data that we can learn from.
* A model of how to transform the data.
* An objective function that quantifies how well (or badly) the model is doing.
* An algorithm to adjust the model’s parameters to optimize the objective function.

### 1.2.1. Data
In order to work with data usefully, we typically need to come up with a suitable numerical representation. Each example (or data point, data instance, sample) typically consists of a set of attributes called features (sometimes called covariates or inputs), based on which the model must make its predictions. In supervised learning problems, our goal is to predict the value of a special attribute, called the label (or target), that is not part of the model’s input.

In such cases, when every sample is characterized by the same number of numerical features, we say that the inputs are fixed-length vectors and we call the (constant) length of the vectors the dimensionality of the data.

However, not all data can easily be represented as fixed-length vectors. While we might expect microscope images to come from standard equipment, we cannot expect images mined from the Internet all to have the same resolution or shape.

One major advantage of deep learning over traditional methods is the comparative grace with which modern models can handle varying-length data.

Generally, the more data we have, the easier our job becomes. When we have more data, we can train more powerful models and rely less heavily on preconceived assumptions. The regime change from (comparatively) small to big data is a major contributor to the success of modern deep learning. Many of the most exciting models in deep learning do not work without large datasets.

We need the _right_ data. If the data is full of mistakes, or if the chosen features are not predictive of the target quantity of interest, learning is going to fail. In sensitive applications of machine learning, like predictive policing, resume screening, and risk models used for lending, we must be especially alert to the consequences of garbage data.

Failure can also occur when the data does not only under-represent some groups but reflects societal prejudices. For example, if past hiring decisions are used to train a predictive model that will be used to screen resumes then machine learning models could inadvertently capture and automate historical injustices. Note that this can all happen without the data scientist actively conspiring, or even being aware.

### 1.2.2. Model
While simple models are perfectly capable of addressing appropriately simple problems, the problems that we focus on in this book stretch the limits of classical methods. Deep learning is differentiated from classical approaches principally by the set of powerful models that it focuses on. These models consist of many successive transformations of the data that are chained together top to bottom, thus the name _deep learning_.

### 1.2.3. Objective Functions
In order to develop a formal mathematical system of learning machines, we need to have formal measures of how good (or bad) our models are. In machine learning, and optimization more generally, we call these _objective functions_.  Because we choose lower to be better, these functions are sometimes called _loss functions_.

_Square error_ is used to predict numerical values. For classification, the most common objective is to _minimize error rate_.

Some objectives (e.g., squared error) are easy to optimize, while others (e.g., error rate) are difficult to optimize directly, owing to non-differentiability or other complications. In these cases, it is common instead to optimize a _surrogate objective_.

Doing well on the training data does not guarantee that we will do well on unseen data. So we will typically want to split the available data into two partitions: the training dataset (or training set) for learning model parameters; and the test dataset (or test set), which is held out for evaluation.

### 1.2.4. Optimization Algorithms
Once we have got some data source and representation, a model, and a well-defined objective function, we need an algorithm capable of searching for the best possible parameters for minimizing the loss function. Popular optimization algorithms for deep learning are based on an approach called _gradient descent_. 

## 1.3. Kinds of Machine Learning Problems
### 1.3.1. Supervised Learning

Supervised learning is a machine learning paradigm where a model is trained on a dataset with labeled examples to predict labels for new input features. The goal is to estimate the _conditional probability_ of a label given input features. It has many successful applications across various industries and involves a learning process where a model is trained on a labeled training set and used to predict labels for unseen inputs.

![Supervised Learning](https://d2l.ai/_images/supervised-learning.svg)

#### 1.3.1.1. Regression

When labels take on arbitrary numerical values (even within some interval), we call this a regression problem. The goal is to produce a model whose predictions closely approximate the actual label values. A good rule of thumb is that any how much? or how many? problem is likely to be regression. For example:
* How many hours will this surgery take?
* How much rainfall will this town have in the next six hours?

#### 1.3.1.2. Classification
