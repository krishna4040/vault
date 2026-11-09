---
publish: true
title: "Lecture 39: Properties of Convex functions-II"
description: In this lecture, we discuss few more properties of convex functions.
created: 2025-04-15
modified: 2026-10-15T16:16:14.558Z
published: 2021-08-24
tags:
  - resource
  - maths
  - convex analysis
  - AI
  - ML
source: https://www.youtube.com/watch?v=dy8XP3xpqM8
author: IIT Roorkee
lecture: 39
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Properties of convex functions

## Definiteness of a matrix

A symmetric matrix H of order n is said to be:

- PSD if,  and PS if followed strictly $x^{T}Hx\geq0, \forall x\epsilon \mathbb{R}^{n}$
- NSD if,  and NS if followed strictly $x^{T}HX\leq0, \forall x\epsilon \mathbb{R}^{n}$

> [!note]
> A symmetric matrix H is NSD/ND if and only if -H is PSD/PD

## Test for Definiteness of a Matrix

### Test 1 ~ Eigen value test

Let A be a real symmetric matrix of order n. Then A is

- _PD_ if and only if eigen values are positive
- _PSD_ iff evs are non negetive
- _ND_ iff evs are negetive
- _NSD_ iff evs are non positive
- _Indefinite_ iff at least one positive and one negative eigen value

### Test 2 ~ Principal Minor test

**Principal Minor**
A PM D\_k of a matrix A of order k is the determinant of the matrix formed by deleting any (n-k) rows and (n-k) columns with the same number

**PMT**
The necessay and sufficient condition for a symmetric matrix to be PSD is that all the possible principal minors should be _Nonnegative_

> [!note]
> for NSD multiply by -1 and check for PSD

## Convex function

if f is a function defined on an open subset S of Rn and if the hessian matrix of f is PSD then f is a convex function
$\nabla^{2}f(x): PSD, \forall x\epsilon S\implies \text{f is convex}$
**Proof**
let f be a convex function on S. let x bar belongs to S then we have to show that $x^{T}\nabla^{2}f(\bar{x})x\geq 0$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                        | created        |
| --------------------------------------------------------------------------- | -------------- |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]] | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]     | April 16, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]     | April 16, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]   | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]           | April 17, 2025 |

tab: Previous Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]] | April 10, 2025 |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]               | April 10, 2025 |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]         | April 10, 2025 |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]       | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]]     | April 09, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=dy8XP3xpqM8)
