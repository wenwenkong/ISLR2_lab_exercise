solutioins to the applied exercises in islr2 ch12
================
Wenwen Kong
9/5/2022

### Problem 7

In the chapter, we mentioned the use of correlation-based distance and
Euclidean distance as dissimilarity measures for hierarchical
clustering. It turns out that these two measures are almost equivalent:
if each observation has been centered to have mean zero and standard
deviation one, and if we let
![r\_{ij}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;r_%7Bij%7D "r_{ij}")
denote the correlation between the
![i](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;i "i")th
and
![j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;j "j")th
observations, then the quantity
![1 - r\_{ij}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;1%20-%20r_%7Bij%7D "1 - r_{ij}")
is proportional to the squared Euclidean distance between the
![i](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;i "i")th
and
![j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;j "j")th
observations.

On the `USArrests` data, show that this proportionality holds. *Hint:
The Euclidean distance can be calculated using the `dist()` function,
and correlations can be calculated using the `cor()` function.*

### Problem 8

In Section 12.2.3, a formula for calculating PVE was given in Equation
12.10. We also saw that the PVE can be obtained using the `sdev` output
of the `prcomp()` function.

On the `USArrests` data, calculate PVE in two ways:

1)  Using the `sdev` output of the `prcomp()` function, as was done in
    Section 12.2.3.

2)  By applying Equation 12.10 directly. That is, use the `prcomp()`
    function to compute the principal component loadings. Then, use
    those loadings in Equations 12.10 to obtain the PVE.

These two approaches should give the same results. *Hint: You will only
obtain the same results in (a) and (b) if the same data is used in both
cases. For instance, if in (a) you performed `prcomp()` using centered
and scaled variables, then you must center and scale the variables
before applying Equation 12.10 in (b)*

### Problem 9

Consider the `USArrests` data. We will now perform hierarchical
clustering on the states.

1)  Using hierarchical clustering with complete linkage and Euclidean
    distance, cluster the states.

2)  Cut the dendrogram at a height that results in three distinct
    clusters. Which states belong to which clusters?

3)  Hierarchically cluster the states using complete linkage and
    Euclidean distance, *after scaling the variables to have standard
    deviation one.*

4)  What effect does scaling the variables have on the hierarchical
    clustering obtained? In your opinion, should the variables be scaled
    before the inter-observation dissimilarities are computed? Provide a
    justification for your answer.

### Problem 10

In this problem, you will generate simulated data, and then peform PCA
and
![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
clustering on the data.

1)  Generate a simulated data set with 20 observations in each of three
    classes
    (i.e. ![60](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;60 "60")
    observations total), and
    ![50](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;50 "50")
    variables. *Hint: There are a number of functions in `R` that you
    can use to generate data. One example is the `rnorm()` function;
    `runif()` is another option. Be sure to add a mean shift to the
    observations in each class so that there are three distinct
    classes.*

2)  Perform PCA on the 60 observations and plot the first two principal
    component score vectors. Use a different color to indicate the
    observations in each of the three classes. If the three classes
    appear separated in this plot, then continue on to part (c). If not,
    then return to part (a) and modify the simulation so that there is
    greater separation between the three classes. Do not continue to
    part (c) until the three classes show at least some separation in
    the first two principal component score vectors.

3)  Perform
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering of the observations with
    ![K = 3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K%20%3D%203 "K = 3").
    How well do the clusters that you obtained in
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering compare to the true class labels? *Hint: You can use the
    `table()` function in `R` to compare the true class labels to the
    class labels obtained by clustering. Be careful how you interpret
    the results: K-means clustering will arbitrarily number the
    clusters, so you cannot simply check whether the true class labels
    and clustering labels are the same.*

4)  Perform
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering with
    ![K = 2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K%20%3D%202 "K = 2").
    Describe your results.

5)  Now perform
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering with
    ![K = 4](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K%20%3D%204 "K = 4"),
    and describe your results.

6)  Now perform
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering with
    ![K = 3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K%20%3D%203 "K = 3")
    on the first two principal component score vectors, rather than on
    the raw data. That is, perform
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering on the
    ![60 \times 2](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;60%20%5Ctimes%202 "60 \times 2")
    matrix of which the first column is the first principal component
    score vector, and the second column is the second principal
    component score vector. Comment on the results.

7)  Using the `scale()` function, perform
    ![K](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K "K")-means
    clustering with
    ![K = 3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;K%20%3D%203 "K = 3")
    on the data *after scaling each variable to have standard deviation
    noe*. How do these results compare to those obtained in (b)?
    Explain.

### Problem 11

Write an `R` function to perform matrix completion as in Algorithm 12.1,
and as outlined in Section 12.5.2. In each iteration, the function
should keep track of the relative error, as well as the iteration count.
Iterations should continue until the relative error is small enough or
until some maximum number of iterations is reached (set a default value
for this maximum number). Furthermore, there should be an option to
print out the progress in each iteration.

Test your function on the `Boston` data. First, standardize the features
to have mean zero and standard deviation one using the `scale()`
function. Run an experiment where you randomly leave out an increasing
(and nested) number of observations from
![5\\%](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;5%5C%25 "5\%")
to
![30\\%](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;30%5C%25 "30\%"),
in steps of
![5\\%](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;5%5C%25 "5\%").
Apply Algorithm 12.1 with
![M = 1, 2, ..., 8](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;M%20%3D%201%2C%202%2C%20...%2C%208 "M = 1, 2, ..., 8").
Display the approximation error as a function of the fraction of
observations that are missing, and the value of
![M](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;M "M"),
averaged over
![10](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;10 "10")
repetitions of the experiment.

### Problem 12

In Section 12.5.2, Algorithm 12.1 was implemented using the `svd()`
function. However, given the connection between the `svd()` function and
the `prcomp()` function highlighted in the lab, we could have instead
implemented the algorithm using `prcomp()`.

Write a function to implement Algorithm 12.1 that makes use of
`prcomp()` rather than `svd()`.

### Problem 13

On the book website, [www.statlearning.com](www.statlearning.com), there
is a gene expression data set (`Ch12Ex13.csv`) that consists of
![40](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;40 "40")
tissue samples with measurements on 1,000 genes. The first 20 samples
are from healthy patients, while the second 20 are from a diseased
group.

1)  Load in the data using `read.csv()`. You will need to select
    `header = F`.

2)  Apply hierarchical clustering to the samples using correlation-based
    distance, and plot the dendrogram. Do the genes separate the samples
    into the two groups? Do your results depend on the type of linkage
    used?

3)  Your collaborator wants to know which genes differ the most across
    the two groups. Suggest a way to answer this question, and apply it
    here.
