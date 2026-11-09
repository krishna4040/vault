---
publish: true
title: "Lecture 08 : Orthogonal Complement and Projection Mapping"
description: In this lecture, we have discussed orthogonal complement  and projection mapping with some examples and properties.
created: 2025-03-31
modified: 2026-10-15T16:16:14.557Z
published: 2021-07-15
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=zsD3nwxA274&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=10
author: IIT Roorkee
lecture: 8
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Orthogonal vectors

This is the generalization of perpendicular vectors
In an inner product space (V,<.,.>), two vectors vi and vj are said to be orthogonal if
$<v_{i},v_{j}> = 0$

## Orthogonal complement

If W is subset of V, where V is inner product space, then the orthogonal complement of W, denoted by Wp, is ser of vectors in V that are orthogonal to every element of W:
$W^{\perp}=\{ v\epsilon V|v\perp w\forall w\epsilon W \}$

#### Remarks

- There is no requirement on W to be a subspace of V. however, Wp is always subspace of V
- If W is also a subspace of V, the
  $V = W \oplus W^{\perp}$
  means, every vector v belongs to V can be written uniqely as
  $v = v_{w}+v_{w^{\perp}}$
  where,
  $V_{w}\epsilon W \text{ and } v_{w^{\perp}}\epsilon W^{\perp}$

## Orthogonal projection

Let V be an inner product space and W ve a subspace of V. Also let {w1,w2,...,wk} be an orthogonal basis of w.
The linear transformation
$P_{w}:V\to W$ is defined as,
$P_{w}(v)=\frac{<v,w_{1}>}{<w_{1},w_{1}>}w_{1}+\frac{<v,w_{2}>}{<w_{2},w_{2}>}w_{2}+\dots+\frac{<v,w_{k}>}{<w_{k},w_{k}>}w_{k}$

#### Remarks

$v-P_{w}(v) \epsilon W^{\perp}$
$P_{W}(w)=w \forall w\epsilon W$
$P_{W}^{2}=P_{W}$
$\text{for any }v\epsilon V,||P_{W}(v)|| \leq ||v||$
$\text{for any }v\epsilon V, \text{ and } w \epsilon W ||v-P_{W}(v)|| \leq ||v-w|| \text{ or } P_{W}(v)=arg_{w\epsilon W}min||v-w||$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                              | created        |
| --------------------------------------------------------------------------------- | -------------- |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]       | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]] | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                   | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]       | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                 | April 02, 2025 |

tab: Previous Lectures
| File                                                            | created        |
| --------------------------------------------------------------- | -------------- |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]             | March 31, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]] | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]       | March 30, 2025 |
| [[Resources/Vector Subspace.md\|Vector Subspace]]               | March 30, 2025 |
| [[Resources/Vector Space.md\|Vector Space]]                     | March 30, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=zsD3nwxA274\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=10)
