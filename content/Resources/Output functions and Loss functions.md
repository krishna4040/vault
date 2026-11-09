---
publish: true
title: "Deep Learning(CS7015): Lec 4.3 Output functions and Loss functions"
description: lec04mod03
created: 2025-04-22
modified: 2026-10-15T16:16:14.557Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/hMkRDNzH9vs/maxresdefault.jpg
source: https://www.youtube.com/watch?v=hMkRDNzH9vs&t=387s
author: IIT Roorkee
cover: https://i.ytimg.com/vi/hMkRDNzH9vs/maxresdefault.jpg
lecture: 4.3
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Output Function and Loss Functions

The choice of loss function depends on the problem at hand

## Regression problem

![[System/Assets/Pasted image 20250422184507.png]]
Let suppose $f:\mathbb{R}^{n}\to \mathbb{R}^{3}$ s.t. $y=f(x)$ then the objective or the loss function is given as
$\mathcal{L}(\theta)=\frac{1}{N}\sum_{i=1}^{N}\sum_{j=1}^{3}(\hat{y}_{ij}-y_{ij})^{2}$
The output function O cannot be a logistic function as it limits $\hat{y}$ to 0 & 1, but suppose if we want $\hat{y}\epsilon \mathbb{R}$ so in such cases it makes sense to have O as linear function
$f(x)=h_{L}=O(a_{L})=W_{0}a_{L}+b_{0}$

## Classification ouput functions

### Information and Probability

The leass the prob of an event the more information we have about the event
$I(A)=-\log_{2}P(A)$
Entropy is defiend as the Expectation of Probability w.r.t information available corrosponding to the event. Entropy is given as
$E=\sum P_{i}I_{i}=-\sum P_{i}\log_{2}P_{i}$
It is the measure of how close the predicted distribution to the original distribution. The less the entropy the more accurate the predicted distribution
![[System/Assets/Pasted image 20250422190225.png]]
here output is a probability distributioin and to ensure $\hat{y}$ is also a PD the choice of output function can be a softmax function
$[a_{L}]_{k\times 1}=[W_{L}]_{k\times n}[h_{L-1}]_{n\times 1}+[b_{L}]_{k \times 1}$
$[\hat{y}]_{k\times1}=O([a_{L}]_{k\times 1})=[\frac{e^{a_{Li}}}{\sum_{j=1}^{k}e^{a_{Lj}}}]_{k\times1}$

> [!note]
> **SoftMax Function**
> $softmax: \mathbb{R}^{k}\to \Delta^{k-1} \text{ s.t. } softmax(z_{i})=\frac{e^{z_{i}}}{\sum_{j}^{k}e^{z_{jj}}}$
> where $\Delta_{k-1}$ is probability simplex and is defined as $\left\{  p\epsilon \mathbb{R}^{k}|\sum p_{i}=1, p_{i}>0  \right\}$

The objective functions for two PDs for k classification is given as,
$\mathcal{L}(\theta)=-\sum_{c=1}^{k}y_{c}\log \hat{y_{c}}$
for binary classification we have

$$$y_{c}=\begin{cases}
1 \text{ c = l (the true class label)} \\
0 \text{ otherwise}
\end{cases} \implies \mathcal{L}(\theta)=-\log \hat{y_{l}}$$
so for classification problems we use the objective function
$$min_{\theta}\mathcal{L}(\theta)=-\log \hat{y_{l}} \text{ or } max_{\theta}-\mathcal{L}(\theta)=\log \hat{y_{i}}$$
where $\hat{y}$ is a function of $\theta=[W_{1}\dots,W_{L},b_{1},\dots,b_{L}]$ and $\hat{y_{l}}=[O(W^{3}g(W^{2}g(W^{-1}x+b_{1})+b_{2})+b_{3})]_{l}$ and is known as log-likelhihood of the data
# Summary
![[System/Assets/Pasted image 20250422191728.png]]

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                      | created        |
| ----------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                 | April 23, 2025 |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]] | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                 | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                             | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]         | April 23, 2025 |

tab: Previous Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |
| [[Resources/Learning Parameters Gradient Descent.md\|Learning Parameters Gradient Descent]]                                                               | April 21, 2025 |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]                                                 | April 21, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=hMkRDNzH9vs&t=387s)
$$$
