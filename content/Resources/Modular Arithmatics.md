---
publish: true
title: Modular Arithmetics
description: Modular arithmetics
created: 2026-10-05
modified: 2026-10-15T16:16:14.557Z
published: 2026-10-15T16:16:14.557Z
tags:
  - maths
  - resource
  - dsa
cover:
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 3
type: permanent
---

# Definition

$a = bq+r \implies a \% b = r$
where `a` is Dividend, `b` is Divisor or Modulus, and `r` is remainder

**Properties**

|     | $(a\pm b)\%m = (a\%m)\pm (b\%m)\%m$  |
| --- | ------------------------------------ |
|     | $ab\%m = (a\%m)(b\%m)\%m$            |
|     | $a\%1=0$ and $a\%0=\text{undefined}$ |
|     | $1\%a=1$ and $0\%a=0$                |
|     |                                      |

# Modular Equivalence

$a\equiv b\%m \implies m \mid(a-b) \implies a\%m=b\%m\implies (a-b)\%m=0$

> [!Important] Inference
> $x\equiv a\%m \implies (x-a)\%m=0\implies x=\{ a +mk: k \in \mathbb{Z} \}$

**Properties**

|     | $a\equiv b\%m \ \cap \ c\equiv d\%m \implies a\pm c\equiv b\pm d\%m$ |
| --- | -------------------------------------------------------------------- |
|     | $a\equiv b\%m \ \cap \ c\equiv d\%m \implies ac \equiv bd \%m$       |
|     | $a\equiv b\%m \implies a^{n}\equiv b^{n}\%m$                         |
|     | $a\equiv 0\%m\implies m\mid a\implies a\%m=0\implies a=bm$           |

# Modular Inverse

$MI(a, m) = a^{-1}=x \text{ s.t. } ax\equiv 1\%m\implies ax+my=1$
Solution (modular inverse) exists for the equation $ax+my=1$ when $gcd(a,m)=1$

## MI using Fermants Theorem

$\exists p, p\nmid a\implies gcd(a,p)=1\implies a^{p-1}\equiv 1\%p\implies a^{-1}\equiv a^{p-2}\%p$
for prime $p$ the numbers $1,2,3,\dots p-1$ when multiplied by $a\%p$ becomes permutation of themselves i.e. $a, 2a, 3a, \dots a(p-1)$
This is same as
$1.2.3\dots(p-1)\equiv a.2a\dots (p-1)a\% \implies (p-1)! \equiv a^{p-1}(p-1)! \%p \implies a^{p-1}\equiv 1\%p$

## MI using Euclid Theorem

> This is the general version for Fermants Theorem

$\exists m, gcd(a,m) = 1 \text{ then }a^{-1}\equiv a^{\phi(m)-1}\%m$

> [!NOTE]
> $\phi(p) = p-1$

## Precomputing Modular Inverse

$\forall i\in \mathbb{Z}, 1\leq i< p\implies inv[i] = p-\left\lfloor  \frac{p}{i}  \right\rfloor.inv[p \%i] \ \% \ p $

# Linear Congruences

$ax\equiv b\%m\implies m\mid(ax-b)\implies ax-mk=b$
This is linear Diaphtime Equation, Let $g_{a,m}=g$ then three conditions exists

| Condition  | Implication                            |
| ---------- | -------------------------------------- |
| $g\nmid b$ | No Solution for this linear conguence  |
| $g = 1$    | $x\equiv b a^{-1} \%m$                 |
| $g \mid b$ | $x\equiv \frac{b}{g} \frac{a}{g}^{-1}$ |

## Chinese Remainder Theorem

> For system of Linear congruences we use CRT to find a solution

Let system of Linear congruences be represented as, $x\equiv a_{i}\%m_{i}$, then solution exists only if
$gcd(m_{i}, m_{j})=1 \ \forall \ i\neq j$
then we define $M_{i}=\frac{\prod m_{i}}{m_{i}}$ then solution is given as,
$x\equiv \sum a_{i}M_{i}M_{i}^{-1} \  \% \ M$
