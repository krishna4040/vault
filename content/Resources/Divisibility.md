---
publish: true
title: Divisibility
description: Fundamentals
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
lecture: 0
type: permanent
---

# Divisibility (Definition)

$b \mid a \implies \exists k \in \mathbb{Z}: a = bk$

| Property      | Definition                                        |
| ------------- | ------------------------------------------------- |
| Symmetry      | $a \mid a$                                        |
| Associative   | $a \mid b \cap b \mid c \implies a \mid c$        |
| Distributive  | $a \mid b \cap a \mid c \implies a \mid (b\pm c)$ |
| Euclids Lemma | $a \mid b \cap a \mid c \implies a \mid bc$       |
| GCD           | $a \mid b \implies a \% b = 0$                    |
| Congruence    | $a \mid b \implies b \equiv 0 \% a$               |
| identity      | $1 \mid a$                                        |
| Divisor       | $d \mid a \cap d \mid b \implies d \mid ax + by$  |

# Factors and Multiples

```tabs
tab: Factor
$$\exists d \mid n \implies \text{d is factor / divisor of n}$$

tab: Multiple
$$\forall n \ \exists \ kn \text{ multiples}$$
```

## Factor Pair

$\forall d \text{ of n, } \frac{n}{d} \text{ is a pair}$
**Factor Enumeration**
It is a time optimization strategy to reduce search from `n` to $\sqrt{ n }$ It states that,
$\forall d \leq \sqrt{ n }, \ \frac{n}{d} \text{ can be determined}$

# Prime Numbers

$P = \{ n \in \mathbb{N}: n > 1 \cap \forall d \in \mathbb{N}, d \mid n \implies (d = 1 \cup d = n) \}$
**Properties**

- `0` and `1` are Neither prime nor composite
- `2` is the smallest only even prime
- There are $\infty$ Primes
- $\forall p > 3: 6k\pm 1$

## Primality Test

# Composite Numbers

$C = \{ n \in N : n > 1 \cap \exists d \in \mathbb{N}, 1 < d < n \ \cap d \mid n \}$

> [!NOTE] Interpretation
> It states that there exists a divisor of n strictly between 1 and n excluding those

$n = ab$

- $a = p_{1}, b = p_{2} \implies \text{n is semiprime}$
- $a = b \implies \text{n is perfect square}$

## Prime Factorization form of composite numbers

Every Composite number can be written in the following form, this is known as prime factorization form:
$n = p_{1}^{a_{1}}p_{2}^{a_{2}}\dots p_{k}^{a_{k}} = \prod_{i}p_{i}^{a_{i}}$

- $\forall a_{i} = 1 \implies \text{n is square free number}$
- $\forall a_{i} > 2 \implies \text{n is powerful number}$
- Total Distinct Prime Divisors = `k`
- Total Prime Divisors = $\sum_{i}a_{i}$

Some important details that can be derived for all divisors of n from this form

```tabs
tab: Number
$$\tau(n) = \prod_{i}(a_{i}+1)$$
- Pairs = $\frac{\tau(n)}{2}$
- Perfect Divisors = $\tau(n)-1$

tab: Sum
$$\sigma(n) = \prod_{i} \frac{p_{i}^{a_{i}+1}-1}{p_{i}-1}$$
- $n = \frac{\sigma(n)}{2} \implies \text{n is perfect}$
- $n > \frac{\sigma(n)}{2} \implies \text{n is abundant}$
- $n < \frac{\sigma(n)}{2} \implies \text{n is deficient}$

tab: Product
$$P_{n} = \begin{cases}
n^{\tau(n)/2} & n \neq k^{2} \\
n^{\tau(n)-1/2}.\sqrt{ n } & n = k^{2}
\end{cases}$$
- $n = p \implies P_{n} = p$
```

Some other details that can be obtained from this form are:

```tabs
tab: Euler toient Function
It Tells the total number of coprimes with n

$$\phi(n) = n\prod_{p}\left( 1-\frac{1}{p} \right)$$
- $\sum_{d\mid n}\phi(d) = n$
- $\phi(p^{k}) = p^{k} - p^{k-1}$

tab: Mobilus Function
$$
\mu(n) = \begin{cases}
1 & n = 1 \\
0 & p^{2} \mid n \\
-1^{k} & \text{n is prod of k distinct primes}
\end{cases}
$$
```

### Dirichlet Convulation

> All the above properties can be defined using this convulation

$f * g (n) = \sum_{d\mid n}f(d)g\left( \frac{n}{d} \right)$

- $1(n) = 1, id(n) = n$
- $\tau = 1 * 1 = \sum_{d\mid n}1 = \tau(n)$
- $\sigma = id*1 = \sum_{d\mid n}d = \sigma(n)$
- $\phi*1 = id \implies \sum_{d\mid n}\phi(d) = n$
- $\phi = id * \mu$
