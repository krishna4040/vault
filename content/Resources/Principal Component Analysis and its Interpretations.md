---
publish: true
title: "Deep Learning(CS7015): Lec 6.4 Principal Component Analysis and its Interpretations"
description: lec06mod04
created: 2025-04-24
modified: 2026-10-15T16:16:14.557Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/5eEPs8XS5AQ/maxresdefault.jpg
source: https://www.youtube.com/watch?v=5eEPs8XS5AQ&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=47
author: IIT Roorkee
cover: https://i.ytimg.com/vi/5eEPs8XS5AQ/maxresdefault.jpg
lecture: 6.4
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# PCA

![[System/Assets/Pasted image 20250515190527.png]]
The data is in $\mathbb{R}^{2}$, we consider a new basis $\vec{u_{1}},\vec{u_{2}}$ and we realize that the $u_{2}$ direction adds noise and does not contribute in classification
In general, we are interested in representing the data in fewer dimensions such that

- the data has high variance along these dimensions or remove those dimensions where variance is low
- the dimensions are linearly independent
- even better if they are orthogonal

Let $p_{1},p_{2},\dots,p_{n}$ be a set of such n LI orthogonal vectors. Let P be a $n\times n$ matrix such that these vectors are columns of P
Let $x_{1},x_{2},\dots,x_{m}\epsilon \mathbb{R}^{n}$ be m data points and let X be a matrix such that thesse are the rows of this matrix. Further let us assume that the data is 0 meand and unit variance
We want to represet each $x_{i}$ using this new basis $P$ so,
$x_{i}=\alpha_{i1}p_{1}+\dots+\alpha_{in}p_{n}$
For orthogonal basis we can find $\alpha_{i}$’s using
$\alpha_{ij}=x_{i}^{T}p_{j}$
In general the transformed data $\hat{x_{i}}$ is given by
$\hat{x_{i}}=x_{i}^{T}P$
and for all data points, $\hat{X}=XP$

# Covariance Matrix

If X is a matirx whose colums are zero mean then $\Sigma=\frac{1}{m}X^{T}X$ is the covariance matrix, In other words each entry in this matrix stores the covariance between column i and j
$\Sigma_{ij}=\frac{1}{m}\sum_{k}(X_{ki}-\mu_{i})(X_{kj}-\mu_{j})$

# Finding P

Covarinace Matrix of new data is given as,
$\hat{\Sigma}=\frac{1}{m}\hat{X^{T}}\hat{X}=P^{T}\Sigma P$
For our conditions of least covariance we want,

$$$\begin{cases}
\hat{\Sigma}_{ij} = 0, i\neq j \\
\hat{\Sigma}_{ij} \neq0, i = j
\end{cases}$$
In other words, we want $\hat{\Sigma}=P^{T}\Sigma P=D$, Hence P contains Eigen vectors of $\Sigma=XX^{T}$ by eigen value decomposition
# What about Higher variance?
The ith dimension of the transformed data $\hat{X}$ is given by $\hat{X_{i}}=Xp_{i}$ and the variance is given as
$$V=\frac{\hat{X_{i}^{T}}\hat{X}_{i}}{m}=\frac{1}{m}p_{i}^{T}X^{T}Xp_{i}=\frac{1}{m}p_{i}^{T}\lambda_{i}p_{i}=\frac{\lambda_{i}}{m}$$
Since we pick top k eigen values we ensure high variance

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Regularization.md\|Regularization]]                                       | March 10, 2025 |
| [[Resources/Vectorial Representation of Words.md\|Vectorial Representation of Words]] | March 10, 2025 |
| [[Resources/CNN.md\|CNN]]                                                             | March 10, 2025 |
| [[Resources/RNN.md\|RNN]]                                                             | March 10, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Eigenvalue Decompositon.md\|Eigenvalue Decompositon]]                                           | April 24, 2025 |
| [[Resources/Linear Algebra  Basic Definitions.md\|Linear Algebra  Basic Definitions]]                       | April 23, 2025 |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]] | April 23, 2025 |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]]     | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]                           | April 23, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=5eEPs8XS5AQ&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=47)
$$$
