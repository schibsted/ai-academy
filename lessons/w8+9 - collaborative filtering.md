# Week 8 + 9 - Collaborative Filtering
In week 8 and 9 we will introduce two new concepts: 
First we will learn a new high-level library that can be used instead of fast.ai: `Pytorch-Lightning`. 
Secondly, we will learn about recommender systems and the widely popular matrix factorization model. 
In particular, we will use pytorch-lightning to train a news recommender system.

We have divided the tasks into part 1 and part 2. 

## Week 8

### Before the lab session

NB: This week has 2hrs 15min of lectures.

**Watch video lesson 7** (The first 60 minutes is of various topics and some topics can be skimmed (although still useful). But its important to understand cross entropy!) )


[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/p4ZZq0736Po/0.jpg)](https://www.youtube.com/watch?v=p4ZZq0736Po)

Watch the first 30 minutes of lesson 8:  

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/htiNBPxcXgo/0.jpg)](https://youtu.be/htiNBPxcXgo)

Use the notebook while watching the lecture, and make sure you follow the steps approximately. 
The notebook Jeremy use can be found [here](https://www.kaggle.com/code/jhoward/collaborative-filtering-deep-dive/notebook).

If you have time, you can also start looking at the [pytorch-lightning framework](https://pytorch-lightning.readthedocs.io/en/stable/starter/introduction.html).
)

### Lab session
In this session we will familiarize us with the high level framework pytorch lightning, and if time we will start applying it to a news recommender system. If you dont manage to do everything, do not worry, we will continue in week 9!

First, go through the [pytorch-lightning framework](https://pytorch-lightning.readthedocs.io/en/stable/starter/introduction.html).
There you will see how you can set up training a model. Understand the steps, and discuss with your group how it is different from fast.ai.

Secondly, we will use pytorch lightning to build a news recommender system!
We will use the [MIND news dataset from microsoft](https://www.kaggle.com/datasets/arashnic/mind-news-dataset).


#### Tasks

### News Recommender "mini project"
We have prepared a script that does some pre-processing and train a simple collaborative filtering model that we will work on in the class:
https://www.kaggle.com/code/jacobwelander/mind-recommender-from-scratch-2023

**There is no need to understand all the preprocessing steps here. You can quickly skim through that and start at "Output of data preprocessing"**.

#### Week 8 exercises

- In the pytorch lightning module, create a `self.forward()` function that takes a batch of users+items and compute relevancy scores
- Modify `self.training_step()` to use the `self.forward()` function.
- How can you use `self.forward()` to recommend relevant news items from this model? Implement it!

The idea for the three tasks above is that we create a forward function that can compute the relevancy score between a tensor of users and items.
This is useful because we can use the forward function both when training but also in the predict (or recommend) phase of the model. 

The forward function should be in a format so that the start of the `step` function looks like:
```
def step(self, batch, batch_idx, phase="train"):
  score_click = self.forward(batch['userIdx'], batch['click'])
  
  neg_sample = torch.randint_like(batch["click"],1,self.num_items)
  score_noclick = self.forward(batch['userIdx'], neg_sample)
```

- Does the results in the previous step make sense? How do you validate it?
- The current model does not print any statistics like when fastai is training. Check out [this link to see how we could make something simple to print out losses after each epoch](https://stackoverflow.com/questions/71236391/pytorch-lightning-print-accuracy-and-loss-at-the-end-of-each-epoch). Do you see how to print validation loss as well?

## Week 9

### Before the lab session
MOVE SOME OF THE LECTURE FROM PART 1 TO HERE AND ADD SOMETHING ABOUT "SLATE LIKELIHOOD".

#### Week 9 exercises
Play around with the shell and see if you can modify it in any direction. Either by improving the model, or by adding metrics that are useful for us to understand the performance of the model. Examples can be (in no particular order):

##### Training tools
- Implement some metrics in the model. E.g. we could calculate the accuracy of the model choosing between the positive and negative example. See [here](https://torchmetrics.readthedocs.io/en/stable/pages/lightning.html).
- Try using a [logger](https://pytorch-lightning.readthedocs.io/en/latest/api_references.html#loggers) to visualize the training in a dashboard.
- Visualize the location of users and items using e.g. a Tensorboard logger. Does the similarity of items make sense?

##### Model modifications/improvements
- Try to add user or item biases to the model. Does it help? (and for the theoretical nerds: Should it help?)
- Add l2 regularization to the parameters to reduce any potential overfitting,
- Implement a model that uses a random negative example instead of the in the slate. How does this change your assumption about user behaviour?
- Use more than 1 negative sample when training


##### Advanced
- We are doing news recommendations, and the recency of the news article can be useful. Can you implement time decay into the model? (you would need to change the dataset+ dataloaders)
- In the raw dataset we have the text from each news article. Can we utilize a language model to get a vector representation of each item? Then how should we use this to improve the recommender system above?
