solutioins to the applied exercises in islr2 ch4
================
Wenwen Kong
8/6/2022

### Problem 13

This question should be answered using the `Weekly` data set, which is
part of the `ISLR2` package. This data is similar in nature to the
`Smarket` data from this chapter’s lab, except that it contains 1,089
weekly returns for 21 years, from the beginning of 1990 to the end of
2010.

1)  Produce some numerical and graphical summaries of the `Weekly` data.
    Do there appear to be any patterns?

2)  Use the full data set to perform a logistic regression with
    `Direction` as the response and the five lag variables plus `Volume`
    as predictors. Use the summary function to print the results. Do any
    of the predictors appear to be statistically significant? If so,
    which ones?

3)  Compute the confusion matrix and overall fraction of correct
    predictions. Explain what the confusion matrix is telling you about
    the types of mistakes made by logistic regression.

4)  Now fit the logistic regression model using a training data period
    from 1990 to 2008, with `Lag2` as the only predictor. Compute the
    confusion matrix and the overall fraction of correct predictions for
    the held out data (that is, the data from 2009 and 2010).

5)  Repeat (d) using LDA.

6)  Repeat (d) using QDA.

7)  Repeat (d) using KNN with ![K
    = 1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K%20%3D%201
    "K = 1").

8)  Repeat (d) using naive Bayes.

9)  Which of these methods appears to provide the best results on this
    data?

10) Experiment with different combinations of predictors, including
    possible transformations and interactions, for each of the methods.
    Report the variables, method, and associated confusion matrix that
    appears to provide the best results on the held out data. Note that
    you should also experiment with values for
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K
    "K") in the KNN classifier.

### Problem 14

In this problem, you will develop a model to predict whether a given car
gets high or low gas mileage based on the `Auto` data set.

1)  Create a binary variable, `mpg01`, that contains a
    ![1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;1
    "1") if `mpg` contains a value above its median, and a
    ![0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0
    "0") if `mpg` contains a value below its median. You can compute the
    median using the `median()` function. Note you may find it helpful
    to use the `data.frame()` function to create a single data set
    containing both `mpg01` and the other `Auto` variables.

2)  Explore the data graphically in order to investigate the association
    between `mpg01` and the other features. Which of the other features
    seem most likely to be useful in predicting `mpg01`? Scatterplots
    and boxplots may be useful tools to answer this question. Describe
    your findings.

3)  Split the data into a training set and a test set.

4)  Perform LDA on the training data in order to predict `mpg01` using
    the variables that seemed most associated with `mpg01` in (b). What
    is the test error of the model obtained?

5)  Perform QDA on the training data in order to predict `mpg01` using
    the variables that seemed most associated with `mpg01` in (b). What
    is the test error of the model obtained?

6)  Perform logistic regression on the training data in order to predict
    `mpg01` using the variables that seemed most associated with `mpg01`
    in (b). What is the test error of the model obtained?

7)  Perform naive Bayes on the traininig data in order to predict
    `mpg01` using the variables that seemed most associated with `mpg01`
    in (b). What is the test error of the model obtained?

8)  Perform KNN on the training data, with several values of
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K
    "K"), in order to predict `mpg01`. Use only the variables that
    seemed most associated with `mpg01` in (b). What test errors do you
    obtain? Which value of
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K
    "K") seems to perform the best on this data set?

### Problem 15

This problem involves writing functions.

1)  Write a function, `Power()`, that prints out the result of raising 2
    to the 3rd power. In other words, your function should compute
    ![2^3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;2%5E3
    "2^3") and print out the results. *Hint: Recall that `x^a` raises
    `x` to the power `a`. Use the `print()` function to output the
    result.*

2)  Create a new function, `Power2()`, that allows you to pass *any* two
    numbers, `x` and `a`, and prints out the value of `x^a`. You can do
    this by beginning your function with the line \> Power2 \<-
    function(x, a) {

You should be able to call your function by entering, for instance, \>
Power2(3, 8)

on the command line. This should output the value of
![3^8](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;3%5E8
"3^8"), namely,
![6,561](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;6%2C561
"6,561").

3)  Using the `Power2()` function that you just wrote, compute
    ![10^3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;10%5E3
    "10^3"),
    ![8^{17}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;8%5E%7B17%7D
    "8^{17}"), and
    ![131^3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;131%5E3
    "131^3").

4)  Now create a new function, `Power3()`, that actually *returns* the
    result `x^a` as an `R` object, rather than simply printing it to the
    screen. That is, if you store the value `x^a` in an object called
    `result` within your function, then you can simply `return()` this
    result, using the following line: \> return(result)

The line above should be the last line in your function, before the `}`
symbol.

5)  Now using the `Power3()` function, create a plot of ![f(x) =
    x^2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;f%28x%29%20%3D%20x%5E2
    "f(x) = x^2"). The
    ![x](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;x
    "x")-axis should display a range of integers from
    ![1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;1
    "1") to
    ![10](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;10
    "10"), and the
    ![y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;y
    "y")-axis should display
    ![x^2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;x%5E2
    "x^2"). Label the axes appropriately, and use an appropriate title
    for the figure. Consider displaying either the
    ![x](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;x
    "x")-axis, the
    ![y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;y
    "y")-axis, or both on the log-scale. You can do this by using `log =
    "x"`, `log = "y"`, `log ="xy"` as arguments to the `plot()`
    function.

6)  Create a function, `PlotPower()`, that allows you to create a plot
    of `x` against `x^a` for a fixed `a` and for a rainge of values of
    `x`. For instance, if you call \> PlotPower(1:10, 3)

then a plot should be created with an
![x](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;x
"x")-axis taking on values 1, 2, …, 10, and a
![y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;y
"y")-axis taking on values
![1^3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;1%5E3
"1^3"),
![2^3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;2%5E3
"2^3"), …,
![10^3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;10%5E3
"10^3").

### Problem 16

Using the `Boston` data set, fit classification models in order to
predict whether a given census tract has a crime rate above or below the
median. Explore logistic regression, LDA, naive Bayes, and KNN models
using various subsets of the predictors. Describe your findings. *Hint:
You will have to create the response variable yourself, using the
variables that are contained in the `Boston` data set.*
