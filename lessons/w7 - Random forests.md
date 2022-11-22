# Week 7 - Random forests 

## Before the lab session

Watch Video Lesson 7:

Jeremy starts going through notebook 7 already towards the end of the previous video, starting here at 1:26:40:
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/_rXzeWq4C6w/0.jpg)](https://youtu.be/_rXzeWq4C6w?t=5200)

The rest of notebook 7 is explained until 51:55 in this week's video. 

The last 40 minutes of the video are part of a walk-through for creating a machine learning model for one of the Kaggle competitions which, while not directly relevant to this week's topic and thus more of a bonus, shows a concrete example on how to apply the techniques learned so far to a specific problem.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/AdhG64NF76E/0.jpg)](https://www.youtube.com/watch?v=AdhG64NF76E)

## Lab session

### Task 1

Run through, and try to understand what's going on in the notebook of the week:

Kaggle:
[Week 7 Notebook](https://www.kaggle.com/code/jhoward/how-random-forests-really-work)

Colab:
[Week 7 Notebook](https://colab.research.google.com/github/fastai/course22/blob/master/07-how-random-forests-really-work.ipynb) (Copy to your drive if you want changes to persist)

### Task 2 

- We chose a previous Kaggle competition as a good scenario to test your random forest skills. You will be predicting a full year worth of sales for three items at two stores located in three different countries. This dataset is completely fictional, but contains many effects you see in real-world data, e.g., weekend and holiday effect, seasonality, etc. The dataset is small enough to allow you to try numerous different modeling approaches.
- Files can be either downloaded [here](https://drive.google.com/file/d/1arhntFdrnpdacCOckAwlD9Sf1gSiSJjc/view?usp=sharing) or found directly in [Kaggle](https://www.kaggle.com/competitions/tabular-playground-series-jan-2022/data) if you want to work there. Kaggle also has the [task description](https://www.kaggle.com/competitions/tabular-playground-series-jan-2022/overview).  The dataset consists of:
    - train.csv - the training set, which includes the sales data for each date-country-store-item combination.
    - test.csv - the test set; your task is to predict the corresponding item sales for each date-country-store-item combination


We recommend using random forests in a similar way it is presented in the lecture. 

NB: If you are using the notebook from the lecture as a template, you should jump straight from where you create _trn_xs_, _trn_y_, _val_xs_ and _val_y_ to the cell where you import _DecisionTreeClassifier_. 
Additionally, you will have to use a _DecisionTreeRegressor_ instead, since for this task we are performing regression instead of classification.

Other algorithms (such as XGBoost) should work just as well, but lack the detailed instructions that the lecture notebook provides.

As a baseline to compare against, a simple model we put together (and which you might be able to beat) had a MAPE of just under 6% for random forests and just under 5% for XGBoost. 
Alternatively you can submit your results to the Kaggle competition and see how your results rate against the wider community!
