---
publish: true
title: "Deep Learning(CS7015): Lec 3.1 Sigmoid Neuron"
description: lec03mod01
created: 2025-04-21
modified: 2026-10-15T16:16:14.559Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/X4RmokyD3U8/maxresdefault.jpg
source: https://www.youtube.com/watch?v=X4RmokyD3U8&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=19
author: IIT Roorkee
cover: https://i.ytimg.com/vi/X4RmokyD3U8/maxresdefault.jpg
lecture: 3.1
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Network which can mimic any arbitrary Function

till now we have studied about boolean functions but to represent any arbitrary function we need to first know about sigmoid neurons

# Functions

**Boolean Functions**
$f:\{ 0,1 \}^{n}\to \{ 0,1 \}$

**General Functions**
$f:\mathbb{R}^{n}\to \mathbb{R}$

# Sigmoid Neurons

![[System/Assets/Pasted image 20250421145007.png]]
The threshold logic used by percept very harsh as for w+0.01 and w-0.01 the result is different given by the perceptron
This logic is not smooth, not continuous, not diffferentialbe
So to encounter this we introduced Sigmoid neurons
one form of the sigmoid function called the logistic function is given as
$y=\frac{1}{1+e^{-w^{T}x}}$
Result off sigmoid function between 0 and 1 and can be directly related to probability
This logic is not smooth, not continuous, not diffferentialbe
![[System/Assets/Pasted image 20250421145427.png]]

**Representation**
![[System/Assets/Pasted image 20250421145500.png]]

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]                                                 | April 21, 2025 |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]                                                 | April 21, 2025 |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                                                               | April 21, 2025 |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |

tab: Previous Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]]           | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                                   | April 19, 2025 |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |
| [[Resources/Perceptron Learning Algorithm.md\|Perceptron Learning Algorithm]]                                                 | April 19, 2025 |
| [[Resources/Perceptrons.md\|Perceptrons]]                                                                                     | April 19, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=X4RmokyD3U8\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=19)
