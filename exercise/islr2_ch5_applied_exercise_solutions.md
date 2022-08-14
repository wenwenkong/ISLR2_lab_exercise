solutioins to the applied exercises in islr2 ch5
================
Wenwen Kong
8/13/2022

### Problem 5

In Chapter 4, we used logistic regression to predict the probability of
`default` using `income` and `balance` on the `Default` data set. We
will now estimate the test error of this logistic regression model using
the validation set approach. Do not forget to set a random seed before
beginning your analysis.

1)  Fit a logistic regression model that uses `income` and `balance` to
    predict `default`.

2)  Using the validation set approach, estimate the test error of this
    model. In order to do this, you must perform the following steps:

<!-- -->

    i. Split the sample set into a training set and a validation set.

    ii. Fit a multiple logistic regression model using only the training observations. 

    iii. Obtain a prediction of default status for each individual in the validation set by computing the posterior probability of default for that individual, and classifying the individual to the `default` category if the posterior probability is greater than $0.5$.

    iv. Compute the validation set error, which is the fraction of the observations in the validation set that are misclassified. 

3)  Repeat the process in (b) three times, using three different splits
    of the observations into a training set and a validation set.
    Comment on the results obtained.

4)  Now consider a logistic regression model that predicts the
    probability of `default` using `income`, `balance`, and a dummy
    variable for `student`. Estimate the test error for this model using
    the validation set approach. Comment on whether or not including a
    dummy variable for `student` leads to a reduction in the test error
    rate.

### Problem 6

We continue to consider the use of a logistic regression model to
predict the probability of `default` using `income` and `balance` on the
`Default` data set. In particular, we will now compute estimates for the
standard errors of the `income` and `balance` logistic regression
coefficients in two different ways: (1) using the bootstrap, and (2)
using the standard formula for computing the standard errors in the
`glm()` function. Do not forget to set a random seed before beginning
your analysis.

1)  Using the `summary()` and `glm()` functions, determine the estimated
    standard errors for the coefficients associated with `income` and
    `balance` in a multiple logistic regression model that uses both
    predictors.

2)  Write a function, `boot.fn()`, that takes as input the `Default`
    data set as well as an index of the observations, and that outputs
    the coefficient estimates for `income` and `balance` in the multiple
    logistic regression model.

3)  Use the `boot()` function together with your `boot.fn()` function to
    estimate the standard errors of the logistic regression coefficients
    for `income` and `balance`.

4)  Comment on the estimated standard errors obtained using the `glm()`
    function and using your bootstrap function.

### Problem 7

In Sections 5.3.2 and 5.3.3, we saw that the `cv.glm()` function can be
used in order to compute the LOOCV test error estimate. Alternatively,
one could compute those quantities using just the `glm()` and
`predict.glm()` functions, and a for loop. You will now take this
approach in order to compute the LOOCV error for a simple logistic
regression model on the `Weekly` data set. Recall that in the context of
classification problems, the LOOCV error is given in (5.4).

1)  Fit a logistic regression model that predicts `Direction` using
    `Lag1` and `Lag2`.

2)  Fit a logistic regression model that predicts `Direction` using
    `Lag1` and `Lag2` *using all but the first observation*.

3)  Use the model from (b) to predict the direction of the first
    observation. You can do this by predicting that the first
    observation will go up if P(`Direction` = `"Up"` \| `Lag1`, `Lag2`)
    \> 0.5. Was this observation correctly classified?

4)  Write a for loop from
    ![i = 1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;i%20%3D%201 "i = 1")
    to
    ![i = n](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;i%20%3D%20n "i = n"),
    where
    ![n](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n "n")
    is the number of observations in the data set, that performs each of
    the following steps:

<!-- -->

    i. Fit a logistic regression model using all but the $i$th observation to predict `Direction` using `Lag1` and `Lag2`.

    ii. Compute the posterior probability of the market moving up for the $i$th observation. 

    iii. Use the posterior probability for the $i$th observation in order to predict whether or not the market moves up. 

    iv. Determine whether or not an error was made in predicting the direction for the $i$th observation. If an error was made, then indicate this as 1, and otherwise indicate it as 0. 

