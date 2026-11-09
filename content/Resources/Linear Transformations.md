---
publish: true
title: "Lecture 06 : Linear Transformations"
description: In this lecture, we have introduced the concept of linear transformations. Some related examples and rank-nullity theorem are also discussed in this lecture.
created: 2025-03-30
modified: 2026-10-15T16:16:14.556Z
published: 2021-07-15
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=Li4PfR7v7n8&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=8
author: IIT Roorkee
lecture: 6
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Linear Transformations or Mapping

- LT within calculus are used as way of tracking change, also known as _derivatives_
- In ML it is useful in _modeling of 2D and 3D animation_, where objects size and shape needs to be transformed from one viewing angle to the next.
- An object can be rotated and scaled within a space using a type of LT known as geometric transformations.
- LT also used to project the data from one space to another. _sometimes data set is not linearly separable_ in its original space, therefore we need to transform the data in another space with different dimensions. This can be done either using kernels or LT

**Dimension**
Let V and W be vectors over field F of dimensions n and m, respectively. A linear transformation is a mapping defined as
$T: V^{n}(F) \to W^{m}(F)$
such that
$T(v_{1}+v_{2})=T(v_{1})+T(v_{2}) \space \forall \space v_{1},v_{2}\epsilon V$
$T(\alpha v)=\alpha T(v) \space \forall \space v \space \epsilon \space V \text{ and } \alpha \space \epsilon \space F$

> [!Remarks]
>
> - A linear map from T to itself is called a linear operator
> - A linear map from a vector space to underlying field is called a linear functional.

# LT and Matrix

Every LT is a matrix and every matrix is a LT
suppose V(F) and W(f) are finite dimensional vector spaces with bases {v1,v2,..,vn} and {w1,w2,...,wn} respectively then
T is a linear map defined as
$T: V \to W$
then matrix of T is defined as where aij is elemnet of matrix,
$T(v_{j})=\sum_{i=1}^{m}a_{ij}w_{i}, \space 1\leq j\leq n$
**Geometrical representation**
It shows that jth column of the matrix  of linear map T consists of the coordinate of T(vj) in the chosen basis for W.
Conversely, every matrix
$A \epsilon R^{m\times n} \text{ induced a linear map } T:R^{n}\to R^{m} \text{ given by } T(v)=Av$

## Null space and Range of linear map

Let,
$T: V \to W$
$null(T) = \{ v \epsilon V|T(v)=0 \}$
$range(T)=\{ w\epsilon W|\exists v \epsilon V \text{ s.t. } T(v)=w \}$

> [!Remarks]
>
> - Nullspace of T is also called _Kernel_ of T denoted by ker(T)
> - Null(T) is a subspace of V
> - Range(T) is a subspace of W
> - The dimension of Null(T) is called nullity of T.
> - The dimension of Range(T) is called rank of T.

## Rank Nullity Theorem

For a linear map T,
$T: V \to W \implies dim(range(T)) + dim(null(T)) = dim(V)$
-----------------------------------------------------------

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]                           | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                                             | April 02, 2025 |

tab: Previous Lectures
| File                                                      | created        |
| --------------------------------------------------------- | -------------- |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]] | March 30, 2025 |
| [[Resources/Vector Subspace.md\|Vector Subspace]]         | March 30, 2025 |
| [[Resources/Vector Space.md\|Vector Space]]               | March 30, 2025 |
| [[Resources/Matrix Algebra.md\|Matrix Algebra]]           | March 30, 2025 |
| [[Resources/Vectors.md\|Vectors]]                         | March 30, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=Li4PfR7v7n8)
