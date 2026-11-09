---
publish: true
title: "Lecture 44: Steepest Descent method"
description: In this lecture, we discuss the basic of numerical optimization algorithms and see in detail the steepest descent method to solve an unconstrained optimization problem.
created: 2025-04-17
modified: 2026-10-15T16:16:14.559Z
published: 2021-08-24
tags:
  - resource
  - maths
  - optimization
  - AI
  - ML
source: https://www.youtube.com/watch?v=RmobQRYxu0g&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=46
author: IIT Roorkee
lecture: 44
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Numerical optimization problem

In general, our analytical approach may not work for all types of optimization problems. So, we move to search techniques

# Basic scheme

A common basic scheme is of the form
$x_{k+1}=x_{k}+\alpha_{k}d_{k}$
where xk is the current solution, dk is the direction of movement from xk and alphak > 0 is the step size.
finding alpha and d

for minimization type problem we have a descent property and for maximization type problem we have ascent property

## Descent property

An algo for solving P is said to have a descent property if f(x\_k+1) < f(x\_k) for all k. That is, as we proceed, the value of objective function decrease.

## Order of convergence

Lett a sequence $\{ x_{k} \}$ converge to a point $\bar{x}$ and let $x_{k}\neq \bar{x}$ for sufficiently large k. The quantity $||x_{k}-\bar{x}||$ is called the error of the $k^{th}$ iteration. Suppose there exists p and 0 < $\alpha$ < $\infty$ such that
$\lim_{ k \to \infty } \frac{||x_{k+1}-\bar{x}||}{||x_{k}-\bar{x}||^{p}}=\alpha$
then p is called the order of convergence of the sequence $\{ x_{k} \}$

- for p = 1, we say sequence is linearly convergent
- for p = 2, we say sequence is quadratic convergent
- Larger the value of p, faster the algo will converge

# Unimodal function

the function $f:[a,b]\to R$ is said to be a unimodal function if it has only one peak in the given interval $[a,b]$.
Consider a unimodal min function f, then there exists $a\leq x\leq b$ such that,

- f is strictly decreasing in $[a,x)$
- f is strictly increasing in $[x,b]$

Let there be two disc tint point of experiments $x_{1},x_{2}$ s.t. $x_{1}<x_{2}$ then we reduce the search space using three possible conditions:

- $f(x_{1}) < f(x_{2}) \implies x_{min}\epsilon[a,x_{2}]$
- $f(x_{1})>f(x_{2})\implies x_{min}\epsilon[x_{1},b]$
- $f(x_{1})=f(x_{2})\implies s_{min}\epsilon[x_{1},x_{2}]$

Similarly we can define for an unimodal max function

## Measure of effectiveness

The measure of effectiveness of any search technique, $\alpha$ is defined as
$\alpha=\frac{L_{n}}{L_{0}}$
where, $L_{n}$ is the width of interval of uncertainty after n-experiments and $L_{0}$ is the initial width of uncertainty

# Steepest Descent Method for UOP

consider a UOP
$min_{x\epsilon \mathbb{R}^{n}}f(x)$
where f has continuous first order partial derivatives in $\mathbb{R}^{n}$
Choose the starting point as $X_{1}$ and move towards the optimal point according to the following rule:
$X_{k+1}=X_{k}+\alpha_{k}d_{k}$
where $d_{k}=-\nabla f(X_{k})$ and $\alpha_{k}$ is the optimal step size which can be obatined using the equation
$min_{\alpha}f(X_{k}+\alpha_{k}d_{k}) \implies \frac{df(\alpha)}{d\alpha}=0$
Stopping point: $||\nabla f(X_{k})|| < \epsilon$ or $||f(X_{k+1})-f(X_{k})|| < \epsilon'$ where $\epsilon$ is tolerence level
**Properties**

- is globally convergent
- has order of convergence unity
- has descent property

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                         | April 18, 2025 |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]     | April 18, 2025 |

tab: Previous Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]             | April 17, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]               | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]               | April 16, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=RmobQRYxu0g\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=46)
