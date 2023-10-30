+++
author = "Hashim Y"
title = "An Introduction to Stochastic Gradient Descent and Some Simple Applications "
date = "2023-09-17"
description = "Goes through the basics of SGD and shows applications of the algorithm which are applicable to physics."
tags = ["Machine learning"]
+++

Recently, I've been playing with PyTorch while following through the amazing Daniel Bourke's course in the matter. [A link for those interested: (Click here)](https://www.learnpytorch.io) 

In the 2nd chapter of the course, the main objective is to write a program which can accurately predict the gradient and intercept of a linear regression line. The most prominent algorithms used were the least squares algorithm, used to calculate the loss function, and the stochastic gradient descent (SGD) algorithm used to optimise the loss. 

Stochastic gradient descent is an algorithm used to optimise a function's parameters by iterating through the function and then adjusting the parameters inserted to the function based off the gradients calculated by the loss function. In the case of the machine learning algorithm provided, the gradients for each "step" of parameter are calculated and stored within the loss function. 

The formula used to adjust the function's parameter is as follows: (insert latex statement here)

An important idea to keep in mind when talking about it's application in this case is that machine learning entirely works around tensor operations. This means that our loss function is, in affect, nothing more than a very long list of numbers. So, when we talk about the step, we just mean the difference between them. For example, (talk about a simple linear regression, with some example numbers ok)

We need more images.


