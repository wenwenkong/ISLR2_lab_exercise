Solutioins to the applied exercises in ISLR2 ch3
================
Wenwen Kong
8/6/2022

### Problem 8

This question involves the use of simple linear regression on the `Auto`
data set.

1)  Use the `lm()` function to perform a simple linear regression with
    `mpg` as the response and `horsepower` as the predictor. Use the
    `summary()` function to print the results. Comment on the output.
    For example:

<!-- end list -->

    i. Is there a relationship between the predictor and the response?
    
    ii. How strong is the relationship between the predictor and the response?
    
    iii. Is the relationship between the predictor and the respnose positive or negtative?
    
    iv. What is the predicted `mpg` associated with a `horsepower` of 98? What are the associated 95% confidence and prediction invervals? 

2)  Plot the response and the predictor. Use the `abline()` function to
    display the least squares regression line.

3)  Use the `plot()` function to produce diagnostic plots of the least
    squares regression fit. Comment on any problems you see with the
    fit.

### Problem 9

This question involves the use of multiple linear regression on the
`Auto` data set.

1)  Produce a scatterplot matrix which includes all of the variables in
    the data set.

2)  Compute the matrix of correlations between the variables using the
    function `cor()`. You will need to exclude the `name` variable,
    which is qualitative.

3)  Use the `lm()` function to perform a multiple linear regression with
    `mpg` as the response and all other variables except `name` as the
    predictors. Use the `summary()` function to print the results.
    Comment on the output. For instance:

<!-- end list -->

    i. Is there a relationship between the predictors and the response?
    
    ii. Which predictors appear to have a statistically significant relationship to the response?
    
    iii. What does the coefficient for the `year` variable suggest?

4)  Use the `plot()` function to produce diagnostic plots of the linear
    regression fit. Comment on any problems you see with the fit. Do the
    residual plots suggest any unusually large outliers? Does the
    leverage plot identify any observations with unusually high
    leverage?

5)  Use the `*` and `:` symbols to fit linear regression models with
    interaction effects. Do any interactions appear to be statistically
    significant?

6)  Try a few different transformations of the variables, such as
    ![log(X)](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;log%28X%29
    "log(X)"),
    ![sqrt{X}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;sqrt%7BX%7D
    "sqrt{X}"),
    ![X^2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%5E2
    "X^2"). Comment on your findings.

### Problem 10

This question should be answered using the `Carseats` data set.

1)  Fit a multiple regression model to predict `Sales` using `Price`,
    `Urban`, and `US`.

2)  Provide an interpretation of each coefficient in the model. Be
    careful - some of the variables in the model are qualitative\!

3)  Write out the model in equation form, being careful to handle the
    qualitative variables properly.

4)  For which of the predictors can you reject the null hypothesis
    ![H\_{0}: \\beta\_{j}
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta_%7Bj%7D%20%3D%200
    "H_{0}: \\beta_{j} = 0")?

5)  On the basis of your response to the previous question, fit a
    smaller model that only uses the predictors for which there is
    evidence of association with the outcome.

6)  How well do the models in (a) and (e) fit the data?

7)  Using the model from (e), obtain 95% confifdence intervals for the
    coefficient(s).

8)  Is there evidence of outliers or high leverage observations in the
    model from (e)?

### Problem 11

In this problem we will investigate the *t-statistic* for the null
hypothesis ![H\_{0}: \\beta
= 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta%20%3D%200
"H_{0}: \\beta = 0") in simple linear regression without an intercept.
To begin, we generate a predictor `x` and a response `y` as follows.

> set.seed(1) x \<- rnorm(100) y\<- 2 \* x + rnorm(100)

1)  Perform a simple linear regression of `y` onto `x`, *without* an
    intercept. Report the coefficient estimate
    ![\\hat{\\beta}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta%7D
    "\\hat{\\beta}"), the standard error of this coefficient estimate,
    and the *t-statistic* and *p-value* associated with the null
    hypothesis ![H\_{0}: \\beta
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta%20%3D%200
    "H_{0}: \\beta = 0"). Comment on these results. (You can perform
    regression without an intercept using the command `lm(y~x+0)`.)

