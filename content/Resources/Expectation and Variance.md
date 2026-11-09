---
publish: true
title: "Lecture 50: Expectation and Variance"
description: "In this lecture, we discuss the first two moments: expectation and variance of a random variable."
created: 2025-04-18
modified: 2026-10-15T16:16:14.554Z
published: 2021-09-14
tags:
  - resource
  - maths
  - probability
  - statistics
  - AI
  - ML
source: https://www.youtube.com/watch?v=ucSB5QOTxU8&t=1278s
author: IIT Roorkee
lecture: 50
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Expectation

Expectation of a random variable X, denoted as $E[X]$ is the prob-weighted average of all its possible values. Formally, expectation of X is defined as

$$$\mu=E[X]=\begin{cases}
\sum_{x}xf(x); \text{X is discrete} \\
\int_{-\infty}^{\infty} xf(x) \, dx; \text{X is continuous}
\end{cases}$$
where $f(x)$ is the pmf of X when X is discrete and pdf when X is continuous
> [!note]
> $$E[aX+b]=E[aX]+E[b]=aE[X]+b$$
# Variance
Variance of a RV X is a measure of spread or dispersion of X about the mean. formally, it is the average squared deviation of the values of X from the mean of X,
$$V[X]=E[X-E[X]]^{2}=E[X^{2}]-(E[X])^{2}$$
> [!note]
> $V[aX+b]=a^{2}V[X]$



---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                          | created        |
| ------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]                       | April 18, 2025 |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]]                   | April 18, 2025 |
| [[Resources/Joint probability distribution and covariance.md\|Joint probability distribution and covariance]] | April 18, 2025 |

tab: Previous Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]                   | April 17, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=ucSB5QOTxU8&t=1278s)
$$$
