---
publish: true
title: "Lecture 42: Constrained Optimization-I"
description: In this lecture, we discuss the general formulation of a constrained optimization problem and various types of such problems
created: 2025-04-16
modified: 2026-10-15T16:16:14.553Z
published: 2021-08-24
tags:
  - resource
  - maths
  - optimization
  - AI
  - ML
source: https://www.youtube.com/watch?v=zlKSP3fhZhU&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=44
author: IIT Roorkee
lecture: 42
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Constrained optimization

$max/min_{g_{i}(x) \leq 0} f(x)$
where,
$f:\mathbb{R}^{n}\to R \text{ and } g_{i}:\mathbb{R}^{n}\to R$

# Types of constrained optimization problems

- if f and g\_i forall i are linear, the P is called **LPP**
- if P is not linear then we call it **NLPP**
- if f is quadratic, add all g\_i are linear, the problem is called **QPP**
- if f and all g\_i are convex then P is called convex programming problem **CPP**

## CPP

if f and g\_i are convex functions, then we say P is a CPP

**Different formats of CPP**

| optimization problem      | conditions to be cpp            |
| ------------------------- | ------------------------------- |
| min f(x), s.t. g\_i(x) < 0 | f and g\_i are convex            |
| max f(x), s.t. g\_i(x) < 0 | f is concave and g\_i are convex |
| min f(x), s.t. g\_i(x) > 0 | f is convex and g\_i are concave |
| max f(x), s.t. g\_i(x) > 0 | f and g\_i are concave           |

> [!note]
> All LPPs are CPPs are all linear functions are convex functions

**Theorem**
if g\_i are convex functions, then

$S = \{ x\epsilon \mathbb{R}n: g_{i}(x)\leq 0, i=1,2,\dots,m \}$
is a convex set

## QPP

The general form a QPP is given as
$min f(x) = C^{T}X+\frac{1}{2}X^{T}QX$
subject to
$AX \leq b, X \geq 0$
where C is coefficient matrix for the linear terms in f, and Q is the Hessian matrix of f

**Lemma**
if M be a symmetric PSD of order n then,
$X^{T}MY \leq \frac{1}{2}(X^{T}MX+Y^{T}MY), \forall X,Y\epsilon \mathbb{R}^{n}$
**Result**
A QPP is CPP if Q or Hessian matrix is a symmetric PSD

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]                   | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |

tab: Previous Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]               | April 16, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]                 | April 10, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=zlKSP3fhZhU\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=44)
