solutioins to the applied exercises in islr2 ch10
================
Wenwen Kong
9/5/2022

### Problem 6

Consider the simple function
![R(\beta) = \sin(\beta) + \beta/10.](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;R%28%5Cbeta%29%20%3D%20%5Csin%28%5Cbeta%29%20%2B%20%5Cbeta%2F10. "R(\beta) = \sin(\beta) + \beta/10.")

1)  Draw a graph of this function over the range
    ![\beta \in \[-6, 6\].](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta%20%5Cin%20%5B-6%2C%206%5D. "\beta \in [-6, 6].")

2)  What is the derivative of this function?

3)  Given
    ![\beta^{0} = 2.3](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta%5E%7B0%7D%20%3D%202.3 "\beta^{0} = 2.3"),
    run gradient descent to find a local minimum of
    ![R(\beta)](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;R%28%5Cbeta%29 "R(\beta)")
    using a learning rate of
    ![\rho = 0.1](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Crho%20%3D%200.1 "\rho = 0.1").
    Show each of
    ![\beta^{0}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta%5E%7B0%7D "\beta^{0}"),
    ![\beta^{1}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta%5E%7B1%7D "\beta^{1}"),
    … in your plot, as well as the final answer.

4)  Repeat with
    ![\beta^{0} = 1.4.](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%5Cbeta%5E%7B0%7D%20%3D%201.4. "\beta^{0} = 1.4.")

### Problem 7

Fit a neural network to the `Default` data. Use a single hidden layer
with 10 units, and dropout regularization. Have a look at Labs
10.9.1-10.9.2 for guidance. Compare the classification performance of
your model with that of linear logistic regression.

### Problem 8

From your collection of personal photographs, pick 10 images of animals
(such as dogs, cats, birds, farm animals, etc.) If the subject does not
occupy a reasonable part of the image, then crop the image. Now use a
pretrained image classification CNN as in Lab 10.9.4 to predict the
class of each of your images, and report the probabilities for the top
five predicted classes for each image.

### Problem 9

Fit a lag-5 autoregressive model to the `NYSE` data, as described in the
text and Lab 10.9.6. Refit the model with a 12-level factor representing
the month. Does this factor improve the performance of the model?

### Problem 10

In Section 10.9.6, we showed how to fit a linear AR model to the `NYSE`
data using the `lm()` function. However, we also mentioned that we can
“flatten” the short sequences produced for the RNN model in order to fit
a linear AR model. Use this latter approach to fit a linear AR model to
the `NYSE` data. Compare the test
![R^{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;R%5E%7B2%7D "R^{2}")
of this linear AR model to that of the linear AR model that we fit in
the lab. What are the advantages/disadvantages of each approach?

### Problem 11

Repeat the previous exercise, but now fit a nonlinear AR model by
“flattening” the short sequences produced for the RNN model.

### Problem 12

Consider the RNN fit to the `NYSE` data in Section 10.9.6. Modify the
code to allow inclusion of the variable `day_of_week`, and fit the RNN.
Compute the test
![R^{2}](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;R%5E%7B2%7D "R^{2}").

### Problem 13

Repeat the analysis of Lab 10.9.5 on the `IMDb` data using a similarly
structured neural network. There we used a dictionary of size 10,000.
Consider the effects of varying the dictionary size. Try the values
1000, 3000, 5000, and 10,000, and compare the results.
