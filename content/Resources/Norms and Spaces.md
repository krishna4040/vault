---
publish: true
title: "Lecture 07 : Norms and Spaces"
description: In this lecture, we have discussed about metric spaces, normed spaces, inner product spaces and some related examples.
created: 2025-03-31
modified: 2026-10-15T16:16:14.557Z
published: 2021-07-15
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=lhWKL1tKvx0&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=8
author: IIT Roorkee
lecture: 7
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Metric spaces

It is generalization of distance
A metric on a set S is a function
$d: S \times S \to R$
satisfying
$d(x,y)\geq_{0},\forall x,y\epsilon S \text{ and } d(x,y)=0\iff x=y $
$d(x,y)=d(y,x)$
$d(x,z)\leq d(x,y)+d(y,z) \forall x,y,z\epsilon S$
then (S,d) is called metric space

# Norm spaces

It is generalization of length
A norm on a real vector space V is a function
$||||:V\to R$
such that
$||X||\geq 0 \space \forall X\epsilon V \text{ and }||X||=0 \iff X=\vec{0}$
$||\alpha X||=|\alpha|||X||\space\forall\space X \epsilon V \text{ and } \alpha\epsilon R$
$||X+Y|| \leq ||X||+||Y|| \forall X,Y\epsilon V$

## Relation between Norm and Metric spaces

- Every normed space is a metric space
- converse is not true

#### Examples of some norms on Rn

$||X||_{p}=(\sum_{i=1}^{n}|x_{i}|^{p})^{1/p}$
$||X||_{\infty}=max_{1\leq i\leq n}|x_{i}|$

- p=1: Manhattan norm
- p=2: Euclidean norm
- p=0: L0 norm, it is a number of non-zero elements in X, it is not strictly a norm, this is used in _Compressed sensing_ in ML

#### Visualizing norms

suppose we have two vectors in 2D, starting from one vector there are infinite paths to go to the second vector, all these paths constitute to all these p norms, just norms are not actual curved paths, they are a way to measure effort required to reach from one vector to other

## Convex function

A function f,
$f:S\subset R^{n} \to R$
is said to be convex if for
$x_{1},x_{2}\epsilon S$
we have,
$f(\lambda x_{1}+(1-\lambda)x_{2}) \leq \lambda f(x_{1})+(1-\lambda)f(x_{2})$
where,
$0\leq\lambda\leq 1$

#### Geometrical interpretation

If you plot f(x) = x^2, you’ll see that the curve always lies below the straight line joining any two points on it. This shows that the function is convex.

#### Convex set

A set is said to be convex, if the line joining any two points of the set lies entirely in the set S.
Example: A solid cricle
$S = \{ (x,y)\epsilon R^{2}|x^{2}+y^{2}\leq r^{2} \}$
$\lambda(x_{1},y_{1})+(1-\lambda)(x_{2},y_{2})$
A hollow circle is not convex set, Eqn is given as
$\{ (x,y)\epsilon R^{2}|x^{2}+y^{2}=r^{2} \}$

> [!tip]
> All norms are convex sets

# Inner product spaces

It is generalization of dot product
An inner product on a real vector space V is a function
$<.,.>: V\times V\to R$
satisfying,
$<X,X> \geq 0 \space \forall X\epsilon V \text{ and } $

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]                           | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                                             | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]                                 | April 02, 2025 |

tab: Previous Lectures
| File                                                            | created        |
| --------------------------------------------------------------- | -------------- |
| [[Resources/Linear Transformations.md\|Linear Transformations]] | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]       | March 30, 2025 |
| [[Resources/Vector Subspace.md\|Vector Subspace]]               | March 30, 2025 |
| [[Resources/Vector Space.md\|Vector Space]]                     | March 30, 2025 |
| [[Resources/Matrix Algebra.md\|Matrix Algebra]]                 | March 30, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=lhWKL1tKvx0)
