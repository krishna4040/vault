---
publish: true
title: "Deep Learning(CS7015): Lec 2.6 Proof of Convergence of Perceptron Learning Algorithm"
description: lec02mod06
created: 2025-04-19
modified: 2026-10-15T16:16:14.558Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
source: https://www.youtube.com/watch?v=vAOI9kTDVoo
author: IIT Roorkee
lecture: 2.6
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Theorem

Two sets P and N of points in an n-dimensional space are called absolutely linearly separable if n+1 real number $w_{0},w_{1},\dots,w_{n}$ exist such that every point $(x_{1},x_{2},\dots,x_{n})\epsilon P$ satisfies $\sum_{i=1}^{n}w_{i}.x_{i}>w_{0}$ and every point $(x_{1},x_{2},\dots,x_{n})\epsilon N$ satisfies $\sum_{i=1}^{n}w_{i}.x_{i}< w_{0}$

# Proposition

If the sets P and N are finite and linearly separable, the PLA updates the weight vector $w^{T}$ a finite number of times.

# Proof

if $x\epsilon N$ then $-x\epsilon P$ thus we consider a single set $P'=P\cup N^{-}$ and for every element $p\epsilon P$ ensure that $w^{T}p\geq 0$
The PAL can be written as,
![[System/Assets/Pasted image 20250419025847.png]]
let $w^{*}$ be the normalized solution vector then,
Suppose at time stamp t we inspected the point $p_{i}$ and found that $w^{T}.p_{i}\leq 0$ we make a correction $w_{t+1}=w_{t}+p_{i}$. Let $\beta$ be the angle between $w^{*}$ and $w_{t+1}$ hence
$\cos\beta=\frac{w^{*}.w_{t+1}}{||w_{t+1}||}$
$Nr = w^{*}.w_{t+1}=w^{*}.(w_{t}+p_{i})=w^{*}.w_{t}+w^{*}.p_{i}=\dots= w^{*}w_{0}+k\delta, \delta=min(w^{*}.p_{i}) \forall i$
$Dr^{2}=||w_{t+1}||^{2}=(w_{t}+p_{i}).(w_{t}+p_{i})=||w_{t}||^{2}+||p_{i}||^{2}+2w_{i}p_{i}=||w_{t}||^{2}+1=\dots=||w_{0}||^{2}+k, (||p_{i}||^{2}=1)$
$\cos\beta\geq \frac{w^{*}.w_{0}+k\delta}{\sqrt{ ||w_{0}||^{2}+k }} \implies \cos\beta \propto \sqrt{ k }$
But since $\cos\beta \leq 1$, k must be bounded by a max number, Thus there can only be a finite number of corrections(k) to w and the algorithm will converge

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                | created        |
| ------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                         | April 19, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]] | April 19, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                     | April 21, 2025 |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]           | April 21, 2025 |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]           | April 21, 2025 |

tab: Previous Lectures
| File                                                                                                    | created        |
| ------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Perceptron Learning Algorithm.md\|Perceptron Learning Algorithm]]                           | April 19, 2025 |
| [[Resources/Perceptrons.md\|Perceptrons]]                                                               | April 19, 2025 |
| [[Resources/McCulloch Pitts Neuron, Thresholding Logic.md\|McCulloch Pitts Neuron, Thresholding Logic]] | April 19, 2025 |
| [[Resources/History Of DL.md\|History Of DL]]                                                           | April 15, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=vAOI9kTDVoo)
