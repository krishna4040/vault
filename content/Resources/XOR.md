---
publish: true
title: XOR
description: XOR properties and patterns
created: 2026-10-12
modified: 2026-10-15T16:16:14.560Z
published: 2026-10-15T16:16:14.560Z
tags:
  - resource
  - dsa
  - bits
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 3
type: permanent
---

# First Principles

$$
A\oplus B=\begin{cases}
1 & A\neq B \\
0 & A=B
\end{cases}
$$

## Truth Table

Refer here: [[Bit Fundamentals#^f24332]]

## Properties

Refer here: [[Bit Fundamentals#^3d508d]]

Some improtant properties

1. Identity → $x\oplus 0=x$
2. Self Inverse → $x\oplus x=0$
3. Cancellation → $x\oplus y\oplus y=x$
4. Commutative → $x\oplus y=y\oplus x$
5. Associative → $(x\oplus y)\oplus z=x\oplus(y\oplus z)$

# Algorithms using XOR

## XOR Swap

> The algebraic property allow two values to be swapped without a temp variable

```cpp
a ^= b;
b ^= a;
a ^= b;
```

## Finding unique Item

> The cancellation property of xor helps find a unique item when duplicates are even

$$
unique=XOR_{a_{i}\in A}(a_{i})
$$

## XOR from 1 to n

$$
XOR(1..n)=\begin{cases}
n & n\%4=0 \\
1 & n\%4=1 \\
n+1 & n\%4=2 \\
0 & n\%4=3
\end{cases}
$$

We can define XOR in a range \[L, R] using above formula as,

$$
XOR(L..R)=XOR(R)\oplus XOR(L-1)
$$

## XOR as difference detector

1. $a\oplus b=0\implies a=b$
2. $a\oplus b\neq 0\implies a\neq b\implies(a\oplus b)\&(-a\oplus b) \text{ gives the difference bits for a and b}$
