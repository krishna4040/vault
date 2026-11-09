---
publish: true
title: "Lecture 29 : Minimal Polynomial and Jordan Canonical Form-I"
description: This lecture explains the concept of minimal polynomial and some related results. Jordan blocks in Jordan Canonical Form and their properties are also discussed in this lecture.
created: 2025-04-08
modified: 2026-10-15T16:16:14.557Z
published: 2021-08-17
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=Glp2KqYDmdY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=30
author: IIT Roorkee
lecture: 29
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Minimal Polynomial

**Definition**
For a matrix A of order n, the minimal polynomial m\_A(lam) is a unique monic polynomial of minimal degree such that

$m_{A}(A)=0$
We can say that if for any polynomial f(lam), we have f(A)=0, if and only if

$f(\lambda)=m_{A}(\lambda).q(\lambda)$
for a polynomial q(lam)

**Example**

$$$A=\begin{bmatrix}
2 & 0 \\
0 & 2
\end{bmatrix} \implies A-2I=0\implies m_{A}(\lambda)=\lambda-2$$
$$A = \begin{bmatrix}
2 & 1 \\
0 & 2
\end{bmatrix} \implies (A-2I)^{2}=0\implies m_{A}(\lambda)=(\lambda-2)^{2}$$
**Result**
If A and B are square matrices, A oplus B is defiend to be sqaure matrix as 
$$A\oplus B=\begin{bmatrix}
A & 0 \\
0 & B
\end{bmatrix}$$
and is called the *direct sum* of the matrices A and B
then,
$$c_{A\oplus B}(\lambda)=c_{A}(\lambda).c_{B}(\lambda)$$
$$m_{A\oplus B}(\lambda)=LCM(m_{A}(\lambda),m_{B}(\lambda))$$
where c is characterstic polynomial and m is minimal polynomial
# Jordan Canonical Form
We know that a sq Matrix of order n is diagonazable if and only if it has n linearly independent eigen vectors
Since, not all nXn matrices are diagonalizablr, the JCF gives a more general similarity transformation
*Diagonalization is the special case of JCF*
**Example**
$$A=\begin{bmatrix}
7 & 2 \\
-4 & 1
\end{bmatrix}=\begin{bmatrix}
1 & 1  \\
-1 & -2
\end{bmatrix}\begin{bmatrix}
5 &0 \\
0 & 3
\end{bmatrix}\begin{bmatrix}
1 & 1 \\
-1 & -2
\end{bmatrix}^{-1}$$
$$B=\begin{bmatrix}
1 & 1 \\
0 & 1
\end{bmatrix}\neq PDP^{-1} \text{ as } \lambda=1,1\implies B = SJS^{-1}$$
> [!tip]
> **AM** is the number of time the root is repeated for the characterstic equation
> **GM** is the number of LI eigen vector corrosponding to the eigen value
> $$AM\geq GM$$
> A matrix is diagonizable when AM=GM else we need to go for *JFM*
## Jordan Blocks
A jordan block J_k(lam) is kXk matrix with lamda on the main diagonal and 1 on the super diagonal
$$J_{k}(\lambda_{0})=\begin{bmatrix}
\lambda_{0} & 1 & 0 & 0 & \dots \\
0 & \lambda_{0} & 1 & 0 & \dots \\
. & . & . & . & . \\
. & . & . & . & . \\
. & . & . & \lambda_{0} & 1 \\
0 & 0 & 0 &0 & \lambda_{0}
\end{bmatrix}_{k\times k}$$
**Properties**
- JB has only one eigen value lam = lam_0 with AM=k i.e.

$$|J_{k}(\lambda_{0})-\lambda I_{k}|=(\lambda-\lambda_{0})^{k}$$
- GM of the only value is 1
- if {e1,e2,...en} be the basis of n dimensional space the,
$$J_{k}(\lambda_{0})e_{1}=\lambda_{0}e_{1} \text{ more generally, }J_{k}(\lambda_{0})e_{i}=\lambda_{0}e_{i}+e_{i-1},i=1,2,\dots,k$$


## JCF
A JCF is a block diagonal matrix of order n:
$$J=\begin{bmatrix}
J_{k_{1}}^{\lambda_{1}} & 0 & 0 & 0 &. \\
0 & J_{k_{2}}^{\lambda_{2}} & 0 & 0 & . \\
. & . & . & . & . \\
0 & 0 & 0 & J_{k_{m-1}}^{\lambda_{m-1}} & 0 \\
0 & 0 & 0 & 0 & J_{k_{m}}^{\lambda_{m}}
\end{bmatrix}_{n\times n}$$
such that k1+k2+....+km=n and 0 denotes zero matrix
**Properties**
$$|J-\lambda I|=\prod_{i=1}^{m}(\lambda_{i}-\lambda)^{k_{i}}$$
The JCF has m eigen vectors X1,X2,...,Xm each corresponds to lamda on the jordan block

**Example**
$$A=\begin{bmatrix}
1 & 1 & 1 \\
0 & 1 & 1 \\
0 & 0 & 1
\end{bmatrix}\implies\lambda=1,1,1 \text{ and } X=(1,0,0)^{T} \implies AM\neq GM$$
Hence JCF of A is of order AM and has Jordan blocks = GM
$$J = [J_{3}^{1}] = \begin{bmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
0 & 0 & 1
\end{bmatrix}$$


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]                                     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]]                                   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]                                     | April 09, 2025 |

tab: Previous Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                                       | April 08, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=Glp2KqYDmdY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=30)
$$$
