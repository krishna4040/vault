---
publish: true
title: Array Fundamentals - I
description: Foundation
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
lecture: 1
type: permanent
---

# Representation

An array stores sequence of elements of the same type in a contiguous block of memory.

For an array $A$ with Base Address $B$, element size $w$, and zero-based index $i$:

$$
Address(A[i]) = B+i\times w
$$

**Properties**

- Direct Access by index takes constant time
- Elements are stored contiguously
- inserting or removing elements in middle generally requires shifting elements

# Indexing

For an Array containing $n$ elements, valid indices are $0\leq i<n$

| Expression  | Meaning                               |
| ----------- | ------------------------------------- |
| $A[0]$      | First element                         |
| $A[n-1]$    | Last element                          |
| $A[i]$      | Element at index `i`                  |
| $A[i\pm 1]$ | Next and Prev element, if they exists |
| $A[n-1-i]$  | Symmetric Pair of $A[i]$              |

# Traversal

Traversal means visiting elements systematically to read, process or modify them.

````tabs
tab: Standard
```cpp
for (int i=0; i < n; ++i) {}
```
tab: Reverse
```cpp
for (int i = n-1; i >= 0; --i) {}
```
tab: Range based
```cpp
for (int x: arr) {}
```
````

# Insertion

Insertion places a new element at a specified position

```cpp
void insert(int arr[], int &n, int cap, int pos, int val) {
  if (n >= cap || pos < 0 || pos > n) return;
  for (int i = n; i > pos; --i) arr[i] = arr[i-1];
  arr[pos] = val;
  ++n;
}
```

| Position  | Time Complexity |
| --------- | --------------- |
| Beginning | $O(n)$          |
| Middle    | $O(n)$          |
| Last      | $O(1)$          |

# Deletion

Deletion removes an element at index p. elements to its right shift left to fill the gap

```cpp
void delete(int arr[], int &n, int pos, int val) {
  if (pos < 0 || pos > n) return;
  for (int i = pos; i < n-1; ++i) arr[i] = arr[i+1];
  --n;
}
```

| Position  | Time   |
| --------- | ------ |
| Beginning | $O(n)$ |
| Middle    | $O(n)$ |
| End       | $O(1)$ |

# Dynamic Arrays

```cpp
#include <iosteam>
#include <vector>
using namespace std;

int main() {
  vector<int> v = {1, 2, 3};
}
```

| Operation         | Complexity |
| ----------------- | ---------- |
| `v[i]`            | $O(1)$     |
| `v.size()`        | $O(1)$     |
| `v.push_back(x)`  | $O(1)$     |
| `v.pop_back()`    | $O(1)$     |
| `v.insert(it, x)` | $O(n)$     |
| `v.erase(it)`     | $O(n)$     |
