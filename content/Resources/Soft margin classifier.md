---
publish: true
title: "Lecture 58: Soft margin classifier"
description: This lecture explains the formulation of the soft margin classifier problem and it's dual for non-linearly separable binary class patterns.
created: 2025-04-21
modified: 2026-10-15T16:16:14.559Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=Q3YrpjX3EmU&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=60
author: IIT Roorkee
lecture: 58
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Soft Margin Classifier

Let $\{ x_{i}\epsilon \mathbb{R}^{n}, i=1,2,\dots,m \}$ be set of finite patterns which is linearly separable having class of label +1 and -1. $d_{i}\epsilon \{ -1, +1 \}$ = target value of $i^{th}$ data.
Let these patterns be not linearly separable then error minimizing LPP will not have zero objective value. That is, in the optimal solution of minimizing LPP, all error variables are not zero
Let these error variables be denoted by $\xi_{i} (i=1,2,\dots,m)$
Now, we have to find a classifier $w^{T}x=b$, for which the total error $\sum_{i=1}^{m}\xi_{i}$ is least & $\frac{2}{||w||}$ is maximum
Therefore the optimization problem becomes,
$(SP) \space min_{w,b,\xi} \frac{1}{2}w^{T}w+c\sum_{i=1}^{m}\xi_{i} \text{ s/t } d_{i}(w^{T}x_{i}-b)+\xi_{i}\geq 1, \xi_{i}\geq 0$
The lagragian of the function is given as
$L(w,b,\alpha)=\frac{1}{2}w^{T}w+c\sum \xi_{i}+\sum_{i}\alpha_{i}(1-d_{i}(w^{T}x_{i}-b)-\xi_{i})-\sum_{i}\beta_{i}\xi_{i}$

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

![](https://www.youtube.com/watch?v=Q3YrpjX3EmU\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=60)
