---
publish: true
title: "Lecture 16: Principal Component Analysis - I"
description: In this lecture, we have discussed mean, standard deviation, covariance followed by method to calculate covariance matrix associated with the data. Further, we have explained principal components of t
created: 2025-04-02
modified: 2026-10-15T16:16:14.557Z
published: 2021-07-26
tags:
  - resource
  - maths
  - LA
  - statistics
  - AI
  - ML
source: https://www.youtube.com/watch?v=qZPUBPLMtmo&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=17&t=1004s
author: IIT Roorkee
lecture: 16
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# PCA

For samples x1,x2,...,xn we have mean defined as
**Mean**
$Mean=\mu=\frac{1}{n}\sum_{i=1}^{n}x_{i}$
**Standarad deviation**
$\sigma=\sqrt{ \frac{1}{n}\sum_{i=1}^{n}(x_{i}-\mu)^{2} }$
**Covariance**
It is a measure of how two variables change together
$\Sigma_{XY}=\frac{1}{n}\sum_{i=1}^{n}(x_{i}-\mu_{x})(y_{i}-\mu_{y})^{T}$
_Covariance > 0_: Two variables are changing in same direction
_Covariance < 0_: Two variables are changing in opposite direction
_Covariance=0_: Two variables are independent of each other

**Covariance Matrix**
For a k-dimensional dataset {X1, X2, ..., Xk} the covariance matrix is defined as

$$$\Sigma=\begin{bmatrix}
\sigma_{X_{1}}^{2} & \Sigma_{X_{1}X_{2}} & \dots & \Sigma_{X_{1}X_{k}} \\
\Sigma_{X_{1}X_{2}} & \sigma_{X_{2}}^{2} & \dots& \Sigma_{X_{2}X_{k}} \\
. & . & . & . \\
. & . & . & .  \\
\Sigma_{X_{k}X_{1}} & . & . & \sigma_{X_{k}}^{2}
\end{bmatrix}_{k\times k}$$
It is a symmetric matrix of order k hence having real eigen values and there is orthogonal decomposition

**Principal components**
The principal components are the eigen vectors of the covariance matrix of the data
- First PC is the eigen vectoer corresponding to the largest eigen value of the covariance matrix
- If we want to transform a n dimensional dataset to a k dimensional dataset then we will select first k principal components
- These k PCs are the eigen vectors of the covariance matrix $$\Sigma=\frac{1}{n}C^{T}C$$ corresponding to top k largest eigen values

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |

tab: Previous Lectures
| File                                                                              | created        |
| --------------------------------------------------------------------------------- | -------------- |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                 | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]       | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                   | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]] | April 02, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]       | April 02, 2025 |

`````
---
# References

![](https://www.youtube.com/watch?v=qZPUBPLMtmo)
$$$
