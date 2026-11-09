---
publish: true
title: Digit Manipulation
description: Digits
created: 2026-10-06
modified: 2026-10-15T16:16:14.554Z
published: 2026-10-15T16:16:14.554Z
tags:
  - maths
  - resource
  - dsa
cover:
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 5
type: permanent
---

# Number

$n = d_{k}d_{k-1}\dots d_{1}d_{0}$

# Iterating Over Digits

```tabs
tab: Last Digit
$$n \% 10$$

tab: Removing Last Digit
$$n \leftarrow \left\lfloor  \frac{n}{10}  \right\rfloor $$
```

**Standard Digit processing Loop**

```cpp
while (n > 0) {
	int digit = n % 10;
	n /= 10;
}
```

Some applications of iterating over digits involve:

````tabs
tab: Sum of digits
$$S(n) = \sum_{i}d_{i}$$
```cpp
sum += digit;
```
- $n \equiv S(n) \% 3,9$
- If $S(n) \mid n$ then n is harshads number

tab: Product of digits
$$P(n) = \prod_{i}d_{i}$$
```cpp
if (digit == 0) return 0;
prod *= digit;
```

tab: Reverse of a number
$$\text{reverse(n)} = d_{0}d_{1}\dots d_{k}$$

```cpp
rev = rev * 10 + digit;
```

> [!Warning] Leading Zeroes
> Zeroes don't appear in reverse form so 1200 -> 21

- $n = \text{reverse(n)} \implies \text{n is a palindrome}$

tab: Digit Frequency
```cpp
++freq[digit];
```
- Total digits in number = $\log_{10}+1$

tab: Extracting kth digit from right
$$\lfloor \frac{n}{10^{k}} \rfloor$$
tab: Removing a digit
Let $p=10^{k}% then $n=\text{higher}.10p+\text{digit}.p+\text{lower}$
$$res = \text{higher}.p+\text{lower}$$

tab: Even and odd digits
check for $$d_{k} \% 2 = 0$$
```cpp
if (d&1) odd++;
else even++;
```
- we can find the sum of even and odd digits in number

tab: Minimum and Maximum Digits
```cpp
mn = min(mn, digit);
mx = max(mx, digit);
```
- we can find second max/min in O(n) time


````

Some Number Types Based on Digit

```tabs
tab: Palindrome Number
$$\exists n, rev(n) = n \implies \text{n is palindrome}$$

tab: Circular Numbers
12345, 23451, 34512, ... are circular numbers

tab: Harshad Number
$$\exists n, S(n) \mid n \implies \text{n is harshad}$$

tab: Automorphic Numbers
$$n^{2} \equiv n \% 10^{k}$$

tab: Armstrong Numbers
$$\exists n, n=\sum_{i}^{k} d_{i}^{k} \implies \text{n is Armstrong}$$

tab: Disarium Numbers
$$\exists n, n=\sum_{i}^{k} d_{i}^{i} \implies \text{n is Disarim}$$

tab: Happy numbers
> If repeated sum of square of digits reaches 1 then its a happy number, we use cycle detetion algorithm to find happy numbers

tab: Polyhedral Numbers
- pronic: $n=k(k+1)$
- Triangular: $n=\frac{k(k+1)}{2}$
- Tetrahedral: $n=\frac{k(k+1)(k+2)}{6}$
- Pentagonal: $n=\frac{k(3k-1)}{2}$
```

# Digital Root

$$$DR(n) = \begin{cases}
0 & n = 0 \\
1 + (n-1)\%9 & n > 0
\end{cases}$$
# Digit operations for larger numbers
For a normal integer: $n \leq 10^{18}$ the number of digits is at most 19 therefore any algorithm that scan all digits is effectively O(1), For a string with L digits its O(L) is the natural baseline.

For $n > 10^{5}$ use string representation.
# Digit DP
$$$
