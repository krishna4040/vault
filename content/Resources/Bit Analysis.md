---
publish: true
title: Bit Analysis
description: analysis and pattern in binary represntation
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
lecture: 4
type: permanent
---

# Common Numbers and their binary representation

| Value                      | Binary Pattern                           | Pattern |
| -------------------------- | ---------------------------------------- | ------- |
| $2^{k}$                    | 1 followed by k 0’s, aka sparse numbers  |         |
| $2^{k}-1$                  | k 1’s                                    |         |
| $2^{k}\mid n$              | lowset k bits of n are 0                 |         |
| $2^{w}-1-2^{k}$            | one 0 at kth position, aka dense numbers |         |
| $(AA)_{16} \mid (55)_{16}$ | alternating bits                         |         |

> [!tldr] Trick
> for calculating value of binary representation, break into power of 2’s

**MSB / LSB Significance**

- `LSB` Signifies parity, $n\&1$ is used to check odd numbers.
- `MSB` Signifies sign under signed integers interpretation.

# Popcount

> Popcount refers to number of set bits in a binary representation of a number

$$
popcount(x) = \sum_{i=0}^{w-1}b_{i}
$$

| Algorithm                | Core Idea                          | Time complexity                         |
| ------------------------ | ---------------------------------- | --------------------------------------- |
| Naive approach           | Count number of set bits           | $O(d)$                                  |
| Brian Kernigham’s Method | $n\&n-1$ clears right most setbit  | $O(S)$ where is S is sparsity of number |
| Built in methods         | std::popcount, \_\_builtin\_popcount, |                                         |
Applications:

## Power of 2’s

$$
n > 0 \ \cap \ (n\&(n-1)) = 0
$$

## Hamming Distance

$$
d_{H}(a,b)=popcount(a\oplus b)
$$
