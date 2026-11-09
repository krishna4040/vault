---
publish: true
title: "Deep Learning(CS7015): Lec 3.5 Representation Power of Multilayer Network of Sigmoid Neurons"
description: lec03mod05
created: 2025-04-21
modified: 2026-10-15T16:16:14.558Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/d1K-6b5guh0/maxresdefault.jpg
source: https://www.youtube.com/watch?v=d1K-6b5guh0
author: IIT Roorkee
cover: https://i.ytimg.com/vi/d1K-6b5guh0/maxresdefault.jpg
lecture: 3.5
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Representation power of perceptrons and sigmoid neurons

**Perceptron**
A MLN with a single hidden layer can be used to represent any boolean function precisely (no errors)

**Sigmoid Neurons**
A MLN with a single hidden layer can be used to approximate any continuous function to any desired precision
In other words for any function $f:\mathbb{R}^{n}\to \mathbb{R}^{m}$ we can find a neural network whose output is $g(x)$ satisfies $|g(x)-f(x)|<\epsilon$ where $\epsilon$ is tolerance level
Refer [[Steepest Descent method]] for solving optimization problems
![[System/Assets/Pasted image 20250421185843.png]]
This is an arbitrary continuous function which is to be approximated, this can be done by several _tower functions_
More the number of such towers better the approximation

**Tower Functions**
All the tower functions are same the only difference is they are shifted on x axis and they are scaled
![[System/Assets/Pasted image 20250421190135.png]]
The tower maker functions is defined using logisctic functions as
$f(w,b)=\frac{1}{1+e^{-(wx+b)}}$
as w increases the function becomes sharper and when b increases it will keep shifting in x-axis
suppose $w'>w$ and $b'>b$ then $f(w',b')-f(w,b)$ is given as
![[System/Assets/Pasted image 20250421191433.png]]
![[System/Assets/Pasted image 20250421191530.png]]

# Tower functions in case two inputs

![[System/Assets/Pasted image 20250421192118.png]]

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]]                                                                 | April 22, 2025 |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                                                                                 | April 23, 2025 |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]]                                                                 | April 23, 2025 |

tab: Previous Lectures
| File                                                                                                                | created        |
| ------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                         | April 21, 2025 |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]           | April 21, 2025 |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]           | April 21, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                     | April 21, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]] | April 19, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=d1K-6b5guh0)
