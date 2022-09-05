solutioins to the applied exercises in islr2 ch13
================
Wenwen Kong
9/5/2022

### Problem 7

This problem makes use of the `Carseats` dataset in the `ISLR2` package.

1)  For each quantitative variable in the dataset besides `Sales`, fit a
    linear model to predict `Sales` using that quantitative variable.
    Report the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-values
    associated with the coefficients for the variables. That is, for
    each model of the form
    ![Y = \beta\_{0} + \beta\_{1}X + \epsilon](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y%20%3D%20%5Cbeta_%7B0%7D%20%2B%20%5Cbeta_%7B1%7DX%20%2B%20%5Cepsilon "Y = \beta_{0} + \beta_{1}X + \epsilon"),
    report the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-value
    associated with the coefficient
    ![\beta\_{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta_%7B1%7D "\beta_{1}").
    Here,
    ![Y](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;Y "Y")
    represents `Sales` and
    ![X](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X "X")
    represents one of the other quantitative variables.

2)  Suppose we control the Type
    ![I](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;I "I")
    error at level
    ![\alpha = 0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Calpha%20%3D%200.05 "\alpha = 0.05")
    for the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-values
    obtained in (a). Which null hypotheses do we reject?

3)  Now suppose we control the FWER at level
    ![0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0.05 "0.05")
    for the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-values.
    Which null hypotheses do we reject?

4)  Finally, suppose we control the FDR at level
    ![0.2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0.2 "0.2")
    for the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-values.
    Which null hypotheses do we reject?

### Problem 8

In this problem, we will simulate data from
![m = 100](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;m%20%3D%20100 "m = 100")
fund managers.

> set.seed(1) n \<- 20 m \<- 100 x \<- matrix(rnorm(n \* m), ncol = m)

These data represent each fund manager’s percentage returns for each of
![n = 20](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;n%20%3D%2020 "n = 20")
months. We wish to test the null hypothesis that each fund manager’s
percentage returns have population mean equal to zero. Notice that we
simulated the data in such a way that each fund manager’s percentage
returns do have population mean zero; in other words, all
![m](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;m "m")
null hypotheses are true.

1)  Conduct a one-sample
    ![t](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;t "t")-test
    for each fund manager, and plot a histogram of the
    ![p](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p "p")-values
    obtained.

2)  If we control Type
    ![I](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;I "I")
    error for each null hypothesis at level
    ![\alpha = 0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Calpha%20%3D%200.05 "\alpha = 0.05"),
    then how many null hypotheses do we reject?

3)  If we control the FWER at level
    ![0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0.05 "0.05"),
    then how many null hypotheses do we reject?

4)  If we control the FDR at level
    ![0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0.05 "0.05"),
    then how many null hypotheses do we reject?

5)  Nowe suppose we “cherry-pick” the 10 fund managers who perform the
    best in our data. If we control the FWER for just these 10 fund
    managers at level
    ![0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0.05 "0.05"),
    then how many null hypotheses do we reject? If we control the FDR
    for just these 10 fund managers at level
    ![0.05](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;0.05 "0.05"),
    then how many null hypotheses do we reject?

6)  Explain why the analysis in (e) is misleading. *Hint: The standard
    approaches for controlling the FWER and FDR assume that all tested
    null hypotheses are adjusted for multiplicity, and that no
    “cherry-picking” of the smallest p-values has occurred. What goes
    wrong if we cherry-pick?*
