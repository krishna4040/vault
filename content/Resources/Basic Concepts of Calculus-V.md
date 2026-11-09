---
publish: true
title: "Lecture 35 : Basic Concepts of Calculus-V"
description: In this lecture, we discuss about Chain rule and the several formulations.
created: 2025-04-10
modified: 2026-10-15T16:16:14.552Z
published: 2021-08-19
tags:
  - resource
  - maths
  - calculus
  - AI
  - ML
source: https://www.youtube.com/watch?v=fEP5yqdwArE&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=36&t=495s
author: IIT Roorkee
lecture: 35
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Chain rule

$z=f(y) \text{ and } y=\phi(x) \implies \frac{dz}{dx}=\frac{dz}{dy} \frac{dy}{dx}$
similarly extending this concept,
$z=f(x_{1},x_{2},\dots,x_{n}),x_{i}=x_{i}(t)\implies \frac{dz}{dt}=\sum_{i=1}^{n} \frac{\delta z}{\delta x_{i}} \frac{dx_{i}}{dt}$

## Chain Rule when dependent variables are function of two variable

$z=f(x,y),x=g(r,s),y=h(r,s)\implies \frac{\delta z}{\delta r}=\frac{\delta z}{\delta x} \frac{\delta x}{\delta r}+\frac{\delta z}{\delta y} \frac{\delta y}{\delta r}; \frac{\delta z}{\delta s}=\frac{\delta z}{\delta x} \frac{\delta x}{\delta s}+\frac{\delta z}{\delta y} \frac{\delta y}{\delta s}$
similarly extending this concept,
$z=f(x_{1},x_{2},\dots x_{n}),x_{i}=g_{i}(r,s)\implies \frac{\delta z}{\delta r}=\sum \frac{\delta z}{\delta x_{i}} \frac{\delta x_{i}}{\delta r} \text{ and } \frac{\delta z}{\delta s}=\sum \frac{\delta z}{\delta x_{i}} \frac{\delta x_{i}}{\delta s}$

# Change of variable

$z=f(x,y),x=g(r,s),y=h(r,s)\implies \frac{\delta z}{\delta r}=\frac{\delta z}{\delta x} \frac{\delta x}{\delta r}+\frac{\delta z}{\delta y} \frac{\delta y}{\delta r}; \frac{\delta z}{\delta s}=\frac{\delta z}{\delta x} \frac{\delta x}{\delta s}+\frac{\delta z}{\delta y} \frac{\delta y}{\delta s}$
These two equations forms a system of linear equation and using cramers rule we get,
$z_{x}=f_{x}=\frac{1}{J}\left[ \frac{\delta(f,y)}{\delta (r,s)} \right]$
$z_{y}=f_{y}=-\frac{1}{J}\left[ \frac{\delta(f,x)}{\delta(r,s)} \right]$
where,

$$$J=|\begin{bmatrix}
\frac{\delta x}{\delta r} & \frac{\delta y}{\delta s} \\
\frac{\delta x}{\delta s} & \frac{\delta y}{\delta r}
\end{bmatrix}| = \frac{\delta(x,y)}{\delta(r,s)}$$
**Property of Jacobian**
$$J=\frac{\delta(x,y)}{\delta(u,v)} \text{ and } J'=\frac{\delta(u,v)}{\delta(x,y)} \implies JJ'=1$$
Chain rule holds
$$\frac{\delta(u,v)}{\delta(x,y)}=\frac{\delta(u,v)}{\delta(r,s)} \frac{\delta(r,s)}{\delta(x,y)}$$


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]                 | April 10, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]               | April 16, 2025 |

tab: Previous Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]                                     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]]                                   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]                                     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=fEP5yqdwArE&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=36&t=495s)
$$$
