---
publish: true
title: "Deep Learning(CS7015): Lec 3.3 Learning Parameters: (Infeasible) guess work"
description: lec03mod03
created: 2025-04-21
modified: 2026-10-15T16:16:14.556Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/HnaBcIL2shc/maxresdefault.jpg
source: https://www.youtube.com/watch?v=HnaBcIL2shc&list=PLyqSpQzTE6M9gCgajvQbc68Hk_JKGBAYT&index=22
author: IIT Roorkee
cover: https://i.ytimg.com/vi/HnaBcIL2shc/maxresdefault.jpg
lecture: 3.3
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Learning Parameters with guess work

Lets consider a simple model $f:\mathbb{R}\to \mathbb{R}, \hat{y}=f(x)=\frac{1}{1+e^{-(wx+b)}}$
![[System/Assets/Pasted image 20250421152335.png]]

- Data → $\{ x_{i},y_{i} \}_{i=1}^{n} \implies \text{n pairs of }(x,y)$
- Objective function → $min_{w,b} \mathcal{L}(w,b)=\sum_{i=1}^{n}(y_{i}-\hat{y}_{i})^{2}$

# Guessing parameters for learning

![[System/Assets/Pasted image 20250421152936.png]]
![[System/Assets/Pasted image 20250421153420.png]]

# Optimizing our guess work

Lets set our range of w where we will guess and plot the error or objective function
![[System/Assets/Pasted image 20250421153252.png]]

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                                                               | April 21, 2025 |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]]                                                                 | April 22, 2025 |

tab: Previous Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]                     | April 21, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                               | April 21, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]]           | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                                   | April 19, 2025 |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=HnaBcIL2shc\&list=PLyqSpQzTE6M9gCgajvQbc68Hk_JKGBAYT\&index=22)
