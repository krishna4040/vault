---
publish: true
title: Bit Mask
description: masking in bit manipulation
created: 2026-10-12
modified: 2026-10-15T16:16:14.552Z
published: 2026-10-15T16:16:14.552Z
tags:
  - resource
  - dsa
  - bits
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 2
type: permanent
---

# Bit Positions

> Bit position starts from zero
> $b_{k}\dots b_{3}b_{2}b_{1}b_{0}$

# Bit Mask

Bit mask is defined using $M=1<<k$ so there are four fundamental operations that can be performed using this mask.

| Operation      | Expression              |
| -------------- | ----------------------- |
| Check bit `k`  | `x & M`<br>`x >> k & 1` |
| Set bit `k`    | `x \|= M`               |
| Clear bit `k`  | `x &= ~M`               |
| Toggle bit `k` | `x ^= M`                |

Some Variations Include

````tabs
tab: Get Lower k bits
use Mask $2^{k}-1$, so
```cpp
int lowbits = x & ((1<<k)-1);
```

tab: Get bits in range `l` through `r`
use Mask $((1 << (r-l+1))-1)<<l$
```cpp
int bits = (x >> l) & mask;
```
````
