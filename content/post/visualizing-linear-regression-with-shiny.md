---
categories:
- rstats
- teaching
comments: true
date: 2018-09-28T15:55:00
tags:
- rstats
- shiny
- teaching 
- econometrics
title: Visualizing Linear Regression with Shiny
---

For my [econometrics course](http://ryansafner.com/courses/econ480) this semester, I have been using `R` to help students visualize linear regression models. Running a regression in `R` is quite simple, as is intepretting the results, with a little bit of training. However, I emphasize that I want students to *understand* what is happening "inside the black box" of regression. I discourage blindly trusting  `R`'s opaquely simple input and output, and get students to learn what `R` is doing *under the hood*, even if they will never have to manually estimate the model themselves. 

### Brief Econometrics Review Incoming: 

Ordinary Least Squares (OLS) regression simply chooses the intercept ($\hat{\beta_0}$) and slope ($\hat{\beta_1}$) parameters for the equation of a line that best fits the data:
$$\hat{Y_i}=\hat{\beta_0}+\hat{\beta_1}X_i$$ 

by trying to minimize the **Sum of Squared Errors (SSE)**. The error $\epsilon$ (or residual) of an observation is defined as the difference between the *actual* value of $Y$ observed in the data associated with a given value of $X$, and the *predicted* value, $\hat{Y}$ given $X$: 

$$\hat{\epsilon}=Y_i-\hat{Y_i}$$

So what OLS does is minimize the sum of the squared errors:

$$\min \sum^n_{i=1} \hat{\epsilon_i}^2$$

This is a calculus problem that is solvable, if tedious. But at least it should be intuitive to understand what OLS does. 

### Visualizing with Shiny 

Beyond grinding students down with pure theory, I wrote an [interactive Shiny App](https://ryansafner.shinyapps.io/ols_estimation_by_min_sse/) with `R` that demonstrates this process to choosing the optimal slope and intercept. 

With this example, I have a randomly-generated set of data (within specific parameters, to keep the graph scaled properly). I then allow users to choose a slope and intercept with sliders, to move the line accordingly. The graph also displays all of the errors as dashed red lines. Moving the slope or the intercept too much causes the generated line to create much larger errors. The graph also calculates the **SSE** (which again, OLS minimizes), in addition to the standard error of the regression (**SER**), which calculates the average size of the error. 

I would have loved to be able to graph the square of the errors, and display them, to show that OLS minimizes the area of those squares, if drawn. However, I was unable to figure out how to draw a square from each data point and the regression line (for squared error)| instead of a mere dashed line (for error). 

I love Shiny and have only begun to fully understand how it works and the benefits of its application. I have already coded several other models for intuitive visualization that I may post about later, namely a [Calculus of Consent model of the optimal voting rule](https://ryansafner.shinyapps.io/ccmodel/) in [public choice](https://ryansafner.com/courses/ECON410), and ambitiously, the [consumer's constrained optimization problem](https://ryansafner.shinyapps.io/consumer/) in [intermediate microeconomics](https://ryansafner.com/courses/ECON306). Using sliders in shiny allow me to demonstrate the marginal effects of each parameter change on a model's predicted outcome far better than just me proving several theoretical examples by way of equations. Students can instead see the change in real time. 
