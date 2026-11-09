---
publish: true
title: "Deep Learning(CS7015): Lec 2.5 Perceptron Learning Algorithm"
description: lec02mod05
created: 2025-04-19
modified: 2026-10-15T16:16:14.557Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
source: https://www.youtube.com/watch?v=VRcixOuG-TU
author: IIT Roorkee
lecture: 2.5
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# PLA

$$
\begin{aligned}
& P \leftarrow \textit{inputs with label } 1; \\
& N \leftarrow \textit{inputs with label } 0; \\
& \text{Initialize } \mathbf{w} = [w_1, w_2, \ldots, w_N] \text{ randomly}; \\
& \textbf{while } \neg \text{convergence do} \\
& \quad \text{Pick random } \mathbf{x} \in P \cup N; \\
& \quad \textbf{if } \mathbf{x} \in P \text{ and } \sum_{i=0}^{n} w_i \cdot x_i < 0 \text{ then} \\
& \quad\quad \mathbf{w} = \mathbf{w} + \mathbf{x}; \\
& \quad \textbf{end} \\
& \quad \textbf{if } \mathbf{x} \in N \text{ and } \sum_{i=0}^{n} w_i \cdot x_i \geq 0 \text{ then} \\
& \quad\quad \mathbf{w} = \mathbf{w} - \mathbf{x}; \\
& \quad \textbf{end} \\
& \textbf{end}
\end{aligned}
$$

Consider two vector $w=(w_{0},w_{1},\dots,w_{n})$ and $x=(x_{0},x_{1},\dots,x_{n})$ we have,
$w^{T}x=\sum_{i=0}^{n}w_{i}.x_{i}$
We can thus rewrite the perceptron rule as

$$$y=\begin{cases}
1 \text{ if } w^{T}x\geq 0 \\
0 \text{ if } w^{T}x < 0
\end{cases}$$
**Interpreting PLA**
![[System/Assets/Pasted image 20250419024547.png]]
- The angle between w and x is 90
- The angle between w and positive output points is less then 90
- The angle between w and negetive output points is greater than 90
---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                          | created        |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Proof of Convergence of Perceptron Learning Algorithm.md\|Proof of Convergence of Perceptron Learning Algorithm]] | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                                   | April 19, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]]           | April 19, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                               | April 21, 2025 |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]                     | April 21, 2025 |

tab: Previous Lectures
| File                                                                                                    | created        |
| ------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Perceptrons.md\|Perceptrons]]                                                               | April 19, 2025 |
| [[Resources/McCulloch Pitts Neuron, Thresholding Logic.md\|McCulloch Pitts Neuron, Thresholding Logic]] | April 19, 2025 |
| [[Resources/History Of DL.md\|History Of DL]]                                                           | April 15, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=VRcixOuG-TU)
$$$
