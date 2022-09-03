solutioins to the applied exercises in islr2 ch6
================
Wenwen Kong
9/2/2022

### Problem 8

In this exercise, we will generate simulated data, and will then use
this data to perform best subset selection.

1)  Use the `rnorm()` function to generate a predictor
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X "X")
    of length
    ![n = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%20100 "n = 100"),
    as well as a noise vector
    ![\epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cepsilon "\epsilon")
    of length
    ![n = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%20100 "n = 100").

2)  Generate a response vector

In Chapter 4, we used logistic regression to predict the probability of
`default` using `income` and `balance` on the `Default` data set. We
will now estimate the test error of this logistic regression model using
the validation set approach. Do not forget to set a random seed before
beginning your analysis.

1)  Fit a logistic regression model that uses `income` and `balance` to
    predict `default`.

2)  Generate a response vector
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y")
    of length
    ![n = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%20100 "n = 100")
    according to the model
    ![Y = \beta\_{0} + \beta\_{1}X + \beta\_{2}X^{2}+\beta\_{3}X^{3}+ \epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20%3D%20%5Cbeta_%7B0%7D%20%2B%20%5Cbeta_%7B1%7DX%20%2B%20%5Cbeta_%7B2%7DX%5E%7B2%7D%2B%5Cbeta_%7B3%7DX%5E%7B3%7D%2B%20%5Cepsilon "Y = \beta_{0} + \beta_{1}X + \beta_{2}X^{2}+\beta_{3}X^{3}+ \epsilon"),
    where
    ![\beta\_{0}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B0%7D "\beta_{0}"),
    ![\beta\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B1%7D "\beta_{1}"),
    ![\beta\_{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B2%7D "\beta_{2}"),
    and
    ![\beta\_{3}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B3%7D "\beta_{3}")
    are constants of your choice.

3)  Use the `regsubsets()` function to perform best subset selection in
    order to choose the best model containing the perdictors
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X "X"),
    ![X^{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%5E%7B2%7D "X^{2}"),
    …,
    ![X^{10}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%5E%7B10%7D "X^{10}").
    What is the best model obtained according to
    ![C\_{p}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;C_%7Bp%7D "C_{p}"),
    ![BIC](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;BIC "BIC"),
    and adjusted
    ![R^{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;R%5E%7B2%7D "R^{2}")?
    Show some plots to provide evidence for your answer, and report the
    coefficients of the best model obtained. Note you will need to use
    the `data.frame()` function to create a single data set containing
    both
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X "X")
    and
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y").

4)  Repeat (c), using forward stepwise selection and also using
    backwards stepwise selection. How does your answer compare to the
    results in (c)?

5)  Now fit a lasso model to the simulated data, again using
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X "X"),
    ![X^{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%5E%7B2%7D "X^{2}"),
    …,
    ![X^{10}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%5E%7B10%7D "X^{10}")
    as predictors. Use cross-validation to select the optimal value of
    ![\lambda](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Clambda "\lambda").
    Create plots of the cross-validation error as a function of
    ![\lambda](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Clambda "\lambda").
    Report the resulting coefficient estimates, and discuss the results
    obtained.

6)  Now generate a response vector
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y")
    according to the model
    ![Y = \beta\_{0} + \beta\_{7}X^{7} + \epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20%3D%20%5Cbeta_%7B0%7D%20%2B%20%5Cbeta_%7B7%7DX%5E%7B7%7D%20%2B%20%5Cepsilon "Y = \beta_{0} + \beta_{7}X^{7} + \epsilon"),
    and perform best subset selection and the lasso. Discuss the results
    obtained.

### Problem 9

In this exercise, we will predict the number of applications received
using the other variables in the `College` data set.

1)  Split the data set into a training set and a test set.

2)  Fit a linear model using least squares on the training set, and
    report the test error obtained.

3)  Fit a ridge regression model on the training set, with
    ![\lambda](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Clambda "\lambda")
    chosen by cross-validation. Report the test error obtained.

