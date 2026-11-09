---
publish: true
title: "Lecture 51: Discrete probability distributions"
description: "In this lecture, we discuss few discrete probability distributions: binomial distribution and poisson distribution."
created: 2025-04-18
modified: 2026-10-15T16:16:14.554Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
  - maths
  - probability
  - statistics
source: https://www.youtube.com/watch?v=qDIK0wR41Ic
author: IIT Roorkee
lecture: 51
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Discrete Distributions

## Bernoulli’s Trials

A series of trials are referred to as “Bernoulli's’s trials” if the following assumptions hold:

- There are only two possible outcomes for each trial success or failure
- the prob of success remains same for each trial
- the outcomes from different trials are independent
- there are finitely many such trials conducted

## Bionomial Distributions

if n independent BTs are performed, then the RV X denoting the number of successes in the n trials is said to follow the BD, denoted as X ~ b(n,p) where p is the prob of success in each trial. if there are x success in n trials, then we have n-x failures, so prob of x successes if given as
$f(x)=p[X=x]=C^{n}_{x}p^{x}(1-p)^{n-x};x=0,1,\dots,n$

- mean → $E[X]=np$
- variance → $V[X]=npq$

## Poisson Distribution

A RV X is said to follow PD, denoted as X ~ $P(\lambda)$ if its pmf is given as
$f(x)=P[X=x]=\frac{\lambda^{x}e^{-\lambda}}{x!}, x=0,1,\dots, \lambda> 0$

- mean → $E[X]=\lambda$
- Variance → $V[X]=\lambda$

Poisson distribution serves as a model for various experiments and phenomenon associated with waiting of an occurence. for instance, the number of customers arriving a shop in a given time interval can be modeled using poisson distribution

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                          | created        |
| ------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]]                   | April 18, 2025 |
| [[Resources/Joint probability distribution and covariance.md\|Joint probability distribution and covariance]] | April 18, 2025 |

tab: Previous Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                         | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=qDIK0wR41Ic)
