---
publish: true
title: Growth
created: 2026-10-06
modified: 2026-10-15T16:16:14.555Z
published: 2026-10-15T16:16:14.555Z
tags:
  - resource
  - investment
  - foundation
description:
cover:
author:
reference:
project: Investing
area: Finance
type: literature
---

# Return

^c4861b

It refers to change in value, also know as `Rate`. It can be simple or compound.

```tabs
tab: Simple Rate
> Simple rate applied to original principal

Let R be sequence of n Rate changes then cumulative rate can be defined as
$$R_{final} = \sum_{r_{i}\in R}^{n}r_{i}

tab: Compound Rate
> Compound rate applies to accumulated principal

Let R be sequnce of n Rate changes then cumulative rate can be defined as
$$R_{final} = \prod_{r_{i}\in R}^{n} (1+r_{i})-1$$
```

# Growth

$$
G = 1+r
$$

Growth can be either simple or compound.

## Simple

> Growth Calculated from original principal each period say n

$FV = PV(1+rn)$

## Compounded

> Growth Calculated from previous periods Base, if total periods is n then

$FV = PV(1+r)^{n}$

### Rate across periods

> suppose you know a compound rate $r_{1}$ for a period of length $t_{1}$ and you want the equivalent compound rate $r_{2}$ for another period $t_{2}$

$$
r_{2} = (1+r_{1})^{t_{2}/t_{1}}-1
$$

> [!note] CAGR (Compound Annual growth rate)
> when $t_{2}=1yr$ then $r_{2}=CAGR$ implies
>
> $$
> CAGR = (1+r_{1})^{1/t_{1}}-1 = (\frac{FV}{PV})^{1/n}-1
> $$
