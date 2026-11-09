---
publish: true
title: "Deep Learning(CS7015): Lec 2.2 McCulloch Pitts Neuron, Thresholding Logic"
description: lec02mod02
created: 2025-04-19
modified: 2026-10-15T16:16:14.557Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
source: https://www.youtube.com/watch?v=6XhSJbfT1pk
author: IIT Roorkee
lecture: 2.2
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# MCP Neuron

![[System/Assets/Pasted image 20250419020730.png]]
$g(x_{1},x_{2},\dots,x_{n})=g(x)=\sum_{i=1}^{n}x_{i}$

$$$y=fog(x)=\begin{cases}
1 \text{ if } g(x) \geq \theta \\
0 \text{ if } g(x) \leq \theta
\end{cases}$$
$\theta$ is called the threshold parameter and this is called the threshold logic
## MP as logic gates
![[System/Assets/Pasted image 20250419021254.png]]
A single MPN can be used to represent boolean functions which are linearly seprable
Linear seprability: there exists a line/plane/hyperplane such that all inputs which produce a 1 lie on one side on the line/plane/hyperplane and all inputs which produce a 0 lie on other side of line/plane/hyperplane

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Perceptrons.md\|Perceptrons]]                                                                                     | April 19, 2025 |
| [[Resources/Perceptron Learning Algorithm.md\|Perceptron Learning Algorithm]]                                                 | April 19, 2025 |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                                   | April 19, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]]           | April 19, 2025 |

tab: Previous Lectures
| File                                          | created        |
| --------------------------------------------- | -------------- |
| [[Resources/History Of DL.md\|History Of DL]] | April 15, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=6XhSJbfT1pk)
$$$
