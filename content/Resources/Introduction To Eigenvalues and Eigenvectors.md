---
publish: true
title: "Deep Learning(CS7015): Lec 6.1 Eigenvalues and Eigenvectors"
description: lec06mod01
created: 2025-04-23
modified: 2026-10-15T16:16:14.555Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/BTzz3BuYuM8/maxresdefault.jpg
source: https://www.youtube.com/watch?v=BTzz3BuYuM8&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=43
author: IIT Roorkee
cover: https://i.ytimg.com/vi/BTzz3BuYuM8/maxresdefault.jpg
lecture: 6.1
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

Look [[Eigenvalues and Eigenvectors]] in statistical ML

# Exploding and Vanishing Gradients (Intution)

## Definitions

## Dominant Eigen Value

Let $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$ be the eigen values of an $n \times n$ matrix A. $\lambda_{1}$ is called the dominant eigen value of A if
$|\lambda_{1}|\geq|\lambda_{i}|, i=2,\dots,n$

## Stochastic Matrix

A matrix M is called a column stochastic matrix if all the entries are positive and the sum of the elements in each column is 1

# Theorems

## Theorem ~ 1

The largest or dominant eigenvalue of a stochastic matrix is 1

## Theorem ~ 2

If A is a $n \times n$ square matrix with a dominant eigenvalue, then the sequence of vectors given by $Av_{0},A^{2}v_{0},\dots ,A^{n}v_{0},\dots$ approaches a multiple of the dominant eigenvector of A

## An Important Example

^5d37f8

Let us assume that on day 0, $k_{1}$ students eat Chinese food and $k_{2}$ eat mexican food, on each subsequent day i, a fraction $p$ of the students who ate chinese food on previous day continue to eat chinese and $(1-p)$ shift to mexican food
similarly a fraction q eats mexican and 1-q shifts to chinese
The number of customers in the two restraunts is thus given by:
$v_{0},Mv_{0},M^{2}v_{0},\dots$
![[System/Assets/Pasted image 20250423203445.png]]
![[System/Assets/Pasted image 20250423203514.png]]
Let $e_{d}$ be the dominant eigen vector of M and $\lambda_{d}=1$, the above series converges to
$v_{n}=M^{n}v_{0}=ke_{d}$
$v_{n+1}=Mv_{n}=k(Me_{d})=k(\lambda_{d}e_{d})=ke_{d}$
In general, for a square matrix A the above sequence can be given as
$A^{p+n}x_{0}=k(\lambda_{d})^{n}e_{d}$

- $|\lambda|>1$ will explode
- $|\lambda|<1$ will vanish
- $|\lambda|=1$ will reach steady state

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                        | created        |
| --------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear Algebra  Basic Definitions.md\|Linear Algebra  Basic Definitions]]                                       | April 23, 2025 |
| [[Resources/Eigenvalue Decompositon.md\|Eigenvalue Decompositon]]                                                           | April 24, 2025 |
| [[Resources/Principal Component Analysis and its Interpretations.md\|Principal Component Analysis and its Interpretations]] | April 24, 2025 |
| [[Resources/Regularization.md\|Regularization]]                                                                             | March 10, 2025 |
| [[Resources/Vectorial Representation of Words.md\|Vectorial Representation of Words]]                                       | March 10, 2025 |

tab: Previous Lectures
| File                                                                                                    | created        |
| ------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]] | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]                       | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                                           | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                               | April 23, 2025 |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]]               | April 23, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=BTzz3BuYuM8\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=43)
