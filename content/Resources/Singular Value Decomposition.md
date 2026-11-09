---
publish: true
title: "Lecture12: Singular Value Decomposition"
description: In this lecture, singular values and method to calculate orthogonal matrices U and V for singular value decomposition are discussed.
created: 2025-04-02
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-24
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=igG1egOAsRM&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=14
author: IIT Roorkee
lecture: 12
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# SVD need?

For rectangular matrices we cannot have diagonalization, we have singular values in case of rectangular matrices

# Singular values

Let A be a rectangular matrix of order m X n, consider the matrix A^T A, it is a symmetric matrix of order n which is PSD. The eigen values of A^T A are
$\lambda_{1}\geq\lambda_{2}\geq\dots\geq\lambda_{n}\geq 0$
let $\sigma_{i}=\sqrt{ \lambda_{i} }$
$\sigma_{1}\geq\sigma_{2}\geq\dots\sigma_{n}\geq 0$
The numbers s1,s2,..,sn are called singular values of A, where s is sigma

# SVD

Let A be a nXm matrix. The SVD of A is, $A = U\Sigma V^{T}$
where U and V are orthogonal matrix of order m and n respectively and sigma is a mXn matrix where diagonal elements of first r rows are singular values of a and rest of the entries are zeroes.

**Matrix V**
A is a mXn matrix then A^T A is mXm symmetric PSD matrix then eigen vectors corresponding to A^T A are v1,v2,...,vn are othonormal then V is given as $V = \begin{bmatrix}
v_{1} & v_{2} & \dots & v_{n}
\end{bmatrix}$
**Matrix U**
A is a mXn matrix then AA^T is nXn symmetric PSD matrix then eigen vectors corresponding to AA^T are u1,u2,...,um are othonormal then U is given as $U = \begin{bmatrix}
u_{1} & u_{2} & \dots & u_{m}
\end{bmatrix}$
**Matrix Sigma**
Let A is mXn matrix with rank(A)=r where, r<= min(m,n)
_if m>n_

$$$\Sigma=\begin{bmatrix}
\sigma_{1} & 0 & \dots & 0 \\
0 & \sigma_{2} & \dots & 0 \\
\dots & \dots & \sigma_{r} & \dots \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{bmatrix}$$
*if m < n*
$$\Sigma=\begin{bmatrix}
\sigma_{1} & 0 & \dots & 0 & 0 \\
0 & \sigma_{2} & \dots & 0 & 0 \\
\dots & \dots & \sigma_{r} & \dots & \dots \\
\end{bmatrix}$$

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
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                                             | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]                           | April 02, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |

`````
---
# References

![](https://www.youtube.com/watch?v=igG1egOAsRM)  
$$$
