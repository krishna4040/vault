---
publish: true
title: "Lecture 49: Bayes' theorem and Random variables"
description: This lecture discusses the Bayes' theorem and its applications. It also discusses what random variables are and their classification.
created: 2025-04-18
modified: 2026-10-15T16:16:14.552Z
published: 2021-09-14
tags:
  - resource
  - maths
  - probability
  - AI
  - ML
source: https://www.youtube.com/watch?v=0UxcDQz4sWQ&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=50&t=1s
author: IIT Roorkee
lecture: 49
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Baye’s Theorem

if $\{ E_{1},E_{2},\dots,E_{n} \}$ are n non-empty that constitute a partition of a sample space S and A is any event of non-zero probability then
$P(E_{i}|A)=\frac{P(E_{i})P(A|E_{i})}{\sum_{i=1}^{n}P(E_{i})P(A|E_{i})}$

# Random variables

A random variable is some uncertain quantity with an associated probability distribution over the values it can assume. Formally a random variable is a function X: S→R
Range of X is denoted as $X(S)=\{ X(s): s\epsilon S \}$
$P(X=x)=P(\{ s\epsilon S:X(s)=x \})$

# CDF (cumulative distribution function)

The CDF or the DF gives the probabiity that a random variable is at most a certain value.
$\text{cdf of X }= F_{X}(x)=P(X\leq x)\forall x\epsilon \mathbb{R}$

# Discrete Renadom Variable

It is random variavle that has a countable range and assumes each value in its range with positibe probability. Discrete random variables are completely specified by their **probability mass function** (pmf) $f_{x}:X(S)\to[0,1]$ which staisfies

- $f_{X}(x)\geq0,\forall x\epsilon X(S)$
- $\sum_{x\epsilon X(S)}f_{X}(x)=1$

# Continuous Random Variable

It is a random variable that has an uncountable range and whose cdf $F_{X}$ is a continuous function which are completely specified by their **probability density function** (pdf) $f_{X}:X(S)\to[0,1]$ which statisfies

- $f_{X}(x)\geq 0, \forall x\epsilon X(S)$
- $\int_{-\infty}^{\infty} f_{X}(x) \, dx=1$

# Results

- $P(a\leq X\leq b)=P(X\leq b)-P(X\leq a)=F_{X}(b)-F_{X}(a)$
- $F_{X}(x)=P(X\leq x)=\begin{cases}\int_{-\infty}^{\infty} f_{X}(t) \, dt; \text{X is continous} \\ \sum_{y\leq x}^{-\infty}f_{X}(y); \text{X is discrete} \end{cases}$
- $f_{X}(x)=P(X\leq x)-P(X<x)=F_{X}(x)-F_{X}(x^{-})$ X is descrete
- $f_{X}(x)=\frac{d}{dx}F_{X}(x)$ X is continuous

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                          | created        |
| ------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                                           | April 18, 2025 |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]                       | April 18, 2025 |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]]                   | April 18, 2025 |
| [[Resources/Joint probability distribution and covariance.md\|Joint probability distribution and covariance]] | April 18, 2025 |

tab: Previous Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]                   | April 17, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]                     | April 16, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=0UxcDQz4sWQ\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=50\&t=1s)
