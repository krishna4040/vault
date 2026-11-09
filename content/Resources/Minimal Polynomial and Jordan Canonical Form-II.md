---
publish: true
title: "Lecture 30 : Minimal Polynomial and Jordan Canonical Form-II"
description: In this lecture, we have discussed about Jordan canonical transformation, generalized eigenvectors and the relation between minimal polynomial and JCF of a matrix.
created: 2025-04-09
modified: 2026-10-15T16:16:14.557Z
published: 2021-08-17
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=D_PFhnlFfLc&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=31
author: IIT Roorkee
lecture: 30
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# JCF transformation

Every Matrix A of order n is similar to a Jordan Canonical Form J s.t.
$A_{n\times n}=SJS^{-1}$
Where S is the matrix containing the eigen vectors and generalized eigenvectors of A.

## Generalized Eigenvector

If A is a nXn matrix. a generalized eigenvector of A corresponding to the eigen value lam is a non zero vector x satisfying
$(A-\lambda I)^{p}x=0$
for some positive integer p such that
$(A-\lambda I)^{p-1}\neq0$
i.e.
$x \epsilon Ker(A-\lambda I)$
-----------------------------

$$$B = \begin{bmatrix}
1 & 0 & 1 \\
0 & 1& 1 \\
0 & 0 & 1
\end{bmatrix} \implies \lambda=1,1,1 \implies X=(1,0,0)^{T} \text{ and } (0,1,0)^{T}$$
$$S = \begin{bmatrix}
X_{1}^{T} & X_{2}^{T} & X
\end{bmatrix}$$
where X is the generalized eigen vector, we have
$$(B-I)X_{1}=(B-I)X_{2}=0$$
so let $$(B-I)^{2}X=0 \implies(B-I)X=X_{2}$$
# Application in ML
The J matrix is the sparse matrix or sparse form of A, for any matrix we can consider its sparse form have some operations and then reconstruct it


---
# Related


---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                            | created        |
| ------------------------------------------------------------------------------- | -------------- |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]     | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-II.md\|Basic Concepts of Calculus-II]]   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-III.md\|Basic Concepts of Calculus-III]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-IV.md\|Basic Concepts of Calculus-IV]]   | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-V.md\|Basic Concepts of Calculus-V]]     | April 10, 2025 |

tab: Previous Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]                 | April 08, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                                       | April 08, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=D_PFhnlFfLc&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=31)
$$$
