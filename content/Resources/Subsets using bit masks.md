---
publish: true
title: Subsets using bit masks
created: 2026-10-13
modified: 2026-10-16T15:51:59.103Z
published: 2026-10-16T15:51:59.103Z
tags:
  - resource
  - dsa
  - bits
description: ""
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 6
type: permanent
---

# Core Idea

A bitmask represents a subset by using the bits of an integer to indicate which element is selected.

suppose we have a set: $A=\{ a,b,c \}$, Assign one bit to each element

| Bit position | Element | Meaning when bit = 1 |
| ------------ | ------- | -------------------- |
| 0            | a       | include a            |
| 1            | b       | include b            |
| 2            | c       | include c            |

For Mask `101` means following:

- Bit 0 is on → include a
- Bit 1 is off → exclude b
- Bit 2 is on → include c
  means `101` represents the subset $\{ a,c \}$

| Mask | Subset        |
| ---- | ------------- |
| 000  | $\phi$        |
| 001  | $\{ a \}$     |
| 010  | $\{ b \}$     |
| 011  | $\{ a,b \}$   |
| 100  | $\{ c \}$     |
| 101  | $\{ a,c \}$   |
| 110  | $\{ b,c \}$   |
| 111  | $\{ a,b,c \}$ |

# Algorithm

1. A set with n elements have a total of $2^{n}$ subsets, so to represent all subsets of a set using bits we need mask of width $w_{M}=n$
2. This mask can take all values defined in the range given width that is from $[0, 2^{w}]$
3. For each mask, we check which bit position are set, and combination of those position gives corresponding subset to that mask

```cpp
vector<pair<vector<int>, int>> subset(vector<int> &a) {
	int n = a.size();
	vector<pair<vector<int>, int>> res;
	for (int mask = 0; mask <= (1 << n); mask++) {
		// a mask corresponds to one of 2^n subset of array
		vector<int> sset;
		int sum = 0;
		for (int i = 0; i <= n; i++) {
			// check if ith position is set in mask
			if (mask & (1<<i)) {
				sset.push_back(a[i]);
				sum += a[i];
			}
		}
		res.push_back({sset, sum});
	}
	return res;
}
```

**Analysis**: Time complexity for this algorithm is $O(2^{n})$

> [!info] Variation
> Subset of size k can be found by considering mask where
>
> $$
> popcount(mask)=k
> $$

# Enumerating submasks

If a mask is give as M has k set bits or popcount of M is k, then submasks corresponding to mask M are $2^{k}$

Submasks, the unset bit in mask M remains in place and then all combination of remaining set bits are the associated submasks of mask M

# Array Patterns

Starting from Mask M = 0, we can form desired subsets using following operations:

| operation                                      | syntax                   |
| ---------------------------------------------- | ------------------------ |
| check weather position `i` is selected in mask | $mask \& (1\ll i)\neq 0$ |
| select index i                                 | $mask\|=(1\ll i)$        |
| deselect index i                               | $mask \&=\~(1\ll i)$     |
| toggle index i                                 | $mask \oplus=(1\ll i)$   |
