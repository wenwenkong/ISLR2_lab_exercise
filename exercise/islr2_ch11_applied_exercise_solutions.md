solutioins to the applied exercises in islr2 ch11
================
Wenwen Kong
9/5/2022

### Problem 10

This exercise focuses on the brain tumor data, which is included in the
`ISLR2 R` library.

1)  Plot the Kaplan-Meier survival curve with
    ![\pm 1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cpm%201 "\pm 1")
    standard error bands, using the `survfit()` function in the
    `survival` package.

2)  Draw a bootstrap sample of size
    ![n = 88](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%2088 "n = 88")
    from the pairs
    ![(y\_{i}, \delta\_{i})](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%28y_%7Bi%7D%2C%20%5Cdelta_%7Bi%7D%29 "(y_{i}, \delta_{i})"),
    and compute the resulting Kaplan-Meier survival curve. Repeat this
    process
    ![B = 200](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;B%20%3D%20200 "B = 200")
    times. Use the results to obtain an estimate of the standard error
    of the Kaplan-Meier survival curve at each timepoint. Compare this
    to the standard error obtained in (a).

3)  Fit a Cox proportional hazards model that uses all of the predictors
    to predict survival. Summarize the main findings.

4)  Stratify the data by the value of `ki`. (Since only one observation
    has `ki = 40`, you can group that observation together with the
    observations that have `ki = 60`.) Plot Kaplan-Meier survival curves
    for each of the five strata, adjusted for the other predictors.

### Problem 11

This example makes use of the data in Table 11.4

1)  Create two groups of observations. In Group 1,
    ![X \lt 2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%20%5Clt%202 "X \lt 2"),
    whereas in Group 2,
    ![X \ge 2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X%20%5Cge%202 "X \ge 2").
    Plot the Kaplan-Meier survival curves corresponding to the two
    groups. Be sure to label the curves so that it is clear which curve
    corresponds to which group. By eye, does there appear to be a
    difference between the two groups’ survival curves?

2)  Fit Cox’s proportional hazards model, using the group indicator as a
    covariate. What is the estimated coefficient? Write a sentence
    providing the interpretation of this coefficient, in terms of the
    hazard or the instantaneous probability of the event. Is there
    evidence that the true coefficient value is non-zero?

3)  Recall from Section 11.5.2 that in the case of a single binary
    covariate, the log-rank test statistic shoiuld be identical to the
    score statistic for the Cox model. Conduct a log-rank test to
    determine whether there is a difference between the survival curves
    for the two groups. How does the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-value
    for the log-rank test statistic compare to the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-value
    for the score statistic for the Cox model from (b)?
