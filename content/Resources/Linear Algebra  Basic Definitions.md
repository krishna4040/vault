---
publish: true
title: "Deep Learning(CS7015): Lec 6.2 Linear Algebra : Basic Definitions"
description: lec06mod02
created: 2025-04-23
modified: 2026-10-15T16:16:14.556Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/FsWX2c7Q6Qg/maxresdefault.jpg
source: https://www.youtube.com/watch?v=FsWX2c7Q6Qg&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=45
author: IIT Roorkee
cover: https://i.ytimg.com/vi/FsWX2c7Q6Qg/maxresdefault.jpg
lecture: 6.2
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# LA ~ Basics

# Basis

[[Basis and Dimension]]

$$$z=\alpha_{1}u_{1}+\alpha_{2}u_{2}+\dots+\alpha_{n}u_{n}\implies \begin{bmatrix}
z_{1} \\
z_{2} \\
. \\
. \\
z_{n}
\end{bmatrix}=\begin{bmatrix}
u_{11} & u_{21} & . & . & u_{n1} \\
u_{21} & u_{22} & . & . & u_{n_{2}} \\
. & . & . & . & . \\
. & . & . & . & . \\
u_{1n} & u_{2n} & . & . & u_{nn}
\end{bmatrix}\begin{bmatrix}
\alpha_{1} \\
\alpha_{2} \\
. \\
. \\
\alpha_{n}
\end{bmatrix}$$
for orthonormal basis
![[System/Assets/Pasted image 20250423205144.png]]
# Relation with Eigen vectors
The Eigen vectors of a matrix $A\epsilon \mathbb{R}^{n\times n}$ having distinct Eigen values are linearly independent
The eigenvectors of a square symmetric matrix are orthogonal

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                        | created        |
| --------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Eigenvalue Decompositon.md\|Eigenvalue Decompositon]]                                                           | April 24, 2025 |
| [[Resources/Principal Component Analysis and its Interpretations.md\|Principal Component Analysis and its Interpretations]] | April 24, 2025 |
| [[Resources/Regularization.md\|Regularization]]                                                                             | March 10, 2025 |
| [[Resources/Vectorial Representation of Words.md\|Vectorial Representation of Words]]                                       | March 10, 2025 |
| [[Resources/CNN.md\|CNN]]                                                                                                   | March 10, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]] | April 23, 2025 |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]]     | April 23, 2025 |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]                           | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                                               | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                                   | April 23, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=FsWX2c7Q6Qg&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=45)
$$$
