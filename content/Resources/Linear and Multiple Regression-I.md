---
publish: true
title: "Lecture 22: Linear and Multiple Regression-I"
description: In this lecture, we have discussed about linear and multiple regression, fitting evaluation, goodness of fitting, polynomial regression, Ridge regression and Lasso regression.
created: 2025-04-04
modified: 2026-10-15T16:16:14.556Z
published: 2021-08-16
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=ldVOzC2v7wI&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=24
author: IIT Roorkee
lecture: 22
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Regression

It refers to the problem of learning the relationships between some input variables $X = [x_{1},x_{2},\dots ,x_{n}]^{T}$
and a quantitative output variable y. Means, regression is about learning a model f such that $y = f(x)+\epsilon$

# Linear/ Multiple Linear Regression

The Linear regression model describes the output variable y (a scaler) as an affine combination of the input variables x1;x2;...;xp plus a noise term epsilon, i.e. where, ai are the parameters or wights of the regression model which we need to estimate based on the given data
$y = f(x_{1},x_{2},\dots x_{n})+\epsilon$

| Emp | Age           | Exp           | Edu           | Sal       |
| --- | ------------- | ------------- | ------------- | --------- |
| E1  | $x_{1}^{1}$ | $x_{2}^{1}$ | $x_{3}^{1}$ | $y_{1}$ |
| E2  | $x_{1}^{2}$ | $x_{2}^{2}$ | $x_{3}^{2}$ | $y_{2}$ |
| En  | $x_{1}^{n}$ | $x_{2}^{n}$ | $x_{3}^{n}$ | $y_{n}$ |
**System of Linear Equations**
$y_{i}=\alpha_{0}+\alpha_{1}x_{1}^{i}+\alpha_{2}x_{2}^{i}+\alpha_{3}x_{3}^{i}, \space 1\leq i\leq n$
**Matrix Determination of SOLE**

$$$A = \begin{bmatrix}
1 & x_{1}^{1} & x_{2}^{1} & x_{3}^{1} \\
1 & x_{1}^{2} & x_{2}^{2} & x_{3}^{2} \\
. & . & . & . \\
1 & x_{1}^{n} & x_{2}^{n} & x_{3}^{n}
\end{bmatrix},X=\begin{bmatrix}
\alpha_{0} \\
\alpha_{1} \\
\alpha_{2} \\
\alpha_{3}
\end{bmatrix},b=\begin{bmatrix}
y_{1} \\
y_{2} \\
. \\
y_{n}
\end{bmatrix}$$
This is a overdetermined system, using *Lease square approximation* we have
$$X = A^{+}b=(A^{T}A)^{-1}A^{T}b$$
now the model is given as,
$$y = \alpha_{0}+\alpha_{1}x_{1}+\alpha_{2}x_{2}+\alpha_{3}x_{3}$$

**Calculus Approach**
$$E = \sum_{i=1}^{n} (y_{i}-(\alpha_{0}+\alpha_{1}x_{1}^{i}+\alpha_{2}x_{2}^{i}+\alpha_{3}x_{3}^{i}))^{2}$$
finding parameters such that error is minium, hence $$\frac{\delta E}{\alpha_{0}}=0, \frac{\delta E}{\alpha_{1}}=0, \frac{\delta E}{\alpha_{2}}=0 \frac{\delta E}{\alpha_{3}}=0$$
We will get four equations and four unknowns which can be solved using simple matrix operations
## Fitting Evaluation: MSE and RMSE
| Emp | Age           | Exp           | Edu           | Sal       | Predicted Sal | Residual            |
| --- | ------------- | ------------- | ------------- | --------- | ------------- | ------------------- |
| E1  | $$x_{1}^{1}$$ | $$x_{2}^{1}$$ | $$x_{3}^{1}$$ | $$y_{1}$$ | $$y_{1}^{*}$$ | $$y_{1}^{*}-y_{1}$$ |
| E2  | $$x_{1}^{2}$$ | $$x_{2}^{2}$$ | $$x_{3}^{2}$$ | $$y_{2}$$ | $$y_{2}^{*}$$ | $$y_{2}^{*}-y_{2}$$ |
| En  | $$x_{1}^{n}$$ | $$x_{2}^{n}$$ | $$x_{3}^{n}$$ | $$y_{n}$$ | $$y_{n}^{*}$$ | $$y_{n}^{*}-y_{n}$$ |
$$RSS = \sum_{i=1}^{n} (y_{i}^{*}-y_{i})^{2}$$
$$MSE = \frac{1}{n}RSS$$
$$RMSE = \frac{1}{n}\sqrt{ RSS }$$
#### Goodness of fitting
Consider the linear regression models as $$Y = \alpha+\beta X, Y=\alpha$$
then we define R2 as,
$$R^{2} = 1-\frac{\text{sum of square residuals from model with } \alpha \text{ and } \beta}{\text{sum of square residuals from model with } \alpha \text{ only}}$$
- We have 0 <= R2 <= 1
- R2 = 0 model is not useful
- R2 = 1 model fits all points perfectly

**How large R2 need to be to be considered as good?**
This depends on the context, there is no absolute ans here. for hard to predict Y variables, smaller values may be good
# Polynomial Regression
$$Y=\alpha_{0}+\alpha_{1}x+\alpha_{2}x^{2}+\dots\alpha_{n}x^{n}$$
As we go in higher degree, chances of overfitting increases implies R2 = 1, one of the way to prevent overfitting is using *Regularization*
# Regularization
- Regularization is our first weapon to combat overfitting
- It constrains the machine learning algorithm to improve out of sample error especially when noise is present
## Ridge regression
In MLR,
$$E = \sum_{i=1}^{n}\left( y_{i}-\alpha_{0}-\sum_{j=1}^{p}\alpha_{j}x_{ij} \right)^{2}$$
Ridge regression is similar to MLR, except that the coefficients (alphas) are estimated by minimizing a slightly different quantity, means the coefficient will not increase too much, means there will be no higher weightage to a feature in my model
$$E = RSS + \lambda \sum_{j=1}^{p}\alpha_{j}^{2}$$
where lambda >= 0, is a *tuning parameter*, to be determined separately.
- The effect of this equation is to add a shrinkage penalty
- such constraint improve fit, because shrinking coefficients can significantly reduce their variance
## Lasso regression
- one significant problem of Ridge regression is that the penalty term will never force any of the coefficient to be exactly 0
- Thus, the final model will include all p predictors, which creates a challenge in model interpretation
- A more modern MLA is lasso
- It works as same as RR but the penalty term can shrink a coefficient to zero
$$E = RSS + \lambda \sum_{j=1}^{p}|\alpha_{j}|$$
Thus, the lasso performs *variable/ feature selection*

---
# Previous Lectures
```dataview
list
From
```

---
# References
![](https://www.youtube.com/watch?v=ldVOzC2v7wI)
$$$
