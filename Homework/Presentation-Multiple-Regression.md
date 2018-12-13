Multiple Linear Regression
========================================================
author: 
date: 12/5/2018
autosize: true

Multiple Linear Regression
========================================================

MLR is used when we want to build a model with more than one variable  

_This is singular LR and models a line._
$$
y_i = \beta_0 +  \beta_i x_i + \epsilon_i i = 1,...,n
$$

_This is a MLR model that descrbies a parabola_
$$
y_i = \beta_0 +  \beta_i x_1 + \beta_2 x_2 + \epsilon_i i = 1,...,n
$$

Chapter 8 Problem 3
========================================================

_This is a single row of data_

```
  bwt ges par age ht  wt sk
1 120 285   0  27 62 100  0
```
_This is the model resulting from said data_

```
             est std er     t      p
intercept -80.41  14.35 -5.60 0.0000
gestation   0.44   0.03 15.26 0.0000
parity     -3.33   1.13 -2.95 0.0033
age        -0.01   0.09 -0.10 0.9170
height      1.15   0.21  5.63 0.0000
weight      0.05   0.03  1.99 0.0471
smoke      -8.40   0.95 -8.81 0.0000
```

The model (part a).
========================================================

_Our model is built from the coefficient column of that data_


$$
y_i = -8041 +  .44 x_1   -3.33x_2 - .01x_3 + 1.15 x_4 + .05 x_5 -8.40 x_6+ \epsilon_i
$$

Slopes (part b)
========================================================

 This slope represents the average increase in $y$ over $x$  
 
**Gestation**: the average birthweight increases by .44 ounces per day of pregnacy  

**AGE**: The average birth weight decreease by about 3.33 ounces per year of the mother's age

What about parity? (part c)
========================================================
The coefficient for parity in the previous exercise was -1.93. 

These coefficients are different because **our** model includes more variables.

Does it check out? (part d)
========================================================

To calculate the residual, we can use R right here in the presentation! 
_This is the value predicted by our model_

```
[1] 120.58
```
_To find the residual, we subtract the predicted y value from the actual y value._

```
[1] -0.58
```
Hey! That's pretty good. 

Variance of Residuals (part 3)
========================================================

To calculate the residual, we can use R right here in the presentation!  
_This is the value predicted by our model_

```r
var.e = 249.28
var.y = 332.57
pop = 1236
k = 6
r.square = 1-(var.e/var.y)
r.square.adjusted = 1 -(var.e/var.y) * (pop-1/pop-k-1)
r.square
```

```
[1] 0.2504435
```

```r
r.square.adjusted
```

```
[1] -920.2043
```