4)  Fit a lasso model on the training set, with
    ![\lambda](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Clambda "\lambda")
    chosen by cross-validation. Report the test error obtained, along
    with the number of non-zero coefficient estimates.

5)  Fit a
    ![PCR](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;PCR "PCR")
    model on the training set, with
    ![M](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;M "M")
    chosen by cross-validation. Report the test error obtained, along
    with the value of
    ![M](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;M "M")
    selected by cross-validation.

6)  Fit a
    ![PLS](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;PLS "PLS")
    model on the training set, with
    ![M](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;M "M")
    chosen by cross-validation. Report the test error obtained, along
    with the value of
    ![M](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;M "M")
    selected by cross-validation.

7)  Comment on the results obtained. How accurately can we predict the
    number of college applications received? Is there much difference
    among the test errors resulting from these five approaches?

### Problem 10

We have seen that as the number of features used in a model increases,
the training error will necessarily decrease, but the test error may
not. We will now explore this in a simulated data set.

1)  Generate a data set with
    ![p = 20](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p%20%3D%2020 "p = 20")
    features,
    ![n = 1,000](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%201%2C000 "n = 1,000")
    observations, and an associated quantitative response vector
    generated according to the model
    ![Y = X\beta + \epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20%3D%20X%5Cbeta%20%2B%20%5Cepsilon "Y = X\beta + \epsilon"),
    where
    ![\beta](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta "\beta")
    has some elements that are exactly equal to zero.

2)  Split your data set into a training set containing
    ![100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;100 "100")
    observations and a test set containing
    ![900](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;900 "900")
    observations.

3)  Perform best subset selection on the training set, and plot the
    training set
    ![MSE](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;MSE "MSE")
    associated with the best model of each size.

4)  Plot the test set
    ![MSE](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;MSE "MSE")
    associated with the best model of each size.

5)  For which model size does the test set
    ![MSE](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;MSE "MSE")
    take on its minimum value? Comment on your results. If it takes on
    its minimum value for a model containing only an intercept or a
    model containing all of the features, then play around with the way
    that you are generating the data in (a) until you come up with a
    scenario in which the test set
    ![MSE](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;MSE "MSE")
    is minimized for an intermediate model size.

6)  How does the model at which the test set
    ![MSE](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;MSE "MSE")
    is minimized compared to the true model used to generate the data?
    Comment on the coefficient values.

7)  Create a plot displaying
    ![\sqrt{\sum\_{j=1}^{p}(\beta\_{j}-\hat{\beta\_{j}^{r}})^{2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Csqrt%7B%5Csum_%7Bj%3D1%7D%5E%7Bp%7D%28%5Cbeta_%7Bj%7D-%5Chat%7B%5Cbeta_%7Bj%7D%5E%7Br%7D%7D%29%5E%7B2%7D%7D "\sqrt{\sum_{j=1}^{p}(\beta_{j}-\hat{\beta_{j}^{r}})^{2}}")
    for a range of values of
    ![r](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;r "r"),
    where
    ![\hat{\beta\_{j}^{r}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7Bj%7D%5E%7Br%7D%7D "\hat{\beta_{j}^{r}}")
    is the
    ![j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;j "j")th
    coefficient estimate for the best model containing
    ![r](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;r "r")
    coefficients. Comment on what you observe. How does this compare to
    the test
    ![MSE](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;MSE "MSE")
    plot from (d)?

### Problem 11

We will now try to predict per capita crime rate in the `Boston` data
set.

1)  Try out some of the regression methods explored in this chapter,
    such as best subset selection, the lasso, ridge regression, and
    ![PCR](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;PCR "PCR").
    Present and discuss results for the approaches that you consider.

2)  Propose a model (or set of models) that seem to perform well on this
    data set, and justify your answer. Make sure that you are evaluating
    model performance using validation set error, cross-validation, or
    some other reasonable alternative, as opposed to using training
    error.

3)  Does your chosen model involve all of the features in the data set?
    Why or why not?
