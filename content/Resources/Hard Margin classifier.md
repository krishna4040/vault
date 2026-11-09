---
publish: true
title: "Lecture 57: Hard Margin classifier"
description: This lecture explains the formulation of the hard margin classifier problem and its dual, optimal solution of which gives the hard margin classifier for linearly separable binary class patterns.
created: 2025-04-21
modified: 2026-10-15T16:16:14.555Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=2W1BEPWl72k&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=58
author: IIT Roorkee
lecture: 57
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Hard Margin Classifier

Let $\{ x_{i}\epsilon \mathbb{R}^{n}, i=1,2,\dots,m \}$ be set of finite patterns which is linearly separable having class of label +1 and -1. $d_{i}\epsilon \{ -1, +1 \}$ = target value of $i^{th}$ data.
Therefore, there exists $w\epsilon \mathbb{R}^{n}$ and $b\epsilon \mathbb{R}$ such that

```mermaid
flowchart TD
subgraph AB["Hyperplane equations for linearly seprable points"]
a["$$w^{T}x_{i}-b>0,\forall i \text{ having } d_{i}=+1$$"]
b["$$-w^{T}x_{i}+b>0, \forall i \text{ having } d_{i}=-1$$"]
end
subgraph CD["After suitable scaling"]
c["$$w^{T}x_{i}-b>=+1, \forall i \text{ having } d_{i}=+1$$"]
d["$$-w^{T}x_{i}+b>=-1, \forall i \text{ having } d_{i}=-1$$"]
end
e["$$d_{i}(w^{T}x_{i}-b>=1), \forall i=1,2,\dots,m$$"]
AB --> CD --> e
```

- Among all the separable hyperplane we choose the hyperplane $w^{T}x=b$ for which the margin $\frac{2}{||w||}$ is maximum or $\frac{||w||^{2}}{2}$ is minimum
- To find the maximum margin classifier, the optimization problem can be modelled as
  $(P_{1}) \space min_{w,b} \frac{1}{2}w^{T}w \text{ s/t } d_{i}(w^{T}x_{i}-b)\geq 1, i=1,2,\dots,m$
- This is a **CPP** with m constraints
- using Lagrangian duality to solve the above equation we reduce the number of constraints
  $L(w,b,\alpha_{i})=\frac{1}{2}w^{T}w+\sum_{i=1}^{m}\alpha_{i}(1-d_{i}(w^{T}x_{i}-b))=\frac{-1}{2}\sum_{i=1}^{m}\sum_{j=1}^{m}\alpha_{i}\alpha_{j}d_{i}d_{j}x_{i}^{T}x_{j}$
  KKT conditions and feasibility conditions for P1 are given as,
  $\nabla_{w}L=0\implies w=\sum_{i=1}^{m}\alpha_{i}d_{i}x_{i} \text{ and } \frac{\delta L}{\delta b}=0 \implies \sum_{i=1}^{m}\alpha_{i}d_{i}=0\text{ and }\alpha_{i}\geq 0 \text{ and }d_{i}(w^{T}x_{i}-b)\geq 1\implies\alpha_{i}[1-d_{i}(w^{T}x_{i}-b)]=0$
  Dual is given as,
  $(P_{2}) \space min_{w,b}L(w,b,\alpha) \text{ s/t KKT conditions of P1}$

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

![](https://www.youtube.com/watch?v=2W1BEPWl72k\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=58)
