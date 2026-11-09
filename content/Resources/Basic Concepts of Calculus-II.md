---
publish: true
title: "Lecture 32: Basic Concepts of Calculus-II"
description: "This lecture discusses further concepts of calculus: limits, continuity and differentiability of functions of one variable."
created: 2025-04-09
modified: 2026-10-15T16:16:14.551Z
published: 2021-08-18
tags:
  - resource
  - maths
  - calculus
  - AI
  - ML
source: https://www.youtube.com/watch?v=5cQwVs6UcCE&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=34
author: IIT Roorkee
lecture: 32
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Limit of a function

Let f:X->Y be a function. Then,
$\lim_{ x \to a }f(x)=L \implies \lim_{ x \to a^{+} }f(x) = \lim_{ x \to a^{-} }f(x)$

# Continuity at a point

Let f:X->Y be a function. Then, f is said to be continuous ar point say x = a if
$\lim_{ x \to a }f(x)=f(a) $
**Properties of CFs**
Let f and g be two real functions, continuous at x = a. Let alpha be a real number. then,
$f\pm g, \alpha f, fg, \frac{f}{g} \text{ is continuous at } x=a \text{ provided } g(a)\neq0 \text{ for last case}$

# Differentiablility of a function

Let f be a real valued function on an open interval (a,b) and let c belongs to (a,b) then f is said to be differentiable at c if,
$\lim_{ x \to c } \frac{f(x)-f(c)}{x-c} \text{ exists} $
and is denoted by
$f'(c) \text{ or } \frac{d}{dx}f(x)\text{ at x = c}$
tweak,
$\lim_{ x \to c } \frac{f(x)-f(c)}{x-c} \text{ exists} \implies \lim_{ x \to c^{-}}\frac{f(x)-f(c)}{x-c} = \lim_{ x \to c^{+} }\frac{f(x)-f(c)}{x-c} \implies \lim_{ h \to 0 }\frac{f(c-h)-f(c)}{-h} = \lim_{ h \to 0 } \frac{f(c+h)-f(c)}{h}$
Geometrically,
if f is differentaible at a point P, there exisits a unique _tangent_ at P.

**Basic Rules**
$(\alpha f(x))'=\alpha f'(x)$
$(f(x)\pm g(x))'=f'(x)\pm g'(x)$
$(f(x)g(x))'=f(x)g'(x)+g(x)f'(x)$
$\left( \frac{f(x)}{g(x)} \right)'=\frac{f'(x)g(x)-f(x)g'(x)}{g(x)^{2}}, g(x)\neq0$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]]     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]       | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]         | April 10, 2025 |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]               | April 10, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]] | April 10, 2025 |

tab: Previous Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                         | April 08, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                       | April 05, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=5cQwVs6UcCE\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=34)
