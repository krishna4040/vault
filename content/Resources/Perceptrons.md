---
publish: true
title: "Deep Learning(CS7015): Lec 2.3 Perceptrons"
description: lec02mod03
created: 2025-04-19
modified: 2026-10-15T16:16:14.557Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
source: https://www.youtube.com/watch?v=XKnBn1XZpQI
author: IIT Roorkee
lecture: 2.3
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Perceptron

![[System/Assets/Pasted image 20250419021913.png]]

- more general computational model than MPN
- introduction to wigths and mechanism for learning these weigths
- inputs not longer related to boolean weights

$$$y=\begin{cases}
1 \text{ if } \sum_{i=1}^{n}w_{i}*x_{i} \geq\theta \\
0 \text{ if } \sum_{i=1}^{n}w_{i}*x_{i} < \theta
\end{cases}$$
alternatively,
![[System/Assets/Pasted image 20250419022231.png]]
$$y=\begin{cases}
1 \text{ if } \sum_{i=0}^{n}w_{i}*x_{i} \geq0 \\
0 \text{ if } \sum_{i=0}^{n}w_{i}*x_{i}\leq0
\end{cases}$$

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Perceptron Learning Algorithm.md\|Perceptron Learning Algorithm]]                                                 | April 19, 2025 |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                                   | April 19, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]]           | April 19, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                               | April 21, 2025 |

tab: Previous Lectures
| File                                                                                                    | created        |
| ------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/McCulloch Pitts Neuron, Thresholding Logic.md\|McCulloch Pitts Neuron, Thresholding Logic]] | April 19, 2025 |
| [[Resources/History Of DL.md\|History Of DL]]                                                           | April 15, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=XKnBn1XZpQI)
$$$
