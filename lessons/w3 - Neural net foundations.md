# Week 3 - Neural net foundations

## Before the lab session

Watch Video Lesson 3: 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/hBBOjCiFcuo/0.jpg)](https://www.youtube.com/watch?v=hBBOjCiFcuo)


## Lab session

### Task 1

a) Run through, and try to understand what's going on in the [notebook of the week](https://www.kaggle.com/code/jhoward/how-does-a-neural-net-really-work)

b) You can think of the example with the quadratic function as an analogy to the model you created in the first lesson. Try to explain the analogy to each other. What do the x and y-values of the quadratic function correspond to?

c) Look through [these slides](https://docs.google.com/presentation/d/1GYZxCM7KlSgsB3bum1FU21lZFAeDg1oWAn4tkP15Xa8/edit?usp=sharing) together. Do the illustrations match your understanding of the training process?

d) Scroll to the cell where you can change the values of a, b and c to fit the function, and MAE is displayed. Modify the code so that the following sentences are displayed above the graph. The words "increased" and "decreased", and the numberical values at the end of the sentences should be updated when the sliders are changed:

parameter a should be increased because params.grad[0] is -1.3

parameter b should be decreased because params.grad[1] is 0.2

parameter c should be increased because params.grad[2] is -0.5

Hint 1: if you are comfortable with analytical derivation, and are new to numerical derivation using pytorch, remember that you can look at slide 2 [here](https://docs.google.com/presentation/d/1GYZxCM7KlSgsB3bum1FU21lZFAeDg1oWAn4tkP15Xa8/edit?usp=sharing)

Hint 2: if you have trouble with the function `plot_function` , try to add `with torch.no_grad():` either to the function, or when the function is called.

e) Are you able to explain how the process of fitting the three parameters can be automated?

### Task 2

a) scroll to the cell where the function `double_relu` is defined. Create a new cell below it and define a function called `triple_relu` which returns the sum of three rectified linear functions

b) create an interactive plot with 6 sliders, displaying the `triple_relu` function

c) add a scatter plot displaying the quadratic function with noise to the interactive plot. Can you make `triple_relu` approximate the scatter plot?

d) modify the function `rectified_linear` so that it returns a normal linear function instead of a rectified linear function. How does this affect the interactive plot displaying `triple_relu`?

e) Try to describe the training process of a neural network to each other. There are a lot of new concepts, so don't worry if you cannot grasp it all. We will revisit this in session 5.

### Task 3 (optional)

Open your notebook from the first session. Take a look at the different architectures [here](https://www.kaggle.com/code/jhoward/which-image-models-are-best/notebook), and train your model again using a different model. Can you make your model perform better?