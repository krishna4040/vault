---
publish: true
title: "Lecture 24 : Logistic Regression-I"
description: In this lecture, we will learn the concept behind Logistic regression especially in the case of classification problem, concepts like Log-it, MLE, etc.
created: 2025-04-05
modified: 2026-10-15T16:16:14.556Z
published: 2021-08-16
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=URaAojXX1H4&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=25&t=409s
author: IIT Roorkee
lecture: 24
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Logistic Regression ~ overview

- Classification problems
- Discrete output

**Binary Classification**

- 0 or 1
- True or False
  In LSA we find parameters such that error is minimum and we get a linear relationship between input and output

# Sigmoid function

A Sigmoid function is a mathematical function which has a characterstic S-shaped curve.

- logistic function
- hyperbolic tangent
- arctangent
  $S(x)=\frac{1}{1+e^{-x}}$

# Logistic Regression

It is basically a supervised classification algorithm. In a classification problem, the target variable or output y can take only discrete values for a given set of features(or inputs)

Logistic regression becomes classification techniques only when a decision threshold is brought into the picture. The setting of the threshold value is a very important aspect of Logistic regression and is dependent on the classification problem itself.
Based on number of categories, logistic regression can be classified as:

- _Binomial_: target variable can have only 2 possible types: 0 or 1 which may represent win vs loss, pass vs fail, dead vs alive
- _multinomial_: target variable can have 3 or more possible types which are not ordered like, disease A, B, C.

# Probability basics

**Sample space**
It is the set of all possible outcomes of the experiment, denoted by omega

**Event space**
the event space is the space of potential results of the experiment. The event space is obtained by considering the collection of subsets of sample space, In case of discrete prob distribution $A = P(\Omega)$
**Probability**
with each event A belongs event space, we associate a number P(A) that measures the probability or degree that the event will occur. The number P(A) is called probability of A.
$0 \leq P(A) \leq 1 \text{ and } \sum P(A_{i})=1$
**Random Variable**
It is a function from sample space to target space
$X:\Omega\to T$
_Example_
$\Omega=\{ HH,HT,TH,TT \}$
Event = counting the number of heads also known as classes
$T = \{ 0,1,2 \}$

- X(HH)=2
- X(HT)=1=X(TH)
- X(TT)=0

# LR vs MLR

instead of $Y=\alpha^{T}X$
We model the probability that Y is equal to class, given X
$p(x)=P(Y=1/X)=\frac{1}{1+e^{-\alpha^{T}X}}$
$\log\left( \frac{p(x)}{1-p(x)} \right)=\alpha^{T}X$
The LHS is known as log.it of p(x) or log.odds

# Logistic regression

Given samples as,
$(x_{i},y_{i})\epsilon \mathbb{R}^{p}\times \{ 0,1 \},i=1,2,\dots,n$
model is, $\log\left( \frac{p(x_{i})}{1-p(x_{i})} \right)=\alpha^{T}x_{i}$
we need to estimate alphas, we use the technique of maximum likelihood estimation
$L(\alpha)=\prod_{i,y_{i}=1}p(x_{i})\prod_{i,y_{i}=0}(1-p(x_{i}))=\prod_{i=1}^{n}p(x_{i})^{y_{i}}(1-p(x_{i}))^{1-y_{i}}$
we find alpha which maximizes this likelihood
maximising the function is similar to maximising its logarithm
so we define $l(\alpha)=\log L(\alpha)$
$l(\alpha)=\sum_{i=1}^{n}y_{i}\log(p(x_{i}))+(1-y_{i})\log(1-p(x_{i}))=\sum_{i=1}^{n}y_{i}\log\left( \frac{p(x_{i})}{1-p(x_{i})} \right)+\log(1-p(x_{i})) = \sum_{i=1}^{n}y_{i}(\alpha^{T}x_{i})-\log(1-p(x_{i}))$
we do not have closed form solution for maximizing this function so we use a numerical optimization technique known as _Gradient Descent_

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                       | April 05, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                         | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |

tab: Previous Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]]                                             | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=URaAojXX1H4\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=25\&t=409s)
