---
publish: true
title: "Lecture 33: Basic Concepts of Calculus-III"
description: In this lecture, we discuss functions of n variables, gradient and directional derivatives.
created: 2025-04-09
modified: 2026-10-15T16:16:14.551Z
published: 2021-08-18
tags:
  - resource
  - maths
  - calculus
  - AI
  - ML
source: https://www.youtube.com/watch?v=1lmZIAN2vb0&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=34
author: IIT Roorkee
lecture: 33
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Function of n variables

Let S is a subset of Rn. A real valued function f on S is a rule that assigns a real number w to every element of S given as
$w = f(x_{1},x_{2},\dots ,x_{n}) \forall(x_{1},x_{2},\dots x_{n})\epsilon S$
so x1,x2,...,xn are called _Independent variables_ and w is called _dependent variable_

**Domain**
**Codomain**
**Range**

# Partial Derivatives

Consider a function of n variables. Then, the partial derivative of f wrt an independent variable xi for any i is given as
$f_{x_{i}}=\frac{\delta f}{\delta x_{i}}=\lim_{ \Delta x_{i} \to 0 } \frac{f(x_{1},x_{2},\dots,x_{i}+\Delta x_{i},\dots,x_{n})-f(x_{1},x_{2},\dots x_{n})}{\Delta x_{i}} $

# Gradient

The single most important concept from calculus in the context of ML is _gradient_. Gradient generalize derivatives to scalar functions of several variables

**Definition**
The gradient of a function f:Rn->R, is given as

$$$\nabla f=\begin{bmatrix}
\frac{\delta f}{\delta x_{1}} & \frac{\delta f}{x_{2}} & \dots & \frac{\delta f}{\delta x_{n}}
\end{bmatrix}^{T}$$
i.e.
$$[\nabla f]_{i}=\frac{\delta f}{\delta x_{i}}$$
# Directional Derivatives
The partial derivate is a measure of rate of change of function along standard domain direction, what if we need to measure rate of change along a arbitrary unit vector hence we define
$$\left( \frac{df}{ds} \right)_{p_{0},\vec{u}}=\lim_{ s \to 0 } \frac{f(x_{0}+su_{1}, y_{0}+su_{2})-f(x_{0},y_{0})}{s} $$
where
$$\vec{u}=u_{1}\hat{i}+u_{2}\hat{j} \text{ and } P_{0}=(x_{0},y_{0})$$
Relation with standarad Derivatives
Equation of line in 2D plane in direction of unit vector u is given as
$$\frac{x-x_{0}}{u_{1}}=\frac{y-y_{0}}{u_{2}}=s \implies x = x_{0}+su_{1}, y=y_{0}+su_{2}$$
$$\left( \frac{df}{ds} \right)_{p_{0},\vec{u}}=\left( \frac{\delta f}{\delta x} \right)_{p_{0}} \frac{dx}{ds} + \left( \frac{\delta f}{\delta y} \right)_{p_{0}} \frac{dy}{ds}=\nabla f_{p_{0}}.\vec{u}$$
Maximum/ Minimum change of f in a vector
$$\left( \frac{df}{ds} \right)_{p_{0},\vec{u}}=|\nabla f_{p_{0}|}\cos\theta$$
*Maximum* theta is 0, u is in direction of gradient
*Minimum* theta is 180, u is in opposite direction of gradient
or grad of f is in the direction of *steepest ascent* from x and -ve of grad of f points in the direction of *steepest descent* from x


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]         | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]           | April 10, 2025 |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]                 | April 10, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |

tab: Previous Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]                                     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                         | April 08, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=1lmZIAN2vb0&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=34)
$$$
