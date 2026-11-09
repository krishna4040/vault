---
publish: true
title: "Lecture 43: Constrained Optimization-II"
description: In this lecture, we discuss few more properties of constrained optimization.
created: 2025-04-17
modified: 2026-10-15T16:16:14.553Z
published: 2021-08-24
tags:
  - resource
  - maths
  - optimization
  - AI
  - ML
source: https://www.youtube.com/watch?v=_ETexK2F8ag&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=44
author: IIT Roorkee
lecture: 43
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Solving CPs

**Necessary Conditions**
Let x bar, be a local min point of the problem at which basic qualification holds. Then there exist multiplies (called KKT-multipliers), lambda\_i, such that following holds

$\nabla f(\bar{x})+\sum_{i=1}^{m}\lambda_{i}\nabla g_{i}(\bar{x})=0$

$g_{i}(\bar{x})\leq 0, i=1,2,\dots,m$

$\lambda_{i}g_{i}(\bar{x}) = 0$

$\lambda_{i}\geq 0 ,\forall i$

These are called **KKT conditions**

**Sufficient condition**
if f and g are differentaible convex functions, the x bar is point of global min of problem

> [!important]
> A KKT point for a CPP is the optimal point or solution

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                         | April 18, 2025 |

tab: Previous Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]               | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]               | April 16, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=_ETexK2F8ag\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=44)