2)  Now perform a simple linear regression of `x` onto `y` without an
    intercept, and report the coefficient estimate, its standard error,
    and the corresponding *t-statistic* and *p-value* associated with
    the null hypothesis ![H\_{0}: \\beta
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta%20%3D%200
    "H_{0}: \\beta = 0"). Comment on these results.

3)  What is the relationship between the results obtained in (a) and
    (b)?

4)  For the regression of
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") onto
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X") without an intercept, the *t-statistic* for ![H\_{0}: \\beta
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta%20%3D%200
    "H_{0}: \\beta = 0") takes the form
    ![\\hat{\\beta}/SE(\\hat{\\beta})](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta%7D%2FSE%28%5Chat%7B%5Cbeta%7D%29
    "\\hat{\\beta}/SE(\\hat{\\beta})"), where
    ![\\hat{\\beta}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta%7D
    "\\hat{\\beta}") is given by (3.38), and where

![SE(\\hat{\\beta}) = \\sqrt{\\frac{\\sum\_{i=1}^{n}(y\_{i} -
x\_{i}\\hat{\\beta})^2}{(n-1)\\sum\_{i'=1}^{n}x\_{i'}^2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;SE%28%5Chat%7B%5Cbeta%7D%29%20%3D%20%5Csqrt%7B%5Cfrac%7B%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%28y_%7Bi%7D%20-%20x_%7Bi%7D%5Chat%7B%5Cbeta%7D%29%5E2%7D%7B%28n-1%29%5Csum_%7Bi%27%3D1%7D%5E%7Bn%7Dx_%7Bi%27%7D%5E2%7D%7D
"SE(\\hat{\\beta}) = \\sqrt{\\frac{\\sum_{i=1}^{n}(y_{i} - x_{i}\\hat{\\beta})^2}{(n-1)\\sum_{i'=1}^{n}x_{i'}^2}}")

(These formulas are slightly different from those given in Sections
3.1.1 and 3.1.2, since here we are performing regression without an
intercept.) Show algebraically, and confirm numerically in `R`, that the
*t-statistic* can be written
as

![\\frac{(\\sqrt{n-1})\\sum\_{i=1}^{n}x\_{i}y\_{i}}{\\sqrt{(\\sum\_{i=1}^{n}x\_{i}^2)(\\sum\_{i'=1}^{n}y\_{i'}^2)-(\\sum\_{i'=1}^{n}x\_{i'}y\_{i'})^2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cfrac%7B%28%5Csqrt%7Bn-1%7D%29%5Csum_%7Bi%3D1%7D%5E%7Bn%7Dx_%7Bi%7Dy_%7Bi%7D%7D%7B%5Csqrt%7B%28%5Csum_%7Bi%3D1%7D%5E%7Bn%7Dx_%7Bi%7D%5E2%29%28%5Csum_%7Bi%27%3D1%7D%5E%7Bn%7Dy_%7Bi%27%7D%5E2%29-%28%5Csum_%7Bi%27%3D1%7D%5E%7Bn%7Dx_%7Bi%27%7Dy_%7Bi%27%7D%29%5E2%7D%7D
"\\frac{(\\sqrt{n-1})\\sum_{i=1}^{n}x_{i}y_{i}}{\\sqrt{(\\sum_{i=1}^{n}x_{i}^2)(\\sum_{i'=1}^{n}y_{i'}^2)-(\\sum_{i'=1}^{n}x_{i'}y_{i'})^2}}")

5)  Using the results from (d), argue that the *t-statistic* for the
    regression of `y` onto `x` is the same as the *t-statistic* for the
    regression of `x` onto `y`.

6)  In `R`, show that when regression is performed *with* an intercept,
    the *t-statistic* for ![H\_{0}: \\beta\_{1}
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta_%7B1%7D%20%3D%200
    "H_{0}: \\beta_{1} = 0") is the same for the regression of `y` onto
    `x` as it is for the regression of `x` onto `y`.

### Problem 12

This problem involves simple linear regression without an intercept.

1)  Recall that the coefficient estimate
    ![\\hat{\\beta}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta%7D
    "\\hat{\\beta}") for the linear regression of
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") onto
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X") without an intercept is given by (3.38). Under what
    circumstance is the coefficient estimate for the regression of
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X") onto
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") the same as the coefficient estimate for the regression of
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") onto
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X")?

2)  Generate an example in `R` with ![n
    = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%20100
    "n = 100") observations in which the coefficient estimate for the
    regression of
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X") onto
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") is *different from* the coefficient estimate for the regression
    of
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") onto
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X").

3)  Generate an example in `R` with ![n
    = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%20100
    "n = 100") observations in which the coefficient estimate for the
    regression of
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X") onto
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") is *the same as* the coefficient estimate for the regression of
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y
    "Y") onto
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X"). \#\#\# Problem 13 In this exercise you will create some
    simulated data and will fit simple linear regression models to it.
    Make sure to use `set.seed(1)` prior to starting part (a) to ensure
    consistent results.

