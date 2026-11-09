---
publish: true
title: "Lecture 52: Continuous probability distributions"
description: "In this lecture, we discuss few continuous probability distributions:  uniform distribution, exponential and Gaussian(normal) distribution."
created: 2025-04-18
modified: 2026-10-15T16:16:14.553Z
published: 2021-09-14
tags:
  - resource
  - AI
  - ML
  - maths
  - probability
  - statistics
source: https://www.youtube.com/watch?v=cWeICjN9Gyw
author: IIT Roorkee
lecture: 52
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Continuous Distributions

## Uniform Distribution

A RV X has uniform distribution and it is reffered to as a CURV, denoted as X ~ $U[a,b]$ if and only if its prob density is given by

$$$u(x;a,b)=\begin{cases}
\frac{1}{b-a}; a<x<b \\
0; otherwise
\end{cases}$$
the parameters a and b of this prob density are real constants, with a < b.
- Mean → $E[X]=\frac{a+b}{2}$
- Variance → $V[X]=\frac{1}{12}(b-a)^{2}$
## Exponential distribution
A RV X has an ED if and only if its prob density is given by
$$\exp(x;\lambda) = \begin{cases}
\frac{1}{\lambda}e^{-x/\lambda}, x\geq0 \\
0, x\leq 0
\end{cases}$$
where $\lambda > 0$
- mean → $E[X]=\lambda$
- variance → $V[X]=\lambda^{2}$
## Normal (Gaussian) Distribution
A CRV X is said to follow a normal distribution, denoted as X ~ $N(\mu,\sigma^{2})$ if its pdf id given as,
$$f(x)=\frac{1}{\sqrt{ 2\pi\sigma }}\exp\left[ -\frac{1}{2} (\frac{x-\mu}{\sigma})^{2} \right]$$
where,
$$\sigma> 0, -\infty<x,\mu<\infty$$
- mean → $E[X]=\mu$
- variance → $V[X]=\sigma^{2}$


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                          | created        |
| ------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Joint probability distribution and covariance.md\|Joint probability distribution and covariance]] | April 18, 2025 |

tab: Previous Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]     | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                         | April 18, 2025 |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]   | April 18, 2025 |
| [[Resources/Review on Probability.md\|Review on Probability]]                               | April 18, 2025 |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=cWeICjN9Gyw)
$$$
