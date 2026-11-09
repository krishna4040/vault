---
publish: true
title: Array Fundamentals - II
description: foundation
created: 2026-10-15
modified: 2026-10-16T15:51:59.102Z
published: 2026-10-16T15:51:59.102Z
tags:
  - resource
  - dsa
  - arrays
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 2
type: permanent
---

# In Place Modification

Modify an array using its existing storage, without allocating another array proportional to the input size.

An algorithm is typically considered in place when its auxiliary space is $O(1)$.

**Core Techniques**

- Overwrite elements while traversing
- Maintain a write pointer for the next valid position.
- use swaps to rearrange elements
- separate logical size from physical capacity

# Reversal

Reverse the order of elements in an array, $A[i] \leftrightarrow A[n-1-i]$

```cpp
void reverse(vector<int> &a) {
  int left = 0, right = a.size()-1;
  while (left < right) {
    swap(arr[left], arr[right]);
    left++;
    right--;
  }
}
```

**Applications**

- Reversing an entire array or subarray
- Implementing array rotation
- Reversing words or sequences
- supporting two pointer transformations

**Analysis**

1. TC: Linear
2. AS: Constant

> [!info]
> C++ provides with `reverse` from `<algorithm>` for reversing arrays
>
> ```cpp
> reverse(a.begin(), ab.end())
> ```

# Rotation

Rotation shifts elements while preserving their circular order, it can be either left or right defined as:

```tabs
tab: Left
$$LROT(i, k) = (i-k+n) \% n$$

tab: Right
$$RROT(i, k) = (i+k) \% n$$
```

**Reversal Algorithm for Left rotation**

1. reverse the first k elements
2. reverse the remaining n-k elements
3. reverse the entire array
