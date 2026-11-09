---
publish: true
title: "Lecture 14: Low Rank Approximations"
description: In this lecture, we have explained rank of  a matrix, matrix factorization, low rank approximation, concept of convexity and some related examples.
created: 2025-04-02
modified: 2026-10-15T16:16:14.556Z
published: 2021-07-26
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=eNQioelqxHo&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=15
author: IIT Roorkee
lecture: 14
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Rank Of A Matrix

Let A be a mXn real matrix the rank of A is defined as $rank(A)=dim(range(A))$
It is the number of LI rows or columns of the matrix A

## Properties of Rank

- rank(A^T) = rank(A)
- rank(PAQ) = rank(A) for invertible matrices P and Q
- rank(AB) <= min{rank(A),rank(B)}

# Rank and Matrix Factorization

Let B = {b1,b2,...,br} be a subset of Rm with rank(A)=r be a basis of range(A). Then each column of A = \[a1, a2, ..., an] can be expressed as a linear combination of B.

$$$\begin{bmatrix}
a_{1} & a_{2} & \dots & a_{n}
\end{bmatrix} = \begin{bmatrix}
b_{1} & b_{2} & \dots & b_{r}
\end{bmatrix} \begin{bmatrix}
c_{11} & . & . & . & c_{1n} \\
. \\
. \\
. \\
c_{r1} & . & . & . & c_{rn}
\end{bmatrix}$$

factorization form is given as,
$$A = BC^{T}, B\epsilon R^{m\times r}\text{ and } C\epsilon R^{n\times r}$$
We say that A has low rank if rank(A) << min(m,n)
- number of elements in A = m.n
- number of elements in BC^T = mr + nr
## Motivation of LRA
suppose A is a matrix of order 50 x 100 and rank is 20 so to store elements of a in normal case we need 5000 units of memory while considering the factorization form we only need 3000 units of memory
# Low Rank Approximation
Let A be a large matrix of order mXn having rank(A)<=min(m,n). the LRA of A is to find another matrix Ak of order mXn which is having rank k<=r and approximate A.
To find the "best" Ak we must define how closely Ak approximates A. The simplest metric is the *Frobenius norm* A-Ak. This criterion leads to the following LRA problem:
$$||A-A_{k}||=min_{A_{k}}\{ ||A-A_{k}||_{F}:A_{k}\epsilon R^{m\times n}\text{ and } r(A_{k}) \leq k \}$$
This is a non convex optimisation problem as $$rank(\alpha A+(1-\alpha)B)\neq\alpha rank(A)+(1-\alpha)rank(B)$$
It is very difficult to find out global minima of non convex optimisation problem, Solution comes in form of SVD
Let ||.|| be a unitary invariant matrix norm
suppose A be a matrix of order mXn defined as $$A = U\Sigma V^{T}=\sum_{i=1}^{n}\sigma_{i}u_{i}v_{i}^{T}$$
Then the best k approximation to A is given as $$A_{k}=\sum_{i=1}^{k}\sigma_{i}u_{i}v_{i}^{T} \text{ where } k \leq rank(A)$$
The measure of *quality of approximation* is given by
$$\frac{||A_{k}||_{F}^{2}}{||A||^{2}_{F}}=\frac{\sigma_{1}^{2}+\sigma_{2}^{2}+\dots+\sigma_{k^{2}}}{\sigma_{1}^{2}+\sigma_{2}^{2}+\dots+\sigma_{r}^{2}}$$


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]]                                             | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |

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

![](https://www.youtube.com/watch?v=eNQioelqxHo)
$$$
