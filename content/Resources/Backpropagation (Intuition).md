---
publish: true
title: "Deep Learning(CS7015): Lec 4.4 Backpropagation (Intuition)"
description: lec04mod04
created: 2025-04-23
modified: 2026-10-15T16:16:14.551Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/DSqgn2lAN1M/maxresdefault.jpg
source: https://www.youtube.com/watch?v=DSqgn2lAN1M&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=27
author: IIT Roorkee
cover: https://i.ytimg.com/vi/DSqgn2lAN1M/maxresdefault.jpg
lecture: 4.4
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

Refer to [[Learning Paramters of Feedforward Neural Networks (Intuition)]] for sigmoid functions

# Backpropagation

![[System/Assets/Pasted image 20250423020934.png]]
The loss function is given as
$\mathcal{L}(\theta)=-\log \hat{y_{L}}$ In this case,
$\frac{\delta \mathcal{L}(\theta)}{\delta W_{111}}=\frac{\delta \mathcal{L}(\theta)}{\delta \hat{y}} \frac{\delta \hat{y}}{\delta a_{L11}} \frac{\delta a_{L11}}{\delta h_{21}} \frac{\delta h_{21}}{\delta a_{21}} \frac{\delta a_{21}}{\delta h_{11}} \frac{\delta h_{11}}{\delta a_{11}} \frac{\delta a_{11}}{\delta W_{111}}$
![[System/Assets/Pasted image 20250423022145.png]]
roadmap:

- Gradient w.r.t ouput units
- Gradient w.r.t. hidden units
- Gradient w.r.t. weights and biasis

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                    | created        |
| ------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]]               | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                               | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                                           | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]                       | April 23, 2025 |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]] | April 23, 2025 |

tab: Previous Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]]                                                                 | April 22, 2025 |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                                                               | April 21, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=DSqgn2lAN1M\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=27)
