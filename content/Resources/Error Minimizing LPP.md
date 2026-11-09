---
publish: true
title: "Lecture 55: Error Minimizing LPP"
description: This lecture explains the formulation of Error minimizing LPP for binary class patterns which helps in predicting whether or not the two sets are linearly separable.
created: 2025-04-19
modified: 2026-10-15T16:16:14.554Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=JJTvVYK8v9A&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=57
author: IIT Roorkee
lecture: 55
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Error Minimizing LPP

The inequalities $A^{+}w>eb$ and $A^{-}w<eb$ by suitable scaling can be rewritten as:
$A^{+}w \geq eb+e$ $A^{-}w\leq eb-e$
Let $a_{+}=max\{ a,0 \}$. For $x\epsilon \mathbb{R}^{n}, x_{+}=((x_{+})_{1},\dots,(x_{+})_{n})^{T}$ and let $||x||_{1}$ denote $L_{1}$ norm of $x\epsilon \mathbb{R}^{n}$, that is
$||x_{1}||=\sum_{i=1}^{n}|x_{i}|$
Now consider following optimization problem
$(P)min_{(w,b)} \frac{1}{m_{1}}||(-A^{+}w+eb+e)_{+}||_{1}+ \frac{1}{m_{2}}||(A^{-}w-eb+e)_{+}||_{1}$
If $A^{+}$ and $A^{-}$ are linearly separable, then the error is zero and hence the optimal value of P is zero. The converse of the statement is also true.
Hence, this optimisation model helps in predicting whether the sets $A^{+}$ and $A^{-}$ are linearly separable
P is NLLP problem we need to model it in a LPP problem
$y = (-A^{+}w+eb+e)_{+} = max\{ -A^{+}w+eb+e,0 \}\implies y \geq 0, y\geq-A^{+}w+eb+e$
$z = (-A^{-}w-eb+e)_{+} = max\{ -A^{-}w-eb+e,0 \}\implies z \geq 0, z\geq-A^{-}w-eb+e$
P changes to,
$min_{w,b} \frac{1}{m_{1}}\sum_{i=1}^{m_{1}}|y_{i}|+ \frac{1}{m_{2}}\sum_{j=1}^{m_{2}}|z_{j}|=min_{w,b} \frac{1}{m_{1}}\sum_{i=1}^{m_{1}}y_{i}+ \frac{1}{m_{2}}\sum_{j=1}^{m_{2}}z_{j} = min_{w,b} \frac{1}{m_{1}}y^{T}e + \frac{1}{m_{2}}z^{T}e$
finally,
$min_{(w,b,x,y)} \frac{e^{T}y}{m_{1}} + \frac{e^{T}z}{m_{2}}, \text{ s.t. } A^{+}w-eb+y\geq e, -A^{-}w+eb+z\geq e, y\geq0, z\geq 0, w \text{ and } b \text{ are unrestricted}$

# Definitions

## Margin

For the plane $w^{T}x=b$, the distance between these two bounding planes $w^{T}x=b-1$ and $w^{T}x=b+1$ is called the _margin_ and is given as
$margin_{p_{w}} = \frac{2}{||w||}$

## Canonical Separating Hyperplane

Let $A^{+},A^{-}\subset \mathbb{R}^{n}$ be linearly separable. Then a separatiing hyperplane $w^{T}x=b$ is called _canonical separating hyperplane_ if it satisfies $A^{+}w\geq eb+e$ and $A^{-}w\leq eb-e$

## Optimal separating Hyperplane

A Canonical Separating Hyperplane is called optimal separating hyper plane if its margin is the maximum amongst all canonical separating hyperplanes
$(P)max_{w} \frac{2}{||w||} \text{ or } min_{w} \frac{||w||}{2}$

---

# Related

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

![](https://www.youtube.com/watch?v=JJTvVYK8v9A\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=57)