4)  Using the `rnorm()` function, create a vector, `x`, containing 100
    observations drawn from a
    ![N(0,1)](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;N%280%2C1%29
    "N(0,1)") distribution. This represents a feature,
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X").

5)  Using the `rnorm()` function, create a vector, `eps`, containing 100
    observations drawn from a
    ![N(0,0.25)](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;N%280%2C0.25%29
    "N(0,0.25)") distribution - a normal distribution with mean zero and
    variance 0.25.

6)  Using `x` and `eps`, generate a vector `y` according to the model
    ![Y = -1 + 0.5X + \\epsilon.
    (3.39)](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20%3D%20-1%20%2B%200.5X%20%2B%20%5Cepsilon.%20%283.39%29
    "Y = -1 + 0.5X + \\epsilon. (3.39)") What is the length of the
    vector `y`? What are the values of
    ![\\beta\_{0}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B0%7D
    "\\beta_{0}") and
    ![\\beta\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B1%7D
    "\\beta_{1}") in this linear model?

7)  Create a scatterplot displaying the relationship between `x` and
    `y`. Comment on what you observe.

8)  Fit a least squares linear model to predict `y` using `x`. Comment
    on the model obtained. How do
    ![\\hat{\\beta\_{0}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B0%7D%7D
    "\\hat{\\beta_{0}}") and
    ![\\hat{\\beta\_{1}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B1%7D%7D
    "\\hat{\\beta_{1}}") compare to
    ![\\beta\_{0}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B0%7D
    "\\beta_{0}") and
    ![\\beta\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B1%7D
    "\\beta_{1}")?

9)  Display the least squares line on the scatterplot obetained in (d).
    Draw the population regression line on the plot, in a different
    color. Use the `legend()` command to create an appropriate legend.

10) Now fit a polynomial regression model that predicts
    ![y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;y
    "y") using
    ![x](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;x
    "x") and
    ![x^2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;x%5E2
    "x^2"). Is there evidence that the quadratic term improves the model
    fit? Explain your answer.

11) Repeat (a)-(f) after modifying the data generation process in such a
    way that there is *less* noise in the data. The model (3.39) should
    remain the same. You can do this by decreasing the variance of the
    normal distribution used to generate the error term
    ![\\epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cepsilon
    "\\epsilon") in (b). Describe your results.

12) Repeat (a)-(f) after modifying the data generation process in such a
    way that there is *more* noise in the data. The model (3.39) should
    remain the same. You can do this by decreasing the variance of the
    normal distribution used to generate the error term
    ![\\epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cepsilon
    "\\epsilon") in (b). Describe your results.

13) What are the confidence intervals for
    ![\\beta\_{0}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B0%7D
    "\\beta_{0}") and
    ![\\beta\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B1%7D
    "\\beta_{1}") based on the original data set, the noisier data set,
    and the less noisy data set? Comment on your results.

### Problem 14

This problem focuses on the *collinearity* problem.

1)  Perform the following commands in `R`: \> set.seed(1) \> x1 \<-
    runif(100) \> x2 \<- 0.5 \* x1 + rnorm(100) / 10 \> y \<- 2 + 2 \*
    x1 + 0.3 \* x2 + rnorm(100)

The last line corresponds to creating a linear model in which `y` is a
function of `x1` and `x2`. Write out the form of the linear model. What
are the regression coefficients?