5)  Take the average of the
    ![n](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n "n")
    numbers obtained in (d)iv in order to obtain the LOOCV estimate for
    the test error. Comment on the results.

### Problem 8.

We will now perform cross-validation on a simulated data set.

1)  Generate a simulated data set as follows: \> set.seed(1) \> x \<-
    rnorm(100) \> y \<- x - 2 \* x^2 + rnorm(100)

In this data set, what is
![n](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n "n")
and what is
![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")?
Write out the model used to generate the data in equation form.

2)  Create a scatterplot of
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X "X")
    against
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y").
    Comment on what you find.

3)  Set a random seed, and then compute the LOOCV errors that result
    from fitting the following four models using least squares:

<!-- -->

    i. $Y = \beta_{0} + \beta_{1}X + \epsilon$

    ii. $Y = \beta_{0} + \beta_{1}X + \beta_{2}X^{2} + \epsilon$

    iii. $Y = \beta_{0} + \beta_{1}X + \beta_{2}X^{2} + \beta_{3}X^{3} + \epsilon$

    iv. $Y = \beta_{0} + \beta_{1}X + \beta_{2}X^{2} + \beta_{3}X^{3} + \beta_{4}X^{4} + \epsilon$

    Note you may find it helpful to use the `data.frame()` function to create a single data set containing both $X$ and $Y$.

4)  Repeat (c) using another random seed, and report your results. Are
    your results the same as what you got in (c)? Why?

5)  Which of the models in (c) had the smallest LOOCV error? Is this
    what you expected? Explain your answer.

6)  Comment on the statistical significance of the coefficient estimates
    that results from fitting each of the models in (c) using least
    squares. Do these results agree with the conclusions drawn based on
    the cross-validation results?

### Problem 9

We will now consider the `Boston` housing data set, from the `ISLR2`
library.

1)  Based on this data set, provide an estimate for the population mean
    of `medv`. Call this estimate
    ![\hat{\mu}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D "\hat{\mu}").

2)  Provide an estimate of the standard error of
    ![\hat{\mu}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D "\hat{\mu}").
    Interpret this result. *Hint: We can compute the standard error of
    the sample mean by dividing the sample standard deviation by the
    square root of the number of observations.*

3)  Now estimate the standard error of
    ![\hat{\mu}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D "\hat{\mu}")
    using the bootstrap. How does this compare to your answer from (b)?

4)  Based on your bootstrap estimate from (c), provide a
    ![95\\%](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;95%5C%25 "95\%")
    confidence interval for the mean of
    ![medv](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;medv "medv").
    Compare it to the results obtained using `t.test(Boston$medv)`.
    *Hint: You can approximate a 95% confidence interval using the
    formula
    ![\[\hat{\mu} - 2SE(\hat{\mu}), \hat{\mu} + 2SE(\hat{\mu})\]](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5B%5Chat%7B%5Cmu%7D%20-%202SE%28%5Chat%7B%5Cmu%7D%29%2C%20%5Chat%7B%5Cmu%7D%20%2B%202SE%28%5Chat%7B%5Cmu%7D%29%5D "[\hat{\mu} - 2SE(\hat{\mu}), \hat{\mu} + 2SE(\hat{\mu})]").*

5)  Based on this data set, provide an estimate,
    ![\hat{\mu}\_{med}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D_%7Bmed%7D "\hat{\mu}_{med}"),
    for the median value of `medv` in the population.

6)  We now would like to estimate the standard error of
    ![\hat{\mu}\_{med}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D_%7Bmed%7D "\hat{\mu}_{med}").
    Unfortunately, there is no simple formula for computing the standard
    error of the median. Instead, estimate the standard error of the
    median using the bootstrap. Comment on your findings.

7)  Based on this data set, provide an estimate for the tenth percentile
    of `medv` in Boston census tracts. Call this quantity
    ![\hat{\mu}\_{0.1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D_%7B0.1%7D "\hat{\mu}_{0.1}").
    (You can use the `quantile()` function.)

8)  Use the bootstrap to estimate the standard error of
    ![\hat{\mu}\_{0.1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cmu%7D_%7B0.1%7D "\hat{\mu}_{0.1}").
    Comment on your findings.
