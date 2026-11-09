---
publish: true
title: "Lecture 41: Unconstrained Optimization"
description: In this video, we discuss in detail about unconstrained optimization and several results for optimal solution.
created: 2025-04-16
modified: 2026-10-15T16:16:14.559Z
published: 2021-08-24
tags:
  - resource
  - maths
  - optimization
  - AI
  - ML
source: https://www.youtube.com/watch?v=6h_10zMtSxc&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=43
author: IIT Roorkee
lecture: 41
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Unconstrained Optimization

$min/max_{x\epsilon \mathbb{R}^{n}} f(x)$

## Optimality conditions

### First order optimality conditions

let f:U->R be a fuction defined on a set U subset of Rn. Suppose that x bar belongs to int(U) is a local optimal point and all partial derivatives of f exists at x bar. Then $\nabla f(\bar{x})=0$
**Stationary point**
let f:U->R be a fuction defined on a set U subset of Rn. Suppose that x bar belongs to int(U) and f be differentiable over some neighbourhood of x bar, then x bar is called a SP of f if,
$\nabla f(\bar{x})=0$

### Second order optimality conditions

**Necessary conditions**
Let f be twice differentiable function defined on an open set U. Let x bar belongs to int(U) be a local minimum of f. Then,
$\nabla^{2}f(\bar{x}) \text{ is PSD}$
**Sufficient conditions**
Let f be twice differentiable function defined on an open set U. Let x bar belongs to int(U) be a stationary point. if,
$\nabla^{2}f(\bar{x}) \text{ is PSD}$
then x bar is a strict minimum point of f.

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]                     | April 16, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]                   | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |

tab: Previous Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]                 | April 10, 2025 |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]           | April 10, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=6h_10zMtSxc\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=43)
