---
publish: true
title: "Lecture 28 : Polar Decomposition"
description: This lecture explains the concept of polar decomposition and relation of polar decomposition with Singular value decomposition.
created: 2025-04-08
modified: 2026-10-15T16:16:14.557Z
published: 2021-08-17
tags:
  - maths
  - LA
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=MNkzdaxhnCI&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=29
author: IIT Roorkee
lecture: 28
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Polar Decomposition

It is another decomposition technique to decompose square or rectangular matrices
**Concept**
$z = x+iy = re^{i\theta}, \space r = \sqrt{ x^{2}+y^{2} }, \space \theta=\tan ^{-1}\left( \frac{y}{x} \right)$
$r \geq0, e^{i\theta}=\cos\theta+i\sin\theta$
**Matrices**
$A = PW$
P is PSD and W is an isometry

> [!tip]
> **Isometry**
> $||Tu||=||u||$

**Theorem**
For any square matrix of dimension n, there exists an orthogonal matrix W and a PSD matrix P such that A = WP
Further more if A is an invertible matirx then the factorization is unique
**Proof**
From SVD of A we have,
$A = USV^{T} = UV^{T}VSV^{T}=WP$
$W = UV^{T}, P=VSV^{T}$
_Uniquness_
Let the factorization is not unique i.e.
$A = WP = ZQ$
hence,
$WP=ZQ \implies Z^{T}W=QP^{-1}\implies QP^{-1} \text{ is an orthogonal matrix} \implies (QP^{-1})^{T}(QP^{-1})=I \implies P^{-1}Q^{2}P^{-1}=I\implies P^{2}=Q^{2}\implies P=Q$

# PD in case of rectangular matrices

## Left Polar Decomposition

Let A be a mXn matrix where n>=m then the LPD of A is $A=HU$
where H is a PSD of order m and U is a mXn matrix having orthonormal columns
$H = \sqrt{ AA^{T} }=SB^{1/2}S^{T}$

## Right Polar Decomposition

Let A be a mXn matrix where m>=n then the RPD of A is $A=UP$ where U is a mXn matrix with orthonormal columns and P is a PSD of order n
$P = \sqrt{ A^{T}A }=SB^{1/2}S^{T}$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]                                     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]]                                   | April 09, 2025 |

tab: Previous Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=MNkzdaxhnCI\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=29)
