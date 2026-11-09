---
publish: true
title: "Lecture 17: PCA : Derivation and Examples"
description: This lecture includes the derivation explaining the concept of PCA and the relation between PCA and SVD.
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
source: https://www.youtube.com/watch?v=AyanC9AbEHA&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=19
author: IIT Roorkee
lecture: 17
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# PCA Derivation

The objective of PCA is to perform dimensionality reduction while preserving as much of the randomness in the high dimensional space as possible.
Let X be n-dimensional vector such that $X=\sum_{i=1}^{n}y_{i}\phi_{i}$
where {phi1,phi2,...phin} forms an orthonormal basis of n-dimensional coordinates yi are given as, $y_{i}=<X,\phi_{i}>=X^{T}\phi_{i}\forall i=1,2,\dots,n$
Now suppose, I want to represent X with fewer basis vectors, i.e. say m say m < n. we can do this by replacing the coordinates with some of pre selected constants
$\hat{X}(m)=\sum_{i=1}^{m}y_{i}\phi_{i}+\sum_{i=m+1}^{n}b_{i}\phi_{i}$
The representation error is given as $\Delta X(m)=X-\hat{X}(m)=\sum_{i=m+1}^{n}(y_{i}-b_{i})\phi_{i}$
Now, we can measure this representation error bt mean squared of the magnitude of del X, i.e. $E[|\Delta X|^{2}]=E\left[ \left( \sum_{m+1}^{n}(y_{i}-b_{i})\phi_{i} \right)^{2} \right]=E\left[\left( \sum_{m+1}^{n}(y_{i}-b_{i})\phi_{i} \right)\left( \sum_{m+1}^{n}(y_{i}-b_{i})\phi_{i} \right)\right]=E\left[\sum_{i=m+1}^{n}\sum_{j=m+1}^{n}(y_{i}-b_{i})(y_{j}-b_{j})\phi_{i}^{T}\phi_{j}\right]$
$E[|\Delta X|^{2}]=\sum_{i=m+1}^{n}E[(y_{i}-b_{i})^{2}]$
Finding bi
$\frac{\delta E[|\Delta X|^{2}]}{\delta b_{i}}=0 \implies b_{i}=E[y_{i}]$
on substituting,
$E[|\Delta X|^{2}]=\sum_{i=m+1}^{n}E[(y_{i}-E[y_{i}])^{2}], \space y_{i}=X^{T}\phi_{i}$
on substituting yi we get,
$E[|\Delta X|^{2}]=\sum_{i=m+1}^{n}E[(X^{T}\phi_{i}-E[X^{T}\phi_{i})^{2}] = \sum \phi_{i}^{T}E[(X-E(X))(X-E(X))^{T}]\phi_{i}$
This is known as covariance matrix, so
$E[|\Delta X|^{2}]=\sum_{i=m+1}^{n}\phi_{i}^{T}\Sigma_{X}\phi_{i}$
To find phii $\frac{\delta E[|\Delta X|^{2}]}{\delta \phi_{i}}=0 \text{ subject to } \phi_{i}^{T}\phi_{i}=1 \implies minimise \space E[|\Delta X|^{2}] \text{ s.t. }\phi_{i}^{T}\phi_{i}=1$
Using Lagrange multiplier, we need to minimize
$\sum_{i=m+1}^{n}\phi_{i}^{T}\Sigma_{X}\phi_{i}+\sum_{i=m+1}^{n}\lambda_{i}(1-\phi_{i}^{T}\phi_{i})=J(\phi_{i})$
Now, we make $\frac{\delta J(\phi_{i})}{\delta \phi_{i}}=0\implies\Sigma_{X}\phi_{i}=\lambda_{i}\phi_{i}$
Here phii, lami are eigen pair of the covariance matrix
From above equations we have, $E[|\Delta X|^{2}]=\sum_{i=m+1}^{n}\phi_{i}^{T}\lambda_{i}\phi_{i} = \sum_{i=m+1}^{n}\lambda_{i}$
In order to minimize the representation error lami is need to be smallest eigenvalues
Therefore in PCA we choose m eigenvectors corresponding to the m largest eigen values lami of the covariance matrix as the Principal directions

# PCA and SVD

Let the data matrix be C of size nXp. Then the principal directions (components) are coming from the eigen vectors of Covariance matrix as, $\Sigma_{X}=\frac{1}{n-1}C^{T}C$
Now if the SVD of C is given as $C = USV^{T}$
then, $\Sigma=\frac{1}{n-1}C^{T}C=\frac{1}{n-1}(USV^{T})^{T}USV^{T}=\frac{1}{n-1}VSU^{T}USV^{T}=\frac{1}{n-1}VS^{2}V^{T}$
The columns of V are the eigen vectors os Sigma. Therefore if the SVD of the data matrix is C=USV^T, then columns of V give the principal direction, XV=
Information preserve is given as,
$\%=\frac{|\lambda_{1}|+|\lambda_{2}|+\dots+|\lambda_{k}|}{|\lambda_{1}|+|\lambda_{2}|+\dots+|\lambda_{n}|}\times 100$

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                                       | April 08, 2025 |

tab: Previous Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                     | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]   | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=AyanC9AbEHA)
