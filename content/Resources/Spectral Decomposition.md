---
publish: true
title: "Lecture 11: Spectral Decomposition"
description: This lecture discusses eigen decomposition of square matrix, necessary condition for eigen decomposition, spectral decomposition of symmetric matrix and related python implementations.
created: 2025-04-02
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-24
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=x9pNERc7Tac&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=13
author: IIT Roorkee
lecture: 11
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Eigen decomposition

Let A be a square matrix of order n, also let {v1,v2,...,vn} be n LI eigenvectors of A, then A can be factorized as $A = PDP^{-1}$
The ith column of P is the eigenvector vi of A, and D is a diagonal matrix whose diagonal elements are the corresponding eigen values of A.
$D_{ii}=\lambda_{i}$

> [!note]
> Every square matrix does not pocesses eigen decomposition

**Condition for eigen decomposition**
We need AM=GM for each eigen value of A

- The matrix A should have n LI eigenvectors
- The eigenvectors of A forms a basis of n-dimensional vector space

# Spectral decomposition

Let A be a nXn symmetric matrix. Then, the eigen Decomposition of A is guaranteed.
$A = PDP^{-1}$
consider lam1,lam2,...,lamn are the eigen values of A and correspondingly v1,v2,...,vn eigen vectors of A then

$$$A = \begin{bmatrix}
v_{1} & v_{2} & \dots & v_{n}
\end{bmatrix}\begin{bmatrix}
\lambda_{1} \\
&\lambda_{2} \\
&& \dots \\
&&& \lambda_{n}
\end{bmatrix}\begin{bmatrix}
v_{1} &v_{2} & \dots&v_{n}
\end{bmatrix}^{-1}$$
Eigen vectors of symmetric matrix are orthogonal i.e.
$$v_{i}.v_{j}=0 \forall i\neq j$$
in that case, P is an orthogonal matrix i.e. $$P = P^{T}$$
implies,$$A = PDP^{T} = \sum_{i=1}^{n}\lambda_{i} v_{i}v_{i}^{T}$$
The decomposition of a matrix A in n rank-1 matrices is known as spectral decomposition of matrix A.

> [!note]
> Each matrix $$v_{i}v_{i}^{T}$$ is the projection onto 1D subspace spanned by vi

---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]         | April 02, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]         | April 02, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]                           | April 02, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]]                                             | March 30, 2025 |

`````
---
# References

![](https://www.youtube.com/watch?v=x9pNERc7Tac)
$$$
