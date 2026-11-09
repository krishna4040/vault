---
publish: true
title: "Lecture 56: Concepts of Duality"
description: This lecture deals with a few concepts of duality, formulation of dual of a constrained optimization problem, weak and strong duality results, which are essential in the formulation of hard and soft m
created: 2025-04-19
modified: 2026-10-15T16:16:14.553Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=V4bZxcRiaWY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=57
author: IIT Roorkee
lecture: 56
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Duality

- Duality is used in mathematical programming for many theoretical and computational developments in diverse fields including operations research, management science and economics.
- the duality principle connects two programs: one, the primal which is a constrained minimization or maximization problem and other called the dual which is a constrained maximization or minimization such that the existence of optimal solution to one of them ensures an optimal solution to other and optimal values of the two are equal
- Results developed in duality theory have helped develop numerical algorithms for solving certain optimization problems.

# Constrained Optimization Problem

The general form of a constrained optimization problem is given as
$(P)Min f(x), \text{ subject to } g_{i}(x) \leq 0$

# Lagragian function

The Lagrangian function for the problem P is defined as:
$L(x,\lambda)=f(x)+\sum_{i=1}^{m}\lambda_{i}g_{i}(x)=f(x)+\lambda^{T}g(x)$
where $x\epsilon \mathbb{R}^{n}, \lambda\epsilon \mathbb{R}^{m}$ and $g(x)=(g_{1}(x),g_{2}(x),\dots,g_{m}(x))^{T}$

# Dual problem

The dual of the problem P is given as:
$max \space L(x,\lambda) \text{ s/t } \nabla_{x}L(x,\lambda)=0, \lambda\geq 0$
This can be re written as:
$(D) \space max \space f(x)+\sum_{i=1}^{m}\lambda_{i}g_{i}(x) \text{ s/t } \nabla f(x)+\sum_{i=1}^{m}\lambda_{i}\nabla g_{i}(x)=0, \lambda_{i}\geq 0$
If f and alff $g_{i}$’s are convex functions the problem P become a CPP.

> [!note]
> The constraint of the Dual problem D is the KKT condition of primal problem P

# Weak duality theorem

Let x be feasible for CPP and $(u,\lambda)$ be feasible for D then,
$f(x)\geq f(u)+\sum_{i=1}^{m}\lambda_{i}g_{i}(u)$
**Corollary**
Let $\bar{x}$ be feasible to CPP and $(\bar{u},\bar{\lambda})$ be feasible for D. Further, let $f(\bar{x})=f(\bar{u})+\sum_{i=1}^{m}\bar{\lambda_{i}}g_{i}(\bar{u})$. Then, $\bar{x}$ is optimal for CPP and $(\bar{u},\lambda)$ is optimal for D

# Strong duality theorem

Let $\bar{x}$ be feasible to CPP and the basic constraint qualification hold at $\bar{x}$. Then there exists $\bar{\lambda}$ such that $(\bar{x},\bar{\lambda})$ is optimal to D. Futher, the optimal values of the two objective functions coincide.

# Dual of a QPP

$(QP) \space min \space C^{T}X+ \frac{1}{2}X^{T}QX \text{ s/t } AX\leq b , X\geq 0$
where A is an $m \times n$ matrix, $c,x\epsilon \mathbb{R}^{n}, b\epsilon \mathbb{R}^{m}$ and Q is an $a \times n$ symmetric PSD

---

# Follow up

```tabs
tab: Next Lectures
| File | created |
| ---- | ------- |

tab: Previous Lectures
| File                                                                                                          | created        |
| ------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Joint probability distribution and covariance.md\|Joint probability distribution and covariance]] | April 18, 2025 |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]]                   | April 18, 2025 |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]                       | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                                           | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]                     | April 18, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=V4bZxcRiaWY\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=57)
