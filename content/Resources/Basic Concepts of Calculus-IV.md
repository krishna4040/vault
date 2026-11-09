---
publish: true
title: "Lecture 34 : Basic Concepts of Calculus-IV"
description: "In this lecture, we discuss several concepts of calculus: Jacobian and Hessian."
created: 2025-04-09
modified: 2026-10-15T16:16:14.552Z
published: 2021-08-19
tags:
  - resource
  - maths
  - calculus
  - AI
  - ML
source: https://www.youtube.com/watch?v=NMCom1iSIkQ&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=36
author: IIT Roorkee
lecture: 34
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Jacobian

The Jacobian of f:Rn->Rm is a matrix of first order partial derivatives, given as

$$$J_{f}=\begin{bmatrix}
\frac{\delta f_{1}}{\delta x_{1}} & \frac{\delta f_{1}}{\delta x_{2}} & \dots & \frac{\delta f_{1}}{\delta x_{n}} \\
\frac{\delta f_{2}}{\delta x_{1}} & \frac{\delta f_{2}}{\delta x_{2}} & \dots & \frac{\delta f_{2}}{\delta x_{n}} \\
. & . & \dots & . \\
\frac{\delta f_{m}}{\delta x_{1}} & \frac{\delta f_{m}}{\delta x_{2}} & \dots & \frac{\delta f_{m}}{\delta x_{n}}
\end{bmatrix} \implies [J_{f}]_{i,j}=\frac{\delta f_{i}}{\delta x_{j}}$$
In terms of gradient we have,
$$J_{f}=\begin{bmatrix}
\nabla f_{1} \\
\nabla f_{2} \\
. \\
. \\
\nabla f_{m}
\end{bmatrix}$$

for m = 1, we have
$$J_{f}^{T}=\nabla f$$
where
$$f(x_{1},x_{2},\dots,x_{n})=(f_{1},f_{2},\dots,f_{m})$$
# Hessian Matrix
The Hessian matrix of f is a matrix of second order partial derivatives given as
$$H=\nabla^{2}f=\begin{bmatrix}
\frac{\delta^{2}f}{\delta x_{1}^{2}} & \frac{\delta^{2}f}{\delta x_{1}\delta x_{2}} & \dots & \frac{\delta^{2}f}{\delta x_{1}\delta x_{n}} \\
\frac{\delta^{2}f}{\delta x_{2}\delta x_{1}} & \frac{\delta^{2}f}{\delta x_{2}^{2}} & \dots & \frac{\delta^{2}f}{\delta x_{2}\delta x_{n}} \\
. & . & \dots & . \\
\frac{\delta^{2}f}{\delta x_{n}\delta x_{1}} & \frac{\delta^{2}f}{\delta x_{n}\delta x_{2}} & \dots & \frac{\delta^{2}f}{\delta^{2}x_{n}^{2}}
\end{bmatrix} \implies [\nabla^{2}f]_{i,j}=\frac{\delta^{2}f}{\delta x_{i}\delta x_{j}}$$
**Remark**
If all the partial derivatives fx, fy, fxy, fyx all exist and are all continuous, then by *Eulers's theorem*, the order of differentiation is interchangable, i.e.
$$f_{xy}=f_{yx} \forall x,y$$
In such case, the Hessian matrix becomes a symmetric matrix

---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                  | created        |
| ------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]           | April 10, 2025 |
| [[Resources/Convex Sets and Functions.md\|Convex Sets and Functions]]                 | April 10, 2025 |
| [[Resources/Properties of convex functions-I.md\|Properties of convex functions-I]]   | April 10, 2025 |
| [[Resources/Properties of Convex functions-II.md\|Properties of Convex functions-II]] | April 15, 2025 |
| [[Resources/Introduction to Optimization.md\|Introduction to Optimization]]           | April 16, 2025 |

tab: Previous Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]]                                   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]                                     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=NMCom1iSIkQ&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=36)
$$$
