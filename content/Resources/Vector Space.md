---
publish: true
title: "Lecture 03: Vector Space : Definition and Examples"
description: This lecture introduces the concept of vector spaces, its definition and several examples.
created: 2025-03-30
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-10
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=AAQzgEJdgMA
author: IIT Roorkee
lecture: 3
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Vector spaces

A vector space V(R) over field R is a set on which two operations vector addition(+) and scaler multiplication(.) are defined such that

- M1: (V, +) forms an Abelian group
  - closure
  - commutative
  - associative
  - existence of additive identity
  - existence of additive inverse
- M2: The operation (.) is defined between scalars and vectors such that $\forall a\epsilon \mathbb{R} \text{ and } v \epsilon V \implies a.v\epsilon V$
- M3: Distributive
  $\forall a\epsilon \mathbb{R}\text{ and }v,w\epsilon V\implies a.(v+w)=av+aw$
- M4
  $\forall a,b\epsilon \mathbb{R} \text{ and } v\epsilon V, (a+b)v=a.v+b.v$
- M5
  $\forall a,b\epsilon \mathbb{R}\text{ and }v\epsilon V, (ab)v=a(bv)$
- M6: Unitary law
  $\exists1\epsilon \mathbb{R}\text{ s.t. }1.v=v \forall v\epsilon V$
  Then (V,+,.) is a vector space

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Vector Subspace.md\|Vector Subspace]]                                                           | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]                                                   | March 30, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]]                                             | March 30, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |

tab: Previous Lectures
| File                                            | created        |
| ----------------------------------------------- | -------------- |
| [[Resources/Matrix Algebra.md\|Matrix Algebra]] | March 30, 2025 |
| [[Resources/Vectors.md\|Vectors]]               | March 30, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=AAQzgEJdgMA)
