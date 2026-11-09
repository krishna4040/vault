---
publish: true
title: "Lecture 38: Properties of convex functions-I"
description: In this video, we discuss several properties of convex functions.
created: 2025-04-10
modified: 2026-10-15T16:16:14.558Z
published: 2021-08-23
tags:
  - resource
  - maths
  - convex analysis
  - AI
  - ML
source: https://www.youtube.com/watch?v=-5u9bOYFzKA&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=40
author: IIT Roorkee
lecture: 38
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Properties of convex functions

## Theorem1

if f is a convex function, any local minimum of f in S is a global minimum on S

**Concept**
if x bar is a local minimum of f on S i.e. where N del is a small portion of S known as neighborhood of x
$f(\bar{x})\leq f(x)\forall x\epsilon N_{\delta}(\bar{x})\cap S$
if x bar is is a global minimum of f on s i.e.
$f(\bar{x})\leq f(x)\forall x\epsilon S$

**Proof**
Let f be a convex function on S, let x bar be the point of local min of f which implies
$\exists \delta, f(\bar{x})\leq f(x), \forall x\epsilon N_{\delta}(\bar{x})\cap S$
suppose x bar is not a point of global minimum which implies
$\exists \hat{x}\epsilon S, f(\hat{x})<f(\bar{x})$
the CLC of x bar and x cap is given as, and this point lies in delta reigon of x bar
$\tilde{x} = \lambda \hat{x}+(1-\lambda)\bar{x}, 0<\lambda<1$
Now,
$f(\tilde{x})=f(\lambda \hat{x}+(1-\lambda)\bar{x}) \leq \lambda f(\hat{x})+(1-\lambda)f(\bar{x}) < \lambda f(\bar{x})+(1-\lambda)f(\bar{x})=f(\bar{x})$
this shows that the clc is less than local minimum
Hence this contradicts our initial assumption hence x bar is a point of global minimum

## Theorem2

If S be a convex set and f be a strict convex function, then there is a unique minimizing point of f over S.

**Proof**
suppose x bar belongs to S is a global point of f, let x bar be not a unique point. implies
$\exists \hat{x}\epsilon S, \bar{x}\neq \hat{x},f(\bar{x})=f(\hat{x})$
then the CLC is given as,
$f(\lambda \bar{x}+(1-\lambda)\hat{x}) < \lambda f(\bar{x})+(1-\lambda)f(\hat{x}) = \lambda f(\hat{x})+(1-\lambda)f(\hat{x})=f(\hat{x})$
this is a contradiction, so x bar is a unique global minimum of f.

## Differentiable Functions

if f is differentiable at x bar then for x + x bar,
$f(x+\bar{x})=f(\bar{x})+x^{T}(\nabla f(\bar{x}))+\alpha(\bar{x},x)||x||$
where,
$\lim_{ x \to 0 }\alpha(\bar{x},x)=0 $
if f is twice differentiable,
$f(x+\bar{x})=f(\bar{x})+x^{T}(\nabla f(\bar{x}))+\frac{1}{2}x^{T}\nabla^{2}f(\bar{x})x+\beta(\bar{x},x)||x||^{2}$
where,
$\lim_{ x \to 0 }\beta(\bar{x},x)=0 $

## Theorem3

if f is a function on open convex subset S then f is convex if and only if,
$f(x_{1})-f(x_{2})\geq(x_{1}-x_{2})^{T}\nabla f(x_{2}), \forall x_{1},x_{2}\epsilon S$
_Geometrically_,
A tangent drawn at any point of a convex function it is always below the curve

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]               | April 16, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]               | April 16, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]             | April 17, 2025 |

tab: Previous Lectures
| File                                                                            | created        |
| ------------------------------------------------------------------------------- | -------------- |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]           | April 10, 2025 |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]     | April 10, 2025 |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]   | April 09, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=-5u9bOYFzKA\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=40)
