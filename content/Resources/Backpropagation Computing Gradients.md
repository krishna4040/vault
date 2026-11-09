---
publish: true
title: "Deep Learning(CS7015): Lec 4.5 Backpropagation: Computing Gradients w.r.t. the Output Units"
description: lec04mod05
created: 2025-04-23
modified: 2026-10-15T16:16:14.551Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/JSfRBOWp3Es/maxresdefault.jpg
source: https://www.youtube.com/watch?v=JSfRBOWp3Es&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=28
author: IIT Roorkee
cover: https://i.ytimg.com/vi/JSfRBOWp3Es/maxresdefault.jpg
lecture: 4.5
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Gradients

![[System/Assets/Pasted image 20250423022451.png]]

## Gradient w.r.t. OP units

$$$\frac{\delta \mathcal{L}(\theta)}{\delta \hat{y_{i}}}=\frac{\delta(-\log \hat{y_{L}})}{\delta \hat{y_{i}}}=\begin{cases}
-\frac{1}{\hat{y}_{L}} \text{ if i=l} \\
0 \text{ otherwise}
\end{cases}=-\frac{\mathbb{1}_{(i=l)}}{\hat{y_{L}}}$$
$$\nabla_{\hat{y}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta \hat{y_{1}}} \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta \hat{y_{k}}}
\end{bmatrix} = -\frac{1}{\hat{y_{L}}}\begin{bmatrix}
\mathbb{1}_{l=1} \\
\mathbb{1}_{l=2} \\
. \\
. \\
\mathbb{1}_{l=k}
\end{bmatrix}=-\frac{1}{\hat{y_{L}}}e(l)$$
where $e(l)$ is a k dimensional vector whose lth element is 1 and all other elements are 0 basically a dash vector
## Gradient w.r.t top most hidden layer pre activation function
$$\frac{\delta \mathcal{L}(\theta)}{\delta a_{Li}}= -\frac{1}{\hat{y_{l}}} \frac{\delta}{\delta a_{Li}}softmax(a_{L})_{l}=-(\mathbb{1}_{(l=i)}-\hat{y_{i}})$$
$$\nabla_{a_{L}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta a_{L1}} \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta a_{Lk}}
\end{bmatrix}=\begin{bmatrix}
-(\mathbb{1}_{l=1}-\hat{y_{1}}) \\
-(\mathbb{1}_{l=2}-\hat{y_{2}}) \\
. \\
. \\
-(\mathbb{1}_{l=k}-\hat{y_{k}})
\end{bmatrix}=-(e(l)-\hat{y})$$
## Gradient w.r.t hidden layers activation functions
$$\frac{\delta \mathcal{L}(\theta)}{\delta h_{ij}}=\sum_{m=1}^{k} \frac{\delta \mathcal{L}(\theta)}{\delta a_{i+1,m}} \frac{\delta a_{i+1,m}}{\delta h_{ij}}=\sum_{m=1}^{k} \frac{\delta \mathcal{L}(\theta)}{\delta a_{i+1},m} W_{i+1,m,j}$$
$$\nabla_{a_{i+1}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta a_{i+1,1}} \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta a_{i+1,k}}
\end{bmatrix}; W_{i+1,.,j}=\begin{bmatrix}
W_{i+1,1,j} \\
. \\
. \\
W_{i+1,k,j}
\end{bmatrix} \implies (W_{i+1,.,j})^{T}\nabla_{a_{i+1}}\mathcal{L}(\theta)=\sum_{m=1}^{k} \frac{\delta \mathcal{L}(\theta)}{\delta a_{i+1,m}}W_{i+1,m,j}=\frac{\delta \mathcal{L}(\theta)}{\delta h_{ij}}$$
$$\nabla_{h_{i}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta h_{i1}} \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta h_{in}}
\end{bmatrix}=\begin{bmatrix}
(W_{i+1,.,1})^{T}\nabla_{a_{i+1}}\mathcal{L}(\theta) \\
(W_{i+1,.,2})^{T}\nabla_{a_{i+1}}\mathcal{L}(\theta) \\
. \\
. \\
(W_{i+1,.,n})^{T}\nabla_{a_{i+1}}\mathcal{L}(\theta)
\end{bmatrix}=(W_{i+1})^{T}(\nabla_{a_{i+1}}\mathcal{L}(\theta))$$
## Gradient w.r.t hidden layers pre activation function
$$\frac{\delta \mathcal{L}(\theta)}{\delta a_{ij}}=\frac{\delta \mathcal{L}(\theta)}{\delta h_{ij}} \frac{\delta h_{ij}}{\delta a_{ij}}=\frac{\delta \mathcal{L}(\theta)}{\delta h_{ij}}.g'(a_{ij})$$
$$\nabla_{a_{i}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta a_{i1}} \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta a_{in}}
\end{bmatrix}=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta h_{i1}}g'(a_{i1}) \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta h_{in}}g'(a_{in})
\end{bmatrix}=\nabla_{h_{i}}\mathcal{L}(\theta)\circ[\dots,g'(a_{ik}),\dots]$$
## Gradient w.r.t parameters
### For Parameters $W_{k}\epsilon \mathbb{R}^{n\times n}$
$$a_{k}=b_{k}+W_{k}h_{k-1} \implies \frac{\delta a_{ki}}{\delta W_{kij}}=h_{k-1,j}$$
$$\frac{\delta \mathcal{L}(\theta)}{\delta W_{kij}}=\frac{\delta \mathcal{L}(\theta)}{\delta a_{ki}}h_{k-1,j}$$
$$\nabla_{W_{k}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta W_{k00}} & \frac{\delta \mathcal{L}(\theta)}{\delta W_{K 01}} & . & . & \frac{\delta \mathcal{L}(\theta)}{\delta W_{K 0n-1}} \\
. & . & . & . & . \\
. & . & . & . & .  \\
\frac{\delta \mathcal{L}(\theta)}{\delta W_{kn0}} & \frac{\delta \mathcal{L}(\theta)}{\delta W_{K n1}} & . & . & \frac{\delta \mathcal{L}(\theta)}{\delta W_{K n-1n-1}} \\
\end{bmatrix}=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta a_{k0}}h_{k-1,0} & \frac{\delta \mathcal{L}(\theta)}{\delta a_{k0}}h_{k-1, 1}& . & . & \frac{\delta \mathcal{L}(\theta)}{\delta a_{k0}}h_{k-1,n-1} \\
. & . & . & . & . \\
. & . & . & . & . \\
\frac{\delta \mathcal{L}(\theta)}{\delta a_{kn}}h_{k-1,0} & \frac{\delta \mathcal{L}(\theta)}{\delta a_{kn}}h_{k-1, 1}& . & . & \frac{\delta \mathcal{L}(\theta)}{\delta a_{kn}}h_{k-1,n-1} \\
\end{bmatrix}=\nabla_{a_{k}}\mathcal{L}(\theta).h_{k-1}^{T}$$
### For biases $b\epsilon \mathbb{R}^{n}$
$$a_{ki}=b_{ki}+\sum_{j}W_{kij}h_{k-1,j}\implies \frac{\delta a_{ki}}{\delta b_{ki}}=1$$
$$\frac{\delta \mathcal{L}(\theta)}{\delta b_{ki}}=\frac{\delta \mathcal{L}(\theta)}{\delta a_{ki}} \frac{\delta a_{ki}}{\delta a_{ki}}=\frac{\delta \mathcal{L}(\theta)}{\delta a_{ki}}$$
$$\nabla_{b_{k}}\mathcal{L}(\theta)=\begin{bmatrix}
\frac{\delta \mathcal{L}(\theta)}{\delta a_{k0}} \\
. \\
. \\
\frac{\delta \mathcal{L}(\theta)}{\delta a_{kn}}
\end{bmatrix}=\nabla_{a_{k}}\mathcal{L}(\theta)$$




---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                                   | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                                               | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]                           | April 23, 2025 |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]]     | April 23, 2025 |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]] | April 23, 2025 |

tab: Previous Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                                                                                 | April 23, 2025 |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]]                                                                 | April 22, 2025 |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |

`````

---
# References
[output unit](https://www.youtube.com/watch?v=JSfRBOWp3Es&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=28)
[hidden unit](https://youtu.be/MDVVUY-sftQ?si=FvamY_3jUdj6N6Wv)
[parameters](https://youtu.be/DirgOcmERwA?si=_Q1TlOzrAxSHUczN)
$$$
