# Week 8 - Collaborative Filtering 

## Before the lab session
NB: This week has 2hrs 15min of lectures.

Watch video lesson 7 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/p4ZZq0736Po/0.jpg)](https://www.youtube.com/watch?v=p4ZZq0736Po)

Watch the first 30 minutes of lesson 8:  

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/htiNBPxcXgo/0.jpg)](https://youtu.be/htiNBPxcXgo)


## Lab session
In this lab session we will try to build a recommender system for news. 
We will use the MIND news dataset from microsoft (https://www.kaggle.com/datasets/arashnic/mind-news-dataset).
I have prepared a script that does some pre-processing and train a simple collaborative filtering model.
Instead of using the fast.ai framework, we will use pytorch lightning as our high level pytorch framework. 
I am sure you will see a lot of similarities (e.g. all pytorch stuff is equivalent as we're still using pytorch):

https://www.kaggle.com/code/enemis/mind-recommender-from-scratch (I am still working on this, will be ready for lab session)


### Tasks
- Make sure you understand the lecture material (video and notebook). The notebook Jeremy use can be found [here](https://www.kaggle.com/code/jhoward/collaborative-filtering-deep-dive/notebook).

### News Recommender "mini project"
We have prepared a small news recsys "shell" to play around with in this class:
https://www.kaggle.com/code/enemis/mind-recommender-from-scratch

#### Part 1

- In the pytorch lightning module, create a `self.forward()` function that takes a batch of users+items and compute relevancy scores
- Modify `self.training_step()` to use the `self.forward()` function.
- How can you use `self.forward()` to recommend relevant news items from this model? Implement it!

The idea for the three tasks above is that we create a forward function that can compute the score between a tensor of users and items. This can then later be used in the predict (or recommend) phase of the model. It should be in a format so that the start of the `step` function looks like:
```
def step(self, batch, batch_idx, phase="train"):
  score_click = self.forward(batch['userIdx'], batch['click'])
  score_noclick = self.forward(batch['userIdx'], batch['noclick'])
```

- Does the results in the previous step make sense? How do you validate it?
- The current model does not print any statistics like when fastai is training. Check out [this link to see how we could make something simple to print out losses after each epoch](https://stackoverflow.com/questions/71236391/pytorch-lightning-print-accuracy-and-loss-at-the-end-of-each-epoch). Do you see how to print validation loss as well?

#### Part 2
Play around with the shell and see if you can modify it in any direction. Either by improving the model, or by adding metrics that are useful for us to understand the performance of the model. Examples can be (in no particular order):

##### Training tools
- Implement some metrics in the model. E.g. we could calculate the accuracy of the model choosing between the positive and negative example. See [here](https://torchmetrics.readthedocs.io/en/stable/pages/lightning.html).
- Try using a [logger](https://pytorch-lightning.readthedocs.io/en/latest/api_references.html#loggers) to visualize the training in a dashboard.
- Visualize the location of users and items using e.g. a Tensorboard logger. Does the similarity of items make sense?

##### Model modifications/improvements
- Try to add user or item biases to the model. Does it help? (and for the theoretical nerds: Should it help?)
- Add l2 regularization to the parameters to reduce any potential overfitting,
- Implement a model that uses a random negative example instead of the in the slate. How does this change your assumption about user behaviour?
- Use more than 1 negative sample when training (either by using the sampled negative or you use more elements in the "noclicks" column)


##### Advanced
- We are doing news recommendations, and the recency of the news article can be useful. Can you implement time decay into the model? (you would need to change the dataset+ dataloaders)
- In the raw dataset we have the text from each news article. Can we utilize a language model to get a vector representation of each item? Then how should we use this to improve the recommender system above?
