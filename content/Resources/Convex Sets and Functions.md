---
publish: true
title: "Lecture 37: Convex Sets and Functions"
description: In this lecture, we talk about what convex sets and convex functions are and their graphical interpretation.
created: 2025-04-10
modified: 2026-10-15T16:16:14.553Z
published: 2021-08-23
tags:
  - resource
  - maths
  - convex analysis
  - AI
  - ML
source: https://www.youtube.com/watch?v=G6QkxaECZgc&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=39
author: IIT Roorkee
lecture: 37
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Convex Set

- while dealing with the algorithm related to ML, "Convexity" plays a vital role
- Several results have been developed in optimization theory based on the concept of convexity
  **Definition**
  A set S which is a subset of Rn is called a convex set if,
  $\forall x_{1},x_{2}\epsilon S \text{ and } \lambda\epsilon[0,1]\implies\lambda x_{1}+(1-\lambda)x_{2}\epsilon S$
  _Geometrically_, this means that a set is convex if the line segment joining any two points of S is also in S
  The RHS is also known as _Convex Linear Combination_ of x1 and x2,
  Geometrically it is the coordinates of the point on the line joining x1 and x2 which divides the line in the ratio lambda and (1-lambda)

**Example**
$S=\{ (x,y): x^{2}+y^{2}\leq 1 \}$
**Properties**

- The intersection of any arbitrary collection of convex sets is convex
- Union of two convex sets need not be convex
- The vector sum C1+C2 of two convex sets C1 and C2 is convex
- The set cC is a convex set for any convex set C and scaler c

# Convex Functions

Let S be a subset of Rn is a convex set and a function f: S->R is said to be convexx over S if,
$\forall x_{1},x_{2}\epsilon S,\lambda\epsilon[0,1]\implies\lambda f(x_{1})+(1-\lambda)f(x_{2})\geq f(\lambda x_{1}+(1-\lambda)x_{2})$
If this inequality holds in strict sense then f is called _Strictly convex_ function on S
_Geometrically_,
The line joining two arbitrarty points on the curve is always on or above the curve

# Concave Fucntions

Let S be a subset of Rn is a convex set and a function f: S->R is said to be convexx over S if,
$\forall x_{1},x_{2}\epsilon S,\lambda\epsilon[0,1]\implies\lambda f(x_{1})+(1-\lambda)f(x_{2})\leq f(\lambda x_{1}+(1-\lambda)x_{2})$

- Just the inequality is reversed
- if f is concave then -f is convex
  **Properties**
- sum of two concave or convex functions is of the same nature
- cf changes the nature of the function where c is constant

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]               | April 16, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]               | April 16, 2025 |

tab: Previous Lectures
| File                                                                            | created        |
| ------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]     | April 10, 2025 |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]     | April 09, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=G6QkxaECZgc\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=39)
