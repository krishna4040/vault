---
publish: true
title: Regularization
description: Bias and variance
created: 2025-03-10
modified: 2026-10-15T16:16:14.558Z
published: 2026-10-15T16:16:14.558Z
tags:
  - resource
  - AI
  - DL
author: IIT Roorkee
source:
lecture: 7
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Bias and Variance

$Bias = E[\hat{y}]-y$
$Variance=E[\hat{y}-E[y]^{2}]$
$Error=B^{2}+V+\sigma^{2}$
Let there be a true function $y_{i}=f(x_{i})+\epsilon_{i}$ and our model be $y_{i}=\hat{f}(x_{i})$ then,
$MSE=E[(\hat{y_{i}}-y)^{2}]=E[(\hat{f}(x_{i})-f(x_{i}))^{2}]-E[\epsilon_{i}^{2}]+2ECov(\epsilon_{i},\hat{f}(x_{i})-f(x_{i}))$
in the test case, $cov(\epsilon_{i},\hat{f}-f)=0$ implies, $\text{True Error}=\text{Emperical Error}+\text{constant}$ and in the training case, $cov(\epsilon_{i},\hat{f}-f)\neq 0$, by Stein’s Lemma we arrive at a conclusion $\frac{1}{n}\sum\epsilon_{i}(\hat{f}-f)=\frac{\sigma^{2}}{n} \frac{\sum\delta \hat{f}}{\delta f}$ in this case $\text{True Error} = \text{Empiracl Error}+\text{some constant}+\text{Model complexity}$ and can be represented as
$\mathcal{L}(\theta)=\mathcal{L}(\theta)_{train}+\Omega(\theta)$ where $\Omega(\theta)$ approximate to stein’s lemma this is the regularized term and results in regularization

- L1 Regularization
- L2 Regularization
- Early stopping
- Adding noise to input
- Dataset Augmentation

# L2 Regularization

$\mathcal{L}(\theta)=\mathcal{L}(\theta)+\frac{\alpha}{2}||\theta||^{2}$
$\tilde{\theta_{t}}=Q[I-(\Lambda+\alpha I)^{-1}\alpha]Q^{T}\theta^{*}$

# Early stopping

We stop before convergence so that weigths do not increase
By Taylor series the loss function is given as where $\mathcal{L}(\theta^{*})=0$ is given as,
$\mathcal{L}(\theta)=\mathcal{L}(\theta^{*})+\frac{1}{2}(\theta-\theta^{*})^{T}H(\theta-\theta^{*}) \implies \nabla \mathcal{L}(\theta)=H(\theta-\theta^{*})=Q\Lambda Q^{T}(\theta-\theta^{*})$
update rule is given as,
$\theta_{t}=\theta_{t-1}-\eta \nabla \mathcal{L}(\theta)$
when $\theta_{0}=0$, $\theta_{t}$ is given as,
$\theta_{t}=Q[I-(1-\epsilon\Lambda^{t})]Q^{T}\theta^{*}$ which is similar to L2 regularization for some equivalent $\epsilon,\Lambda,\alpha$

# Adding Noise to input

Let we add noise to input, Let the inputs be $\tilde{x_{i}}=x_{i}+\epsilon_{i}$ then the model is given as,
$\tilde{y}=\sum \tilde{x_{i}}w_{i}=\hat{y}+\sum w_{i}\epsilon_{i}$
Then,
$MSE=E[(\tilde{y}-y)^{2}]=E[(\hat{y}-y)^{2}]+\sigma^{2}\sum w^{2}$ This is similar to Dataset Augmentation where we transform training data to so that our model do not overfit to training data

# Ensemble methods

# Dropout

# Better Activation Function

| Activatoin Functions               | **Sigmoid**          | **Tanh**   | **ReLU**                                |
| ---------------------------------- | -------------------- | ---------- | --------------------------------------- |
| formula                            | $\frac{1}{1+e^{-x}}$ | $\tanh(x)$ | $max(0,x)$                              |
| Saturation and Vanishing Gradients | yes                  | yes        | Not in positive but in negitive reigion |
| zero centered                      | no                   | yes        | yes                                     |
| Computationaly expensive           | yes                  | yes        | no                                      |
When input is negitive the Output of the ReLU function becomes zero and this does not change in a neural network resulting to be a dead neuron

**Leaky ReLU** → $max(0.01x,x)$
**Parameteric ReLU** → $max(\alpha x,x)$
**Exponential ReLU** → $\begin{cases}x, \text{x>0} \\ ae^{x}-1, \text{x<0}\end{cases}$
**Maxout Neuron** → $max(w_{1}^{T}x+b_{1},w_{2}^{T}x+b_{2})$

# Batch Normalization

Normalize Inputs and output of hidden layer in batches

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Vectorial Representation of Words.md\|Vectorial Representation of Words]] | March 10, 2025 |
| [[Resources/CNN.md\|CNN]]                                                             | March 10, 2025 |
| [[Resources/RNN.md\|RNN]]                                                             | March 10, 2025 |

tab: Previous Lectures
| File                                                                                                                        | created        |
| --------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Principal Component Analysis and its Interpretations.md\|Principal Component Analysis and its Interpretations]] | April 24, 2025 |
| [[Resources/Eigenvalue Decompositon.md\|Eigenvalue Decompositon]]                                                           | April 24, 2025 |
| [[Resources/Linear Algebra  Basic Definitions.md\|Linear Algebra  Basic Definitions]]                                       | April 23, 2025 |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]]                 | April 23, 2025 |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]]                     | April 23, 2025 |

```

---

# References

undefined
