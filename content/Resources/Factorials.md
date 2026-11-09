---
publish: true
title: Factorials
description: Factorials
created: 2026-10-05
modified: 2026-10-15T16:16:14.554Z
published: 2026-10-15T16:16:14.554Z
tags:
  - maths
  - resource
  - dsa
cover:
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 4
type: permanent
---

# Definition

$n! = 1.2.3\dots n$

- Base Case: $0! = 1$
- $O(n)$ time is required to find n!
- long long overflows after $20!$
- $n! \% m$ is easily computable

## Legrande Theorem

> This Deals with prime factorization of Factorials, exponent of p in n! can be determined linearly

$v_{p}(n!)=\sum_{k=1}^{\infty}\left\lfloor  \frac{n}{p^{k}}  \right\rfloor $

> [!Important] Trailing Zeroes in factorial
>
> $$
> Z(n!) = min \{ v_{2}(n!), v_{5}(n!) \}
> $$
>
> Time complexity of this solution is given as $O(\log_{5}n)$

## Factorials under mod

$$
n! \%p
$$

There can be two cases:

```tabs
tab: p > n
Easily computable

tab: p <= n
$$\text{if} p \mid n! \implies n! \equiv 0 \% p \implies \forall k \leq v_{p}(n!), n! \equiv 0 \% p^{k}$$
```

## Factorial Ratios

$$
\frac{n!}{m!} = (m+1)(m+2)\dots n
$$

This can be computed in $O(m-n)$ time

# Combinators

$$
nCr = \begin{pmatrix}
n \\
r
\end{pmatrix} = \frac{n!}{r!(n-r)!}
$$

**Properties**

|     | $nC0=1$             |
| --- | ------------------- |
|     | $nCn=1$             |
|     | $nCr=nCn-r$         |
|     | $nCr=n-1Cr-1+n-1Cr$ |

## Lucas Theorem

> To calculate Combinator under a modulus

If we need to find $nCr \% p$ then wkt $n = n_{0}+n_{1}p+n_{2}p^{2}+\dots$, similarly $r=r_{0}+r_{1}p+r_{2}p^{2}+\dots$ then we can find $nCr \% p$ as:
$nCr \%p = \prod n_{i}Cr_{i} \%p$

## Falling and Rising Factorials

```tabs
tab: Falling Factorial
$$
n^{\underline{r}} = nPr = \frac{n!}{(n-r)!} = n.(n-1)\dots(n-r+1)
$$

tab: Rising Factorial
$$
n^{\bar{r}} = n.(n+1)\dots(n+r-1)
$$
```
