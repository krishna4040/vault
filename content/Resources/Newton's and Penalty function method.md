---
publish: true
title: "Lecture 45: Newton's and Penalty function method"
description: "In this lecture, we discuss two more numerical optimization algorithms: Newton's method for unconstrained optimization and penalty function method for constrained optimization probems"
created: 2025-04-17
modified: 2026-10-15T16:16:14.557Z
published: 2021-08-24
tags:
  - resource
  - maths
  - optimization
  - AI
  - ML
source: https://www.youtube.com/watch?v=91wC1AuJr1M&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=47
author: IIT Roorkee
lecture: 45
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Newton’s method

**Basic Scheme**
Newton’s method is an iterative method used for finding real roots of the equation $g(y)=0$, $y\epsilon \mathbb{R}$. The iterative formula for finding roots is given as
$y_{k+1}=y_{k}-\frac{g(y_{k})}{g'(y_{k})}$
where $y_{k}$ is the current iteratre or the current approximation

**UOP**
Consider the following UOP
$min_{x\epsilon \mathbb{R}^{n}}f(x)$
where $f:\mathbb{R}^{n}\to R$ is a differentiable function. For solving problem, we have to find $\bar{x}\epsilon \mathbb{R}^{n}$ such that $\nabla f(\bar{x})=0$ so, the Newton scheme we have,
$x_{k+1}=x_{k}-(H_{f}(x_{k}))^{-1}\nabla f(x_{k})$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                         | April 18, 2025 |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]     | April 18, 2025 |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]] | April 18, 2025 |

tab: Previous Lectures
| File                                                                        | created        |
| --------------------------------------------------------------------------- | -------------- |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]           | April 17, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]   | April 17, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]     | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]     | April 16, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]] | April 16, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=91wC1AuJr1M\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=47)
