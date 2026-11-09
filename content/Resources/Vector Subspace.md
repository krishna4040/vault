---
publish: true
title: "Lecture 04 : Vector Subspace:  Examples and Properties"
description: This lecture discusses vector subspaces, its definition, properties, examples and some theorems based on this concept.
created: 2025-03-30
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-10
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=gQgZIq945IY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=5
author: IIT Roorkee
lecture: 4
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Vector subspaces

If Rn is a vector space over R then subset S of Rn is said to be a subspace of vector space Rn, is S is also a vector space over the same field R.
or
these three conditions are met
$0\epsilon S$
$\text{S is closed under vector addition: } x,y\epsilon S \implies x+y\epsilon S$
$\text{S is closed under scaler multiplication: } x \epsilon S, \alpha \epsilon R \implies \alpha x \epsilon S$

> [!Theorem]
> Let W be a subset of Rn. Then W is a subspace of Rn if and only if the following conditions hold:
> $W \neq \phi$
> $\text{For any } a,b \epsilon R \text{ and any } \vec{u}, \vec{v} \epsilon W, a\vec{u}+b\vec{v}\epsilon W$

# Geometrical interpretation of subspace of 3D Real plane

if we have a subspace of R3, then

1. origin
2. A line passing through origin
3. A plane passing through origin
4. The space R3 itself

# Some important results

## Theorem1

The intersection of any non-empty collection of sf subspaces of Rn is a subspace of Rn
$S_{1} \epsilon V, S_{2}\epsilon V \implies S_{1}\cap S_{2}\epsilon V$

## Theorem2

The union of two subspaces of Rn is a subspace of Rn if one of them is contained in the other.

# Linear span

Let V(F) be a vector space.
Let S be a non-empty subset of V. Then the set
L(S) given as,
$L(S)=\{ c_{1}v_{1}+c_{2}v_{2}+\dots+c_{n}v_{n} \}, c_{i}\epsilon R$
which is set of all the linear combination of vectors in S, is called linear span of set S

## Geometrical interpretetion of Linear span in 3D

| Vectors in S      | Geometric Shape Formed | Span Covers                    |
| ----------------- | ---------------------- | ------------------------------ |
| One vector        | Line                   | One direction (1D)             |
| Two independent   | Plane                  | 2D surface in 3D space         |
| Three independent | Full space             | All of R3\mathbb{R}^3          |
| Two dependent     | Line                   | No new dimension is added      |
| Three dependent   | Plane or Line          | Depends on which are dependent |

> [!tip]
> The span of n LI vectors in in Rn plane is the entire plane

> [!Theorem]
> Let V(F) is a vector space and let S be a non empty subset of V. then L(S) is a subspace of V

> [!Theorem]
> Let S be a non empty subset of a vector space V, then L(S) is the smallest subspace of V(F) containing S.

# Subspaces in Matrices

Let

$$$A_{m,n}=\begin{bmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n}\\
\dots & \dots & \dots & \dots \\
a_{m1} & a_{12} & \dots & a_{1n}
\end{bmatrix}$$
1. where aij belongs to R then,The row space of A is given by
$$L(\{ (a_{11}, a_{12}, \dots, a_{1n}), (a_{21},a_{22},\dots,a_{2n}), \dots,(a_{m1},a_{m2},\dots,a_{mn}) \})$$

2. The column space of A is given by
$$L(\{ (a_{11}, a_{21}, \dots, a_{m1}), (a_{12},a_{22},\dots,a_{m2}), \dots,(a_{n1},a_{n2},\dots,a_{mn}) \})$$
3. The set N(A) is said to be nullspace of A defiend as
$$N(A) = \{ x\epsilon R^{n} | AX=0 \}$$
4. The set R(A) is said to be range of A defined as
$$R(A)=\{ b\epsilon R^{m}|AX=b, X\epsilon R^{n} \}$$
---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]                                                   | March 30, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]]                                             | March 30, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |

tab: Previous Lectures
| File                                            | created        |
| ----------------------------------------------- | -------------- |
| [[Resources/Vector Space.md\|Vector Space]]     | March 30, 2025 |
| [[Resources/Matrix Algebra.md\|Matrix Algebra]] | March 30, 2025 |
| [[Resources/Vectors.md\|Vectors]]               | March 30, 2025 |

`````
---
# References
![](https://www.youtube.com/watch?v=gQgZIq945IY)
$$$
