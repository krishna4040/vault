---
publish: true
title: GCD & Euclid
description: gcd and euclid
created: 2026-10-05
modified: 2026-10-16T15:51:59.103Z
published: 2026-10-16T15:51:59.103Z
tags:
  - maths
  - resource
  - dsa
cover:
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 2
type: permanent
---

# GCD, LCM - Definitions

$gcd(a, b) = max \{ d > 0: d \mid a \ \cap \ d\mid b \}$
$lcm(a, b) = min \{m > 0: a \mid m \ \cap \ b \mid m \}$
**Properties**

| Property          | Definition                                     |
| ----------------- | ---------------------------------------------- |
| Symmetry          | $gcd(a,b) = gcd(b, a)$                         |
| Scaling property  | $g_{ka, kb} = kg_{a, b}$                       |
|                   | $g_{a,0} = g_{0,a} = \|a\|$                    |
|                   | $g_{a,1} = g_{1,a} = 1$                        |
|                   | $g_{0,0} = 0$                                  |
|                   | $g_{a,b} = 1 \implies \text{a, b are coprime}$ |
| Bezout’s Identity | $g_{a, b} \mid ax+by$                          |
| Euclid Algoritm   | $g_{a,b} = g_{a, a\%b}$                        |

> [!Important] LCM
> $lcm(a,b) = \frac{a}{gcd(a,b)}.b$

# Bezout’s Identity

$ax+by = g_{a,b}$
Then $(x, y)$ are called Bezout’s coefficient and are computed using extended euclidian algoritm

# Linear Diaphotime Equation

$ax + by = c \ \cap \ g \mid c \implies \exists (x, y) \text{ satisfying the equation given as}$
$(x, y) = \left( x_{0}+\frac{b}{g}t, y_{0}-\frac{a}{g}t \right)$
where $x_{0}, y_{0}$ are Bezout’s coefficients.

# GCD using prime factorization

$gcd(a, b) = \prod p^{min(\alpha_{p}, \beta_{p})}$
$lcm(a, b) = \prod p^{max(\alpha_{p}, \beta_{p})}$
