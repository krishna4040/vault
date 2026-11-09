---
publish: true
title: "Lecture 13: SVD : Properties and Applications"
description: This lecture explains the properties of SVD, concept of Pseudo-inverse and different types of  matrix norms.
created: 2025-04-02
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-26
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=MXbkQ0CkYS4&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=15
author: IIT Roorkee
lecture: 13
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Properties

Let A be a mXn real matrix and rank of A is r and SVD is given as, $A = U\Sigma V^{T}$ then,

- only the first r singular values of A are non zero
- the _range_ of A and A^T are given by _first r columns_ of the matrix U and V respectively
- the _null_ of A and A^T are given by _last n-r and m-r_ columns of the matrix V and U respectively

# SVD and Psudeo-inverse

Let A be a mXn real matrix and rank of A is r and SVD is given as, $A = U\Sigma V^{T}$
$A^{+}=(U\Sigma V^{T})^{+} = (V^{T})^{-1}\Sigma^{+}U^{-1}$
**Matrix Sigma Plus**

$$$\Sigma=\begin{bmatrix}
\sigma_{0} \\
& \sigma_{1} \\
&&\dots \\
&&&\sigma_{r} \\
&&&&\dots
\end{bmatrix}_{m\times n} \implies \Sigma^{+}=\begin{bmatrix}
\frac{1}{\sigma_{0}} \\
& \frac{1}{\sigma_{1}} \\
&&\dots \\
&&& \frac{1}{\sigma_{r}} \\
&&&&\dots
\end{bmatrix}_{n\times m}$$
> [!note]
> if any sigma is 0 do not replace by its reciprocal instead do not replace it write 0 id the resultant matrix itself
# Operator and Matrix Norms
If V(F) and W(F) are vectors spaces and the set defined as
$$\tau=\{ T|T:V\to W \text{ is a linear map} \}$$
The set tau forms a vector space over the field F. the norm $$||T||_{op}=max_{X\epsilon V,X\neq 0} \frac{||TX||_{W}}{||X||_{V}}$$
is called operator norm on the space T.
For a matrix A of order mXn, we define the p-norm as $$||A||_{p}=max_{X\neq 0} \frac{||AX||_{p}}{||X||_{p}}$$
#### Examples
$$||A||_{1}=max_{1\leq j \leq n}\sum_{i=1}^{m}|a_{ij}|$$
$$||A||_{\infty}=max_{1\leq i\leq m}\sum_{j=1}^{n}|a_{ij}|$$
$$||A||_{2}=\sigma_{1}(A), \text{ where sigma1 denotes the largest singluar values} = max_{\lambda_{i}}\{ |\lambda_{i}| \} \text{ also called spectral norm}$$
*Forbenius norm*
$$||A||_{F}=\sqrt{ \sum_{i=1}^{min(m,n)}\sigma_{i}^{2}(A) }=\sqrt{ trace(A^{T}A) }$$

> [!note]
> A matrix norm ||.|| is said to be unitary invariant if $$||UAV||=||A||=||\sum||$$ for all orthogonal matrices U and V of appropriate size.

---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                                                               | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]]                                             | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]                                 | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                                             | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]                           | April 02, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |

`````
---
# References

![](https://www.youtube.com/watch?v=MXbkQ0CkYS4)
$$$
