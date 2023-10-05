# Week 5 - From-scratch model 

## Before the lab session

Watch Video Lesson 5: 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/_rXzeWq4C6w/0.jpg)](https://www.youtube.com/watch?v=_rXzeWq4C6w)

## Lab session

### Task 1

In session 3 you discussed the process of fitting parameters in an automated way (Task 1e), and how adding together multiple rectified linear units can be used to approximate any function (at least piecewise continuous functions - Task 2e). Spend a couple of minutes to reflect and discuss. What key takeaways do you remember?

### Task 2

We have created [some slides](https://docs.google.com/presentation/d/12j8Jz3PnH9indnhu6bfNqDt1SvbWJPlYOCuxHKS25S8/edit#slide=id.g260ce99ca3c_0_0) that will hopefully make it easier to follow along [the notebook of the week](https://www.kaggle.com/code/jhoward/linear-model-and-neural-net-from-scratch). Use the slides as support while you run through the notebook of the week, and try to understand what's going on.

* Jeremy explains that if you choose a too high learning rate, the training will not improve the model. Can you explain why?
* Can you explain what will happen if you use a too small learning rate?
* Can you explain why we use the sigmoid function?
* Can you explain how the gradient descent step works? Can you point out the code that corresponds to the gradient descent step?
* Can you explain why we sometimes need to use the torch.no_grad()-function?


### Task 3

In [this task](https://www.kaggle.com/aylinmariadursun/w5-from-scratch-model), we will revisit the notebook from the first session, where you trained your own model. The aim of the session is to learn more about the F1-score, and understand how introducing a threshold can help you adjust your models precision/ recall.

### Task 4

In this weeks video/ notebook, Jeremy cleans and changes the Titanic dataset so that it is suitable for use in a neural network. In session 7 you will apply these techniques to another dataset. Create a short guide for yourself (maybe in a new kaggle notebook?) where the different techniques that are presented in the two sections of the notebook called "Cleaning the data" and "Setting up a linear model" are summarized. Describe the technique briefly, explain when and why we might want to apply the technique and add some example code showing how the technique is applied:
* replace missing values with mode
* taking the log of a variable
* using dummy variables
* normalize variables

### Task 5 - reflection

* Does your team work with tabular data?
* If yes, discuss possible usecases in your team based on what you have learned in this session

### Task 6 (optional, but highly valued)

We are half way through the course! Please spend a few minutes individually and fill out [this feedback form](https://forms.gle/68B7XcxSkeXnFiin8)