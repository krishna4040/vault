---
publish: true
title: "Deep Learning(CS7015): Lec 6.3 Eigenvalue Decompositon"
description: lec06mod03
created: 2025-04-24
modified: 2026-10-15T16:16:14.554Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/mdZVysybPrk/maxresdefault.jpg
source: https://www.youtube.com/watch?v=mdZVysybPrk&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=45&t=248s
author: IIT Roorkee
cover: https://i.ytimg.com/vi/mdZVysybPrk/maxresdefault.jpg
lecture: 6.3
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Eigenvalue Decomposition

Refer to [[Spectral Decomposition]] for more detail
Let $u_{1},u_{2},\dots,u_{n}$ be the eigenvectors of a matrix A and let $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$ be the corresponding eigenvalues
consider a matrix U whose columns are $u_{1},u_{2},\dots,u_{n}$ then,
$AU=U\Lambda$
if $U^{-1}$ exists, then we write
$A=U\Lambda U^{-1}$
is known as eigenvalue decomposition of A
Under what conditions would $U^{-1}$ exists if columns of U are LI

> [!important]
> When A is a symmetric matrix
>
> - every eigen vector is orthogonal to each other and hence LIs
> - $U^{-1}$ exists
> - $Q=U^{T}U=\begin{cases}0\text{if } i\neq j \\ 1 \text{ if } i= j\end{cases}=\mathbb{I}$
> - $U^{-1}=U^{T}$

# Results

Given EVD of $A=U\Lambda U^{T}$ the sequence $x_{0},Ax_{0},A^{2}x_{0},\dots$ in terms of eigenvalues of We arrive at previous conclusion [[Introduction To Eigenvalues and Eigenvectors#^5d37f8|Example on exploding and vaninshing gradients]]

# Theorem

If A is square symmetric $N\times N$ matrix, then the solution to the following optimization problem is given by the eigenvector corresponding to the largest eigenvalue of A
$max_{x}x^{T}Ax\text{ s.t. }||x||=1$
and the solution to
$min_{x}x^{T}Ax \text{ s.t. }||x||=1$ is given by smallest eigenvalue of A

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                        | created        |
| --------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Principal Component Analysis and its Interpretations.md\|Principal Component Analysis and its Interpretations]] | April 24, 2025 |
| [[Resources/Regularization.md\|Regularization]]                                                                             | March 10, 2025 |
| [[Resources/Vectorial Representation of Words.md\|Vectorial Representation of Words]]                                       | March 10, 2025 |
| [[Resources/CNN.md\|CNN]]                                                                                                   | March 10, 2025 |
| [[Resources/RNN.md\|RNN]]                                                                                                   | March 10, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear Algebra  Basic Definitions.md\|Linear Algebra  Basic Definitions]]                       | April 23, 2025 |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]] | April 23, 2025 |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]]     | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]                           | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                                               | April 23, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=mdZVysybPrk\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=45\&t=248s)
