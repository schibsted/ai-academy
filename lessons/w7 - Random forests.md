# Week 7 - Random forests 

## Before the lab session

Watch Video Lesson 7:

Jeremy starts going through notebook 7 already towards the end of the previous video, starting here at 1:26:40:
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/_rXzeWq4C6w/0.jpg)](https://youtu.be/_rXzeWq4C6w?t=5200)

The rest of notebook 7 is explained until 51:55 in this week's video. 

The last 40 minutes of the video are part of a walk-through for creating a machine learning model for one of the Kaggle competitions which, 
while not directly relevant to this week's topic and thus more of a bonus, shows a concrete example on how to apply the techniques learned so far to a specific problem.
Understanding the general can also be useful for this week's tasks. 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/AdhG64NF76E/0.jpg)](https://www.youtube.com/watch?v=AdhG64NF76E)

## Lab session

This lab's notebook is https://www.kaggle.com/code/stefanwender/ai-academy-tabular-task .

(This week's video is based on a Kaggle notebook that can be used as a reference: [Week 7 Notebook](https://www.kaggle.com/code/jhoward/how-random-forests-really-work)
Jeremy also touches upon the book chapter, so in case you are wondering about the code for Model Interpretation and later, that is available [here](https://github.com/fastai/fastbook/blob/master/09_tabular.ipynb) (unfortunately not on Kaggle).

In this lab, you will work with a simple model that predicts reservation cancellations of hotel guests, using things learned during the course.
The source of the task is [a Kaggle tabular modelling competition](https://www.kaggle.com/competitions/playground-series-s3e7), which uses [a synthetic data set](https://www.kaggle.com/datasets/gauravduttakiit/reservation-cancellation-prediction) that is based on a 'real' reservation
cancellation data set.
A synthetic dataset matches the characteristics of the original (attributes, distribution of attributes etc.) nearly entirely but has different values.


Currently, this notebook contains a simple implementation that
- loads the training and validation files,
- trains a very simple (OneR) decision-tree model using 80% of the training data and tests against the remaining 20%,
- creates predictions for the Kaggle validation data and stores those predictions in a csv format that can be submitted to the competition.


Your tasks are to improve upon this implementation in the following ways:
1. Improve the data preprocessing and feature engineering: Using the techniques you learned in this week's video and previous lessons, select the most relevant attributes and, through cleaning and modification
   (where necessary and useful) try to improve model performance.
2. Optimise the decision tree model: Currently the tree only uses a single rule and already achieves nearly 70% accuracy in the test data and close to this in the validation/competition data.
   How much can you improve this through tweaking the tree parameters - or using a random forest classifier instead?
3. (Optional) Create an XGBoost classifier: Jeremey mentions XGBoost only briefly, but in many instances where tabular data is involved, XGBoost models outperform simple decision tree/random forests. They are also
   part of the sklearn library, however need slightly more effort during the data preparation phase as XGBoost, out of the box, cannot handle categorical variables. Using the encoding methods presented in the course
   (dummy variables or one-hot encoding) solves this issue. How does the XGBoost performance compare to the other algorithms?
