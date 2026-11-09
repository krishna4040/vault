---
publish: true
title: "Lecture 10: Special matrices and Properties"
description: In this lecture, we have discussed about quadratic form, Rayleigh Quotient, Positive(semi-) Definite and Negative(Semi-) Definite matrices.
created: 2025-04-02
modified: 2026-10-15T16:16:14.559Z
published: 2021-07-15
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=Scs9rp7SMfQ&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=12
author: IIT Roorkee
lecture: 10
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Quadratic form

Let $A\epsilon R^{n\times n}$
be a symmetric matrix. The expression $q(X)=X^{T}AX$ is called Quadratic form associated with matrix A

**Example**

$$$A=\begin{bmatrix}
1 & -1 & 2 \\
-1 & 3 & 1 \\
2 & 1 & 4
\end{bmatrix}$$
$$q(X)=\begin{bmatrix}
x_{1}&x_{2}&x_{3}
\end{bmatrix}A\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{bmatrix}=1.x_{1}^{2}+3.x_{2}^{2}+4.x_{3}^{2}+(-1+-1)x_{1}x_{2}+(2+2)x_{1}x_{3}+(1+1)x_{2}x_{3}$$
Similarly we can derive the matrix from a quadratic form
## Rayleigh quotients
for a n X n real matrix A, we have
$$R_{A}(X)=\frac{X^{T}AX}{X^{T}X}, \text{ where } X\neq 0$$
#### Properties of Rayleigh quotients
- *scaler invariance*: For X not equal to 0 and any scaler alpha not equal to 0, $$R_{A}(X)=R_{A}(\alpha X)$$
- if X is an eigen vector of A with eigen value lambda, then $$R_{A}(X)=\lambda$$
- $$\lambda_{min}(A)=min_{x\neq 0}R_{A}(X)$$
- $$\text{ for any X such that } ||X||_{2}=1, \text{ we have } \lambda_{min}(A)\leq X^{T}AX\leq\lambda_{max}(A)$$
- For any X not equal to zero we have, $$\lambda_{min}(A)\leq R_{A}(X)\leq\lambda_{max}(A)$$
## Positive semi definite (PSD) Matrices
A symmeteic matrix A is said to be PSD if for all, X belongs to Rn we have,
$$q(X)=X^{T}AX\geq 0$$
If $$q(X)=X^{T}AX>0$$
then A is said to be *Positive Definite (PD)*
> [!tip]
> Write quadratic form of matrix as sum of square to check if matrix is PSD or not
#### Properties
- A symmetric matrix is PSD if and only if its all eigen values are positive
- A symmetric matrix is PSD if its all pivots are positive
- For any square matrix A, AA^T is PSD, moreover id nullspace(A)={0}, then AA^T is PD
- If A is PSD and e>0, then A+eI is PD

#### Geometry of PD quadratic forms
The isocontour of q(X)=X^T AX are *ellipsoids* s.t. the axes points in the direction of the eigen vectors of A, and the radii of these axes are proportional to the inverse sqaure root of the corresponding eigen values.

---
# Related

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                     | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]         | April 02, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]]                                             | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]                                                   | March 30, 2025 |

`````

---
# References

![](https://www.youtube.com/watch?v=Scs9rp7SMfQ)
$$$