2)  What is the correlation between `x1` and `x2`? Create a scatterplot
    displaying the relationship between the variables.

3)  Using this data, fit a least squares regression to predict `y` using
    `x1` and `x2`. Describe the results obtained. What are
    ![\\hat{\\beta\_{0}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B0%7D%7D
    "\\hat{\\beta_{0}}"),
    ![\\hat{\\beta\_{1}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B1%7D%7D
    "\\hat{\\beta_{1}}"), and
    ![\\hat{\\beta\_{2}}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Chat%7B%5Cbeta_%7B2%7D%7D
    "\\hat{\\beta_{2}}")? How do these relate to the true
    ![\\beta\_{0}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B0%7D
    "\\beta_{0}"),
    ![\\beta\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B1%7D
    "\\beta_{1}"), and
    ![\\beta\_{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B2%7D
    "\\beta_{2}")? Can you reject the null hypothesis ![H\_{0}:
    \\beta\_{1}
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta_%7B1%7D%20%3D%200
    "H_{0}: \\beta_{1} = 0")? How about the null hypothesis ![H\_{0}:
    \\beta\_{2}
    = 0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta_%7B2%7D%20%3D%200
    "H_{0}: \\beta_{2} = 0")?

4)  Now fit a least squares regression to predict `y` using only `x1`.
    Comment on your results. Can you reject the null hypothesis
    ![H\_{0}:
    \\beta\_{1}=0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta_%7B1%7D%3D0
    "H_{0}: \\beta_{1}=0")?

5)  Now fit a least squares regression to predict `y` using only `x2`.
    Comment on your results. Can you reject the null hypothesis
    ![H\_{0}:
    \\beta\_{1}=0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%20%5Cbeta_%7B1%7D%3D0
    "H_{0}: \\beta_{1}=0")?

6)  Do the results obtained in (c)-(e) contradict each other? Explain
    your answer.

7)  Now suppose we obtain one additional observation, which was
    unfortunately mismeasured. \> x1 \<- c(x1, 0.1) \> x2 \<- c(x2, 0.8)
    \> y \<- c(y, 6)

Re-fit the linear models from (c) to (e) using this new data. What
effect does this new observation have on each of the models? In each
model, is this observation an outlier? A high-leverage point? Both?
Explain your answers.

### Problem 15

This problem involes the `Boston` data set, which we saw in the lab for
this chapter. We will now try to predict per capita crime rate using the
other variables in this data set. In other words, per capita crime rate
is the response, and the other variables are the predictors.

1)  For each predictor, fit a simple linear regression model to predict
    the response. Describe your results. In which of the models is there
    a statistically significant association between the predictor and
    the response? Create some plots to back up your assertions.

2)  Fit a multiple regression model to predict the response using all of
    the predictors. Describe your results. For which predictors can we
    reject the null hypothesis
    ![H\_{0}:\\beta\_{j}=0](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;H_%7B0%7D%3A%5Cbeta_%7Bj%7D%3D0
    "H_{0}:\\beta_{j}=0")?

3)  How do your results from (a) compare to your results from (b)?
    Create a plot displaying the univariate regression coefficients from
    (a) on the x-axis, and the multiple regression coefficients from (b)
    on the y-axis. That is, each predictor is displayed as a single
    point in the plot. Its coefficient in a simple linear regression
    model is shown on the x-axis, and its coefficient estimate in the
    multiple linear regression model is shown on the y-axis.

4)  Is there evidence of non-linear association between any of the
    predictors and the response? To answer this question, for each
    predictor
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X
    "X"), fit a model of the form ![Y =
    \\beta\_{0}+\\beta\_{1}X+\\beta\_{2}X^2+\\beta\_{3}X^3+\\epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20%3D%20%5Cbeta_%7B0%7D%2B%5Cbeta_%7B1%7DX%2B%5Cbeta_%7B2%7DX%5E2%2B%5Cbeta_%7B3%7DX%5E3%2B%5Cepsilon
    "Y = \\beta_{0}+\\beta_{1}X+\\beta_{2}X^2+\\beta_{3}X^3+\\epsilon")
