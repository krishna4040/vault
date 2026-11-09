---
publish: true
title: "Deep Learning(CS7015): Lec 4.1 Feedforward Neural Networks (a.k.a multilayered network of neurons)"
description: lec04mod01
created: 2025-04-22
modified: 2026-10-15T16:16:14.554Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/AASR9rOzhhA/maxresdefault.jpg
source: https://www.youtube.com/watch?v=AASR9rOzhhA&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=24&t=446s
author: IIT Roorkee
cover: https://i.ytimg.com/vi/AASR9rOzhhA/maxresdefault.jpg
lecture: 4.1
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# FNN

![[System/Assets/Pasted image 20250422025718.png]]

- The input to the network is an n dimensional vector
- The network contains L-1 hidden layers having n neurons each
- Finally, there is one outpyt layer containing k neurons
- Each neuron in the hidden layer and output layer can be split into two parts → pre-activation and activation
- The input layer can be called 0th layer and the output layer can be called the L th layer
- $W_{i}\epsilon \mathbb{R}^{n\times n}$ and $b_{i}\epsilon \mathbb{R}^{n}$ are the weight and bias between layers i-1 and i, we need n weights to connect n inputs/ neurons of previous layer to n neurons of next layer so $W_{i}$ is $n\times n$ matrix and there is one bias corrosponding to each neuron at each level
- $W_{L}\epsilon \mathbb{R}^{n\times k}$ and $b_{L}\epsilon \mathbb{R}^{k}$ are the weight and bias between the last hidden layer and the output layer
- The pre-activation and activation at layer $i$ is given by
  $[a_{i}]_{n\times 1}=[b_{i}]_{n\times 1}+[W_{i}]_{n\times n}[h_{i-1}]_{n\times1}$
  $[h_{i}]_{n\times 1}=g([a_{i}]_{n\times 1})$
  where g is called the activation function
- The output at layer i is given by
  $f(x)=[h_{L}]_{k\times1}=O([a_{L}]_{k\times 1})$
  where O is the output activation function

**The ML setup for FNN**
Data → $\{ x_{i}, y_{i} \}^{N}_{i=1}$
Model → $\hat{y}_{i}=f(x_{i})=O(W^{3}g(W^{2}g(W^{-1}x+b_{1})+b_{2})+b_{3})$
Parameters → $\theta=W_{1},\dots,W_{L},b_{1},\dots,b_{L}, (L=3)$
Algorithm → GD with backpropogation
Loss function → $\mathcal{L}(\theta)= min \frac{1}{N}\sum_{i=1}^{N}(\hat{y}_{i}-y_{i})^{2}$

$a_{i}^{l}=w_{ji}.x_{j}+b_{i}$

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                                          | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]] | April 22, 2025 |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]]                                                     | April 22, 2025 |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                                                                     | April 23, 2025 |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]]                                                     | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                                                                     | April 23, 2025 |

tab: Previous Lectures
| File                                                                                                                                          | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]] | April 21, 2025 |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                                                   | April 21, 2025 |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]                                     | April 21, 2025 |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]                                     | April 21, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                                               | April 21, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=AASR9rOzhhA\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=24\&t=446s)
