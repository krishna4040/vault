---
publish: true
title: Maths foundation
created: 2026-10-06
modified: 2026-10-15T16:16:14.557Z
published: 2026-10-15T16:16:14.557Z
tags:
  - resource
  - maths
  - foundation
  - investment
description:
cover:
author:
reference:
project: Investment
area: Finance
type: literature
---

# Percentages

| percentage               | $x\%=\frac{x}{100}$                                            |
| ------------------------ | -------------------------------------------------------------- |
| percentage of a quantity | $\text{amount} = \frac{x}{100} \times Q$                       |
| percentage change        | $\frac{\text{Final}-\text{Initial}}{\text{Initial}}\times 100$ |
| Amount increase by `r`   | $\text{final} = \text{Initial}(1+r)$                           |
| Amount decrease by `r`   | $\text{final} = \text{intial}(1-r)$                            |
| Ratio                    | $\frac{A}{B}$                                                  |

> [!warning]
> Never use Final when finding change percent

**Subsequent percentage change**
suppose $X$ rises by $x\%$ and then falls by $y\%$ then final value would be

$$
\text{final} = X(1+x)(1-y)
$$

Note even if $x=y, \text{final} \neq X$

# Probability

| Term              | Meaning                                             |
| ----------------- | --------------------------------------------------- |
| Random Experiment | process whose outcome is uncertain before it occurs |
| Sample Space      | Collection of all the outcomes                      |
| Event             | Collection of one or more outcomes, $E\subset S$    |

## Probability of an Event E

$$
P(E) = \frac{n(E)}{n(S)}
$$

- $0 \leq P(E) \leq 1$
- $P(E^{c})=1-P(E)$
- $P(S) = 1$

## Probability for Two Events

## General Rule of Addition

$P(A\cup B)=P(A)+P(B)-P(A \cap B)$

- $\text{if } A \cap B = \phi \implies P(A\cup B) = P(A)+P(B)$, A and B are called Mutually exclusive, $P(A \cap B) = 0$

## Conditional Probability

$$
P(A\mid B) = \frac{P(A \cap B)}{P(B)}
$$

> [!abstract] Intution
> Without additional information its $P(A)$ but known that B has occur relevant universe becomes the outcomes where B occured.

Concepts related to conditional probability

```tabs:
tab: Independent events
$$
\exists A,B \subset S \text{ s.t. } P(A\mid B) = P(A) \implies P(A \cap B) = P(A)P(B)
$$
tab: Baye's Theorem
$$
P(A\mid B) = \frac{P(B\mid A)P(A)}{P(B)}
$$
tab: TPT
$$
P(A) = \sum_{i}P(A\mid B_{i})P(B_{i})
$$
```

# Statistics

| Term        | Meaning                    |
| ----------- | -------------------------- |
| Population  | Sample space               |
| Sample      | Subset of Population       |
| Observation | One recorded data point    |
| Dataset     | Collection of observations |
Let us define a Dataset $X$ with observations $x_{1},x_{2},x_{3}\dots x_{i}$ Then we can derive some analysis like center, spread, and shape.

Some `center` analysis include:

```tabs
tab: Mean
> arithmetic balance point, signifies overall average of observations
$$
\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_{i}
$$
> [!important] Property
> $$\sum_{i=1}^{n}(x_{i}-\bar{x}) = 0$$

**Weighted Mean**
$$
\bar{x_{w}}=\frac{\sum w_{i}x_{i}}{w_{i}}
$$

tab: Median
> Middle of typical observation
$$
\tilde{x} = \begin{cases}
x_{k+1} & i=2k+1 \implies \text{i is odd} \\
x_{k} & i=2k \implies \text{i is even}
\end{cases}
$$
> [!important]
> Observations should be arragned in non decreasing order

tab: Mode
> Most Common observation
$$
Mode(X) = arg \ max_{x}f(x)
$$
where $f(x)$ is frequency function defined as $f(x)=\sum_{i=1}^{n}1_{x_{i}=x}$ and $1_{x_{i}=x}$ is indicator function defined as $1_{x_{i}=x}=\begin{cases}1 & x_{i}=x \\  0 & x_{i}\neq x\end{cases}$

```

Some `Spread` analysis include:

```tabs:
tab: Range
$$
Range = \text{Maximum} - \text{Minimum}
$$

tab: Deviation
> This tell us how far each observation lies from the mean

$$D=\{ d_{1},d_{2},\dots d_{i} \}, d_{i}=x_{i}-\bar{x}$$

> [!important] Property
> $$\sum_{d_{i}\in D}d_{i}=0$$
> so average deviation from mean is always zero, this doesn't tell us how dispersed the observations are as positive and negetive cancel out each other.
>
> So we define **Squared Deviations** as $SS$ as:
> $$SS=\sum_{d_{i}\in D}d_{i}^{2}%$$

tab: Variance
> average squred deviation from mean
$$
\sigma^{2}=\begin{cases}
\frac{SS}{N} & \text{population} \\
\frac{SS}{n-1} & \text{sample}
\end{cases}
$$

> [!important] Significance
> How dispresed are observations around their mean
> lower variance -> observations tend to cluster near mean
> higher variance -> observations are more spread

tab: Standard Deviation
$$\sigma=\sqrt{\sigma^{2}}$$

This tells us how much do observations vary around their mean
Variance has squared units of obersvations where as SD has same unit as that of SD.

tab: Qunatile & IQR
For a RV X, p-qunatile $Q_{p}$ is a value satisfying:
$$P(X\leq Q_{p})=p, 0 \leq p \leq 1$$

- $Q_{1}=Q_{0.25}$
- $Q_{2}=Q_{0.50}$ also known as median
- $Q_{3}=Q_{0.75}$

IQR is the interquartile range defined as $IQR=Q_{3}-Q{1}$
Variance/SD use all observations, IQR focuses on central 50%
```

Some `Shape` analysis include:

```tabs
tab: Skewness
> captures asymmetry in observations.

$$
\gamma_{1}=\frac{E[(X-\mu)^{3}]}{\sigma^{3}}
$$
- $\gamma_{1}>0$, distribution is `right-skewed`, right tail tends to be longer / havier
- $\gamma_{1}<0$, distribution is `left-skewed`, left tail tends to be longer / havier
- $\gamma_{1}\approx0$ little or no skewness

tab: Kurtosis
> closely related to extemeness of the tails.

$$
\beta_{2}=\frac{E[(X-\mu)^{4}]}{\sigma^{4}}
$$
```

## Random Variable

> It is a Function that assigns a numerical value to each outcome $\omega$ of sample space $\Omega$ defined as

$X:\Omega\to \mathbb{R}$

# Calculus
