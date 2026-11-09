---
publish: true
title: "Lecture 09: Eigenvalues and Eigenvectors"
description: In this lecture, we have discussed about eigenvalues and eigenvectors of a square matrix, its  importance in machine learning and related concepts.
created: 2025-04-02
modified: 2026-10-15T16:16:14.554Z
published: 2021-07-15
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=vsb_Y4rNBCc&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=10&t=473s
author: IIT Roorkee
lecture: 9
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Eigen Vectors and Values

**Geometrical interpretation**
suppose we have a vector X suppose we multiply this vector by a Matrix A we get a new vector AX
We observe that when a matrix hits a vector it changes it direction and scales the vector
we see if we can have a matrix that does not change the direction of the vector only scales the vector, such matrices are known as eigen vectors and the scaling factor is known as eigen value

**Math Defination**
Let $A \epsilon R^{n\times n}$
we say that a non-zero vector v belong to Rn is an eigen vector of A corresponding to eigen value lambda if,
$Av=\lambda v \text{ or } (A-\lambda I)v=0 \text{ or } \det(A-\lambda I)=0$

> [!tip]
> $det(A-\lambda I)$ is known as characterstic polynomial

Root of characteristic polynomial gives the eigen values corresponding to that matrix, and for each eigen value there exist a eigen vector
If there are repeated root, it is known as _Algebraic Multiplicity(AM)_ of the eign value

# Properties of eigen values and vectors

Let, $AX = \lambda X$
then,
$A^{-1}AX=A^{-1}(\lambda X)\implies A^{-1}X=\frac{1}{\lambda}X$
$AX=\lambda X \implies A^{2}X=\lambda(\lambda X)\implies A^{2}=\lambda^{2}X$
$Trace(A)=\text{sum of eigen values}$
$Det(A)=\text{product of eigen values}$

# Numpy implementation

```python
import numpy as np
A = np.array([[2,-2,3],[1,1,1],[1,3,-1]])
values, vectors = np.linalg.eig(A)
print(values, vectors)
```

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]   | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                     | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |

tab: Previous Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]]                                             | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]                                                   | March 30, 2025 |
| [[Resources/Vector Subspace.md\|Vector Subspace]]                                                           | March 30, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=vsb_Y4rNBCc)
