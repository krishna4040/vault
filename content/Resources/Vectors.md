---
publish: true
title: "Lecture 01: Vectors in Machine Learning"
description: In this lecture, we have discussed the concepts of vector algebra, linear combinations of vectors, linearly dependent and  independent  vectors, orthogonal vectors and feature vectors with examples.
created: 2025-03-30
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-10
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
author: IIT Roorkee
lecture: 1
project: "[[Artificial Intelligence]]"
reference: https://www.youtube.com/watch?v=Y1Gndz4sNeE
cover:
type: literature
---

# Vector

A vector is a mathematical object that encodes a length and direction

# Vectors in N dimensional Real numbers

$v = [v_{1},v_{2},\dots,v_{n}] \epsilon R^n$

$$$v = \begin{vmatrix}
v_{1} \\
v_{2} \\
. \\
. \\
v_{n}
\end{vmatrix} \epsilon R^n$$
# Properties of Vectors
## Addition and Subtraction
We can add or subtract two vectors if they have same dimensions
$$v_{1}=(x_{1},x_{2},\dots ,x_{n})$$
$$v_{2} = (y_{1},y_{2},\dots,y_{n})$$
$$v_{1}\pm v_{2}=(x_{1}\pm y_{1}, x_{2}\pm y_{2},\dots,x_{n}\pm y_{n})$$
## Dot product
$$v_{1}.v_{2}=x_{1}y_{1}+x_{2}y_{2}+\dots+x_{n}y_{n}=\sum_{i=1}^{n}x_{i}y_{i}$$
## Length or Magnitude
$$|\vec{v}| = \sqrt{ \vec{v}.\vec{v} } = \sqrt{ x_{1}^{2}+x_{2}^{2}+\dots+x_{n}^{2} }$$
## Angle between two vectors
$$\theta = \cos ^{-1}\left( \frac{v_{1}.v_{2}}{|v_{1}||v_{2}|} \right)$$

# Linear Combination of vectors
Consider a set of k vectors, then a new vector v is defined such that
$$v = \alpha_{1}v_{1}+\alpha_{2}v_{2}+\dots+\alpha_{n}v_{n}$$
is called linear combination of k vectors where aplhas are scalar coming from filed on which the k vectors are defined
# Linear Independent and Dependent vectors
A set of vectors S is linearly independent if the linear combination of the vectors is equivalent to zero vector holds only when all alphas are 0
if any alpha is non-zero then the vectors are linearly dependent

> [!important]
> 1. In N dimensional real space, a set of more than n vectors is LD
> 2. Any set containing 0 vector is LD
# Orthogonal vectors
We say that a set of vectors are mutually(pairwise) orthogonal if
$$v_{i}.v_{j}=0, i\neq j$$
A set of orthogonal vectors is *orthonormal* if each vector has length is 1
$$\left( \frac{1}{\sqrt{ 2 }}, \frac{1}{\sqrt{ 2 }} \right), \left( \frac{1}{\sqrt{ 2 }}, \frac{-1}{\sqrt{ 2 }} \right)$$
> [!info]
> A set of orthogonal vector is **LI**
# An Example of feature vectors

| samples | Height | Weight |
| ------- | ------ | ------ |
| e1      | a_1    | b_1    |
| e2      | a_2    | b_2    |
| e_k     | a_k    | b_k    |
Height and wight are features, and each sample is related to its feature using vector representation as follows
$$e_{k}=(\alpha_{1},\beta_{1})$$

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                            | created        |
| --------------------------------------------------------------- | -------------- |
| [[Resources/Matrix Algebra.md\|Matrix Algebra]]                 | March 30, 2025 |
| [[Resources/Vector Space.md\|Vector Space]]                     | March 30, 2025 |
| [[Resources/Vector Subspace.md\|Vector Subspace]]               | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]       | March 30, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]] | March 30, 2025 |

tab: Previous Lectures
| File | created |
| ---- | ------- |

`````
---
# References

![](https://www.youtube.com/watch?v=Y1Gndz4sNeE)  
$$$
