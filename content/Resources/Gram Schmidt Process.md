---
publish: true
title: "Lecture 27 : Gram Schmidt Process"
description: This lecture discusses orthogonal sets, orthogonal projection, gram-schmidt orthogonalization process with some examples.
created: 2025-04-05
modified: 2026-10-15T16:16:14.555Z
published: 2021-08-17
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=2OMKVKxwI-4&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=29
author: IIT Roorkee
lecture: 27
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Inner product space

Let V be a vector space with an inner product space as (V,<.,.>)
**Definition**
Non zero vectors v1,v2,...,vk belongs to V form an orthogonal set if they are orthogonal to each other i.e. $<v_{i},v_{j}>=0$\if in addition all vectors are of unit norm, ||vi|| = 1, then v1,v2,...,vk forms an orthonormal set.

# Orthogonal Projection

**Theorem**
Let V be an inner product space and V\_0 be a finite dimensional subspace of V. Then any vector x belongs to V is uniquely represented as $x = p+o$
where p belongs to V\_0 and o is perp to V\_0
The component p is the orthogonal projection of the vector x onto the subspace V\_0. The distance from x to the subspace V\_0 is ||0||.
if {v1,v2,...,vn} is an orthogonal basis for V\_0 then,

$p = \sum_{i=1}^{n} \frac{<x,v_{i}>}{<v_{i},v_{i}>}v_{i}$

# Gram schmidt process

This is a process from which be can transform set of LI vectors to orthogonal vectors
Let V be an inner product space, suppose X1,X2,...,Xn is a basis of V. Now let,
$v_{1}=X_{1}$
$v_{2}=X_{2}-\frac{<X_{2},v_{1}>}{<v_{1},v_{1}>}v_{1}$
$v_{3}=X_{3}-\frac{<X_{3},v_{1}>}{<v_{1},v_{1}>}v_{1}-\frac{<X_{3},v_{2}>}{<v_{2},v_{2}>}v_{2}$
$v_{n}=X_{n}-\sum_{i=1}^{n-1} \frac{<X_{n},v_{i}>}{<v_{i},v_{i}>}v_{i}$
Then {v1,v2,...,vn} is an orthogonal set
and this set also span the vector space V

**Properties**

- simple form
  $v_{k}=X_{k}-(\alpha_{1}X_{1}+\dots+\alpha_{k-1}X_{k-1})$
- v\_k is orthogonal to X1,X2,...,X\_k-1
- v\_k = X\_k - p\_k, wehre pk is the orthogonal projection of the vector X\_k on the subspace spanned by X1,X2,...,X\_k-1
- ||v\_k|| is the distance X\_k to the subspace spanned by X1,X2,...,X\_k-1
- other form
  $v_{n}=X_{n}-\sum_{i=1}^{n-1}<X_{n},w_{i}>w_{i}, w_{i}=\frac{v_{i}}{||v_{i}||}$
  then {w1,w2,...,wn} is a orthonormal set

---

# Related

---

# Previous Lectures

```dataview
list
From
```

---

# References

![](https://www.youtube.com/watch?v=2OMKVKxwI-4\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=29)
