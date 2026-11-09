---
publish: true
title: "Deep Learning(CS7015): Lec 3.2 A typical Supervised Machine Learning Setup"
description: lec03mod02
created: 2025-04-21
modified: 2026-10-15T16:16:14.551Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/uDcU3ZzH7hs/maxresdefault.jpg
source: https://www.youtube.com/watch?v=uDcU3ZzH7hs&list=PLyqSpQzTE6M9gCgajvQbc68Hk_JKGBAYT&index=20
author: IIT Roorkee
cover: https://i.ytimg.com/vi/uDcU3ZzH7hs/maxresdefault.jpg
lecture: 3.2
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# ML Setup

**Data** → $\{ x_{i}, y_{i} \}_{i=1}^{n}$  or $f:\mathbb{R}^{n}\to \mathbb{R} \text{ s.t. } y=f(x)$

In real world this functions can be governed by physical laws, biological laws, economic laws, and we are unaware about this function so we make some assumptions

**Assumptions** → $y=\hat{f}(x,w)$
**Model** → Our approximation of the relation between x and y
**Parameters** → w is called the parameter which needs to be learned from data
**Learning Algorithm** → An algo for learning the parameters of the model (PAL, GD)
**Objective/Loss/Error Function** → To guide the learning algorithm

# Example

This is an illustration weather we like a movie or not

- Data → $\{ x_{i}=movie, y_{i}=\text{like/dislike} \}_{i-1}^{n}$
- Model → $\hat{y}=\frac{1}{1+e^{-w^{T}x}}$
- parameter → w
- Learning algorithm → Gradient Descent
- Objective function → $\mathcal{L}(w)=\sum_{i=1}^{n}(\hat{y}_{i}-y_{i})^{2}$

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]                                                 | April 21, 2025 |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                                                               | April 21, 2025 |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |

tab: Previous Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                               | April 21, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]]           | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                                   | April 19, 2025 |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |
| [[Resources/Perceptron Learning Algorithm.md\|Perceptron Learning Algorithm]]                                                 | April 19, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=uDcU3ZzH7hs\&list=PLyqSpQzTE6M9gCgajvQbc68Hk_JKGBAYT\&index=20)
