---
publish: true
title: Graycode
description: all about gray code
created: 2026-10-13
modified: 2026-10-16T15:51:59.103Z
published: 2026-10-16T15:51:59.103Z
tags:
  - resource
  - dsa
  - bits
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 5
type: permanent
---

# What is Gray Code?

> Gray code is a binary encoding in which two consecutive values differ in exactly one bit

$$
Gray(n)=n\oplus(n\gg 1)
$$

an important property of gray code:
$d_{H}(G_{i},G_{i+1})=popcount(G_{i}\oplus G_{i+1})=1$

# Binary to Gray Conversion

$$
G=B\oplus(B\gg 1)
$$

# Gray to Binary Conversion

$$
b_{i}=\oplus_{j=i}^{n-1}g_{j}
$$
