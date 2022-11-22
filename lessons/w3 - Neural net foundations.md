# Week 3 - Neural net foundations

## Before the lab session

Watch Video Lesson 3: 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/hBBOjCiFcuo/0.jpg)](https://www.youtube.com/watch?v=hBBOjCiFcuo)


## Lab session

### Task 1

Run through, and try to understand what's going on in the notebook of the week:

Kaggle:
[Week 3 Notebook](https://www.kaggle.com/code/jhoward/how-does-a-neural-net-really-work)

Colab:
[Week 3 Notebook](https://colab.research.google.com/github/fastai/course22/blob/master/04-how-does-a-neural-net-really-work.ipynb) (Copy to your drive if you want changes to persist)

### Task 2

We have generated quadratic data for you, by choosing some parameters a, b and c, and added noise. Each group has different noise in their dataset.

#### a) 
Import the data into the notebook of the week.
#### b) 
Try to figure out what parameters we used to generate the data, using gradient decent to fit the three parameters a, b and c.
#### c) 
Let's see how close you get. Maybe the average value of all groups outperform the individual results? Post your results in the slack-channel, so we can check
#### d)
Create a function similar to "double_relu()", containing 8 relu's instead of 2. Use gradient decent to fit the 16 parameters to the data. Make a plot containing both the data with noice, the quadratic fit from c), and the relu approximation.

### Task 3 
Reproduce the titanic excel example which you can find in [this folder](https://github.com/fastai/course22/blob/master/xl). You can either do this in excel/ LibreOffice Calc or Google sheets. If you prefer Python, try to reproduce the computations in a Jupyter Notebook instead

The powerpoint on Gradients in Pytorch from todays session can be found [here](https://docs.google.com/presentation/d/1woiJM9y28p6tvVCLRjIAX0fTvUGXjvCf8uZ9fN9X-Vo/edit?usp=sharing)
