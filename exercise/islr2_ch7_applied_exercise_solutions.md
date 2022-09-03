solutioins to the applied exercises in islr2 ch7
================
Wenwen Kong
9/2/2022

### Problem 6

In this exercise, you will further analyze the `Wage` data set
considered throughout this chapter.

1)  Perform polynomial regression to predict `wage` using `age`. Use
    cross-validation to select the optimal degree
    ![d](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;d "d")
    for the polynomial. What degree was chosen, and how does this
    compare to the results of hypothesis testing using
    ![ANOVA](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;ANOVA "ANOVA")?
    Make a plot of the resulting polynomial fit to the data.

2)  Fit a step function to predict `wage` using `age`, and perform
    cross-validation to choose the optimal number of cuts. Make a plot
    of the fit obtained.

### Problem 7

The `Wage` data set contains a number of other features not explored in
this chapter, such as marital status (`maritl`), job class (`jobclass`),
and others. Explore the relationships between some of these other
predictors and `wage`, and use non-linear fitting techniques in order to
fit flexible models to the data. Create plots of the results obtained,
and write a summary of your findings.

### Problem 8

Fit some of the non-linear models investigated in this chapter to the
`Auto` data set. Is there evidence for non-linear relationships in this
data set? Create some informative plots to justify your answer.

### Problem 9

This question uses the variables `dis` (the weighted mean of distances
to five Boston employment centers) and `nox` (nitrogen oxides
concentration in parts per 10 million) from the `Boston` data. We will
treat `dis` as the predictor and `nox` as the response.

1)  Use the `poly()` function to fit a cubic polynomial regression to
    predict `nox` using `dis`. Report the regression output, and plot
    the resulting data and polynomial fits.

2)  Plot the polynomial fits for a range of different polynomial degrees
    (say, from
    ![1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;1 "1")
    to
    ![10](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;10 "10")),
    and report the associated residual sum of squares.

3)  Perform cross-validation or another approach to select the optimal
    degree for the polynomial, and explain your results.

4)  Use the `bs()` function to fit a regression spline to predict `nox`
    using `dis`. Report the output for the fit using four degrees of
    freedom. How did you choose the knots? Plot the resulting fit.

5)  Now fit a regression spline for a range of degrees of freedom, and
    plot the resulting fits and report the resulting
    ![RSS](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;RSS "RSS").
    Describe the results obtained.

6)  Perform cross-validation or another approach in order to select the
    best degrees of freedom for a regression spline on this data.
    Describe your results.

### Problem 10

This question relates to the `College` data set.

1)  Split the data into a training set and a test set. Using
    out-of-state tuition as the response and the other variables as the
    predictors, perform forward stepwise selection on the training set
    in order to identify a satisfactory model that uses just a subset of
    the predictors.

2)  Fit a
    ![GAM](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;GAM "GAM")
    on the training data, using out-of-state tuition as the response and
    the features selected in the previous step as the predictors. Plot
    the results, and explain your findings.

3)  Evaluate the model obtained on the test set, and explain the results
    obtained.

4)  For which variables, if any, is there evidence of a non-linear
    relationship with the response?

### Problem 11

In Section 7.7, it was mentioned that
![GAMs](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;GAMs "GAMs")
are generally fit using a *backfitting* approach. The idea behind
backfitting is actually quite simple. We will now explore backfitting in
the context of multiple linear regression.

Suppose that we would like to perform multiple linear regression, but we
do not have software to do so. Instead, we only have software to perform
simple linear regression. Therefore, we take the following iterative
approach: we repeatedly hold all but one coefficient estimate fixed at
its current value, and update only that coefficient estimate using a
simple linear regression. The process is continued until *convergence* -
that is, until the coefficient estimates stop changing.

We now try this out on a toy example.

1)  Generate a response
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y")
    and two predictors
    ![X\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X_%7B1%7D "X_{1}")
    and
    ![X\_{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X_%7B2%7D "X_{2}"),
    with
    ![n = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%20100 "n = 100").

2)  Initialize
    ![\hat{\beta\_{1}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B1%7D%7D "\hat{\beta_{1}}")
    to take on a value of your choice. It does not matter what value you
    choose.

3)  Keeping
    ![\hat{\beta\_{1}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B1%7D%7D "\hat{\beta_{1}}")
    fixed, fit the model
    ![Y - \hat{\beta\_{1}}X\_{1} = \beta\_{0} + \beta\_{2}X\_{2} + \epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20-%20%5Chat%7B%5Cbeta_%7B1%7D%7DX_%7B1%7D%20%3D%20%5Cbeta_%7B0%7D%20%2B%20%5Cbeta_%7B2%7DX_%7B2%7D%20%2B%20%5Cepsilon "Y - \hat{\beta_{1}}X_{1} = \beta_{0} + \beta_{2}X_{2} + \epsilon").

You can do this as follows: \> a \<- y - beta1 \* x1 \> beta2 \<- lm(a
\~ x2)$coef\[2\]

4)  Keeping
    ![\hat{\beta\_{2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B2%7D%7D "\hat{\beta_{2}}")
    fixed, fit the model
    ![Y - \hat{\beta\_{2}}X\_{2} = \beta\_{0} + \beta\_{1}X\_{1} + \epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20-%20%5Chat%7B%5Cbeta_%7B2%7D%7DX_%7B2%7D%20%3D%20%5Cbeta_%7B0%7D%20%2B%20%5Cbeta_%7B1%7DX_%7B1%7D%20%2B%20%5Cepsilon "Y - \hat{\beta_{2}}X_{2} = \beta_{0} + \beta_{1}X_{1} + \epsilon").

You can do this as follows: \> a\<- y - beta2 \* x2 \> beta1 \<- lm(a \~
x1)$coef\[2\]

5)  Write a for loop to repeat (c) and (d)
    ![1,000](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;1%2C000 "1,000")
    times. Report the estimates of
    ![\hat{\beta\_{0}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B0%7D%7D "\hat{\beta_{0}}"),
    ![\hat{\beta\_{1}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B1%7D%7D "\hat{\beta_{1}}"),
    and
    ![\hat{\beta\_{2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B2%7D%7D "\hat{\beta_{2}}")
    at each iteration of the for loop. Create a plot in which each of
    these values is displayed, with
    ![\hat{\beta\_{0}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B0%7D%7D "\hat{\beta_{0}}"),
    ![\hat{\beta\_{1}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B1%7D%7D "\hat{\beta_{1}}"),
    and
    ![\hat{\beta\_{2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B2%7D%7D "\hat{\beta_{2}}")
    each shown in a different color.

6)  Compare your answer in (e) to the results of simply performing
    multiple linear regression to predict
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y")
    using
    ![X\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X_%7B1%7D "X_{1}")
    and
    ![X\_{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X_%7B2%7D "X_{2}").
    Use the `abline()` function to overlay those multiple linear
    regression coefficient estimates on the plot obtained in (e).

7)  On this data set, how many backfitting iterations were required in
    order to obtain a “good” approximation to the multiple regression
    coefficient estimates?

### Problem 12

This problem is a continuation of the previous exercise. In a toy
example with
![p = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p%20%3D%20100 "p = 100"),
show that one can approximate the multiple linear regression coefficient
estimates by repeatedly performing simple linear regression in a
backfitting procedure. How many backfitting iterations are required in
order to obtain a “good” approximation to the multiple regression
coefficient estimates? Create a plot to justify your answer.
