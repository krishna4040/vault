---
publish: true
title: "Lecture 21: Least Square Approximation and Minimum Normed Solution"
description: In this lecture, we have discussed over-determined and under-determined system, least square approximation, pseudo-inverse and minimum normed solution.
created: 2025-04-04
modified: 2026-10-15T16:16:14.556Z
published: 2021-08-16
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=0Dg_yvVgmQo&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=22
author: IIT Roorkee
lecture: 21
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# System of Linear equations

Consider a system of linear equations $AX=b$
where A is of order mXn is _Cofficient matrix_, X belongs to Rn be unknown vector and b belongs to Rm is RHS then

- if m >> n, then system is called _Overdetermined system_, number of observations is more than number of unknown variables
- if m << n, then the system is called _Underdetermined system_, number of observations is less than number of unknown variables

**Overdetermined systems**
$x_{1}+2x_{2}=5$
$x_{1}-x_{2}=1$
$3x_{1}+4x_{2}=1$
$x_{1}+5x_{2}=9$
m = 4, n = 2, exact solution is difficut to find, so we look for Approximate solution
Matrix form is given as,

$$$A = \begin{bmatrix}
1 & 2 \\
1 & -1 \\
3 & 4 \\
1 & 5 \\
\end{bmatrix}, X=\begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix},b=\begin{bmatrix}
5 \\
1 \\
7 \\
9
\end{bmatrix}$$
**Underdetermined system**
$$x_{1}+x_{2}-x_{3}=2$$
$$2x_{1}+x_{2}+x_{3}=4$$
Matrix form is given as,
$$A=\begin{bmatrix}
1 & 1 & -1 \\
2 & 1 & 1
\end{bmatrix}, X = \begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{bmatrix},b=\begin{bmatrix}
2 \\
4
\end{bmatrix}$$
In this case we have infinite solutions, but there is special case of solution that is minimum norm solution for underdetermined equations

# Overdetermined system
- Generally, we often run into the problem that we have more than two points and try to represent our points with one straight line. However, the data points do not lie on a straight line. We can try infinitely many straight lines to fit all the data points. Under this situation, the problem of least squares is to find the line that fits the data the best. This is called *Linear regression or Line fitting*
- The best fitting line is often called the *lease squares line* or the *regression line*
- *Residual*: The directed distances between the observed data points and the corresponding points on the model line is called Residual
- To obtain the best fitting line, we need to minimize the sum of the squares of the resuduals

**Least Square approximation**
Given AX=b where A is mXn real matrix and it is a overdetermined system, Here in LSA we solve the optimisation problem, minimise euclidean morm between A and B
$$arg \space min||AX-b||_{2}^{2}$$
Let consider a overdetermined system in x1 and x2 as,
$$a_{11}x_{1}+a_{12}x_{2}=b_{1}$$
$$a_{21}x_{1}+a_{22}x_{2}=b_{2}$$
$$a_{31}x_{1}+a_{32}x_{2}=b_{3}$$
then Euclidean norm of A and b is given as
$$||AX-b||_{2}^{2}=(a_{11}x_{1}+a_{12}x_{2}-b_{1})^{2}+(a_{21}x_{1}+a_{22}x_{2}-b_{2})^{2}+(a_{31}x_{1}+a_{32}x_{2}-b_{3})^{2} = E$$
So minimising conditions are,
$$\frac{\delta E}{\delta x_{1}}=0, \frac{\delta E}{\delta x_{2}}=0$$
finding x1,x2:
$$AX = b \implies A^{T}AX=A^{T}b \implies X = (A^{T}A)^{-1}A^{T}b$$
here,
$$A^{+}=(A^{T}A)^{-1}A^{T}$$
is known as pusedo inverse of A and $$X = A^{+}b$$ is the least square solution.
# Underdetermined solutions
- Consider the linear system AX=b, which is underdetermined, we have 'n-m' free variables. Assigning any arbitrary values to these variables lead to a solution of AX=b
- Therefore, we can have infinitely many solutions of the system AX=b
- A minimum normed solution *MNS* is that which minimize the ||X|| among these infinite solution

**MNS**
$$min_{x}||X||, \text{ subject to }, AX=b$$
$$min_{x}||AX-b||_{2}^{2}+||X||_{2}^{2}$$
finding X for given optimisation,
$$X = A^{T}(AA^{T})^{-1}b$$
Here psuedo inverse of A is also known as left psuedo inverse given as
$$A^{+}=A^{T}(AA^{T})^{-1}$$

---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                               | April 04, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                       | April 05, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                         | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |

tab: Previous Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]         | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]         | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |

`````
---
# References
![](https://www.youtube.com/watch?v=0Dg_yvVgmQo)  
$$$
