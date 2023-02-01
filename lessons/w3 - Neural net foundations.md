# Week 3 - Neural net foundations

## Before the lab session

Watch Video Lesson 3: 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/hBBOjCiFcuo/0.jpg)](https://www.youtube.com/watch?v=hBBOjCiFcuo)


## Lab session

### Task 1

Run through, and try to understand what's going on in the [notebook of the week](https://www.kaggle.com/code/jhoward/how-does-a-neural-net-really-work)

### Task 2

We have generated quadratic data for you, by choosing some parameters a, b and c, and added noise. Each group has different noise in their dataset. You can find the dataset in the shared drive, in the group-folder.

#### a) 
Import the data into the notebook of the week. In Kaggle, you can hover over the data, and a "copy file path" option will appear to the right. You can use the pandas-function read_csv() to read the data into your notebook. 
#### b) 
Try to figure out what parameters we used to generate the data, using gradient decent to fit the three parameters a, b and c.
#### c) 
Let's see how close you get. Post your results in the slack-channel
#### d)
Create a function similar to "double_relu()", containing 8 relu's instead of 2. Use gradient decent to fit the 16 parameters to the data. Make a plot containing both the data with noice, the quadratic fit from c), and the relu approximation.

### Task 3 

Reproduce the titanic example from the video in a spreadsheet. We have prepared a spreadsheet for you, and instructions. You'll find both in the shared drive, in the folder for this session.

Note: if you prefer to use Excel you can. We have not managed to make this work in Libre Office Calc. Google-sheets will work for everyone, regardless of operating system.

