---
publish: true
title: "Deep Learning(CS7015): Lec 2.7 Linearly Separable Boolean Functions"
description: lec02mod07.
created: 2025-04-19
modified: 2026-10-15T16:16:14.556Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
source: https://www.youtube.com/watch?v=AjUgxQNZhck&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=17
author: IIT Roorkee
lecture: 2.7
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Linearly Separable

Example of non Linearly Separable function

| $x_{1}$ | $x_{2}$ | XOR |                                       |
| ------- | ------- | --- | ------------------------------------- |
| 0       | 0       | 0   | $w_{0}+\sum_{i=1}^{2}w_{i}x_{i}<0$    |
| 1       | 0       | 1   | $w_{0}+\sum_{i=1}^{2}w_{i}x_{i}\geq0$ |
| 0       | 1       | 1   | $w_{0}+\sum_{i=1}^{2}w_{i}x_{i}\geq0$ |
| 1       | 1       | 0   | $w_{0}+\sum_{i=1}^{2}w_{i}x_{i}<0$    |
![[System/Assets/Pasted image 20250419151020.png]]

Most real world data is not linearly separable and will always contain some outliers
for 2 inputs there exists 16 possible boolean functions out of which two are linearly inseparable Xor and !Xor
![[System/Assets/Pasted image 20250419151520.png]]
For n boolean inputs we have $2^{2^{n}}$ functions of which some are linearly separable and some are linearly inseparable

> [!abstract]
> A boolean function divides a set of points in binary class as set of class 1 points and set of class 0 points

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                | created        |
| ------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]] | April 19, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                     | April 21, 2025 |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]           | April 21, 2025 |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]           | April 21, 2025 |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                         | April 21, 2025 |

tab: Previous Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |
| [[Resources/Perceptron Learning Algorithm.md\|Perceptron Learning Algorithm]]                                                 | April 19, 2025 |
| [[Resources/Perceptrons.md\|Perceptrons]]                                                                                     | April 19, 2025 |
| [[Resources/McCulloch Pitts Neuron, Thresholding Logic.md\|McCulloch Pitts Neuron, Thresholding Logic]]                       | April 19, 2025 |
| [[Resources/History Of DL.md\|History Of DL]]                                                                                 | April 15, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=AjUgxQNZhck\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=17)
