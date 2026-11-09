---
publish: true
title: "Lecture 53: Joint probability distribution and covariance"
description: "In this lecture, we discuss joint probability distributions: discrete and continuous, their expectations, variance and also covariance between two random variables."
created: 2025-04-18
modified: 2026-10-15T16:16:14.556Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
  - maths
  - probability
  - statistics
source: https://www.youtube.com/watch?v=slyRsDIX7tA
author: IIT Roorkee
lecture: 53
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Random Vector

Let $X_{1},X_{2},\dots,X_{n}$ be n random variables. Then, $X=\begin{bmatrix}X_{1}&X_{2}&\dots&X_{3}\end{bmatrix}^{T}$ is calle a random vector

# Joint Prob Distributions

Consider a random vector X as $X=\begin{bmatrix}X_{1}&X_{2}&\dots&X_{3}\end{bmatrix}^{T}$. the distribution of X is called JD of random variables $X_{1},X_{2},\dots,X_{n}$ defined as:
$f_{X}(x_{1},x_{2},\dots ,x_{n})=P[X_{1}=x_{1}, X_{2}=x_{2},\dots,X_{n}=x_{n}]$
for discrete random variables, $f_{X}$ gives the **joint pmf** while for continuous random variables, $f_{X}$ gives the **joint pdf**

# Marginal distributions

Consider a random bi variate vector $W=(X,Y)$ and let $f(x,y)$ be tjje joint prob distribution of W. The distribution of X is called marginal distribution of the random variable X defiend as

$$$f_{X}(x)=\begin{cases}
\sum_{Y}f(x,y), \text{ W is discrete} \\
\int_{y}f(x,y)dy, \text{ W is continuous}
\end{cases}$$
similarly, marginal distribution of Y can be obtained
# Covariance

^c7b33e

Covariance is a measure of linear relationship between two RVs defined as
$$Cov(X,Y)=E[(X-E[X])(Y-E[Y])]=E[XY]-E[X][Y]$$
some properties of covariance are
- $V[X]=Cov(X,X)$
- it is bilinear in nature, i.e.
	- $cov(aX+bY,Z)=acov(X,Z)+bcov(Y,Z)$
	- $cov(X,aY+bZ)=acov(X,Y)+bcov(X,Z)$
# Correlation coefficient
it is defined as:
$$\rho(X,Y)=\frac{Cov(X,Y)}{\sqrt{ V[X]V[Y] }}$$
Two random variables are said to be Uncorrelated if Cov(X,Y) = 0 or p(X,Y) = 0

> [!abstract]
> if two random variables are independent, then they are uncorrelated but the converse is not ture

# Expectation and Covariance for Non-Bivariate Random Vector
Expectation of a random vector $X=\begin{bmatrix}X_{1}&X_{2}&\dots&X_{3}\end{bmatrix}^{T}$ is given as
$$E[X]=\begin{bmatrix}
E[X_{1}] \\
E[X_{2}] \\
. \\
. \\
. \\
E[X_{n}]
\end{bmatrix}$$
The Covariace matrix is defined as
$$\Sigma=E[(X-E(X))(X-E(X))^{T}]=\begin{bmatrix}
V[X_{1}] & Cov(X_{1},X_{2}) & \dots & Cov(X_{1},X_{n}) \\
Cov(X_{2},X_{1}) & V[X_{2}] & \dots & Cov(X_{2},X_{n}) \\
\dots & \dots & \dots & \dots \\
\dots & \dots & \dots & \dots  \\
Cov(X_{n},X_{1}) & Cov(X_{n},X_{2}) & \dots & V[X_{n}]
\end{bmatrix}$$
properties of covariance matrix
- $\Sigma$ is a symmetric matrix: $\Sigma^{T}=\Sigma$
- $\Sigma$ is PSD i.e. $\forall x\epsilon \mathbb{R}^{n},x^{T}\Sigma x\geq 0$


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File | created |
| ---- | ------- |

tab: Previous Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]] | April 18, 2025 |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]     | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                         | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=slyRsDIX7tA)
$$$
