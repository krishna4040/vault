---
publish: true
title: "Lecture 05 : Basis and Dimension"
description: In this lecture, we have discussed the basis and dimension of a vector space, some theorems and examples related to this concept.
created: 2025-03-30
modified: 2026-10-15T16:16:14.552Z
published: 2021-07-10
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=Ji6FDYXs1pY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=7
author: IIT Roorkee
lecture: 5
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Basis

Application in ML:

- we need to represent feature vectors as a linear combination of the set of linearly independent vectors or orthogonal vectors.
- we need to represent all the vectors of the feature space of our datasets as the linear combination of these vectors
  These vector form a basis for the feature space.
  The concept Is really important in case of _dimensional reduction_ or the _dictionary learning algorithms_, further all _wavelet based algorithms_ approximate a continuous function by a set of orthogonal basis functions generated from the mother wavelet

**Definition**
Let V(F) be a vector space. A basis for V is a set of linearly independent vectors in V which spans the vector space V.

- The space V is finite-dimensional if it has a finite basis
- A vector in basis is called basis vector

**Standard Basis**

- standard basis for R2 is S={(1,0),(0,1)}
- standard basis for R3 is S={(1,0,0),(0,1,0),(0,0,1)}

**Basis in matrix**
$V=\{ M_{22} | \text{ set of all 2 X 2 real matrices } V(R) \text{ forms a vector space } \}$

$$${ \begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix}, \begin{bmatrix}
0 & 1 \\
0 & 0
\end{bmatrix}, \begin{bmatrix}
0 & 0 \\
1 & 0
\end{bmatrix}, \begin{bmatrix}
0 & 0 \\
0 & 1
\end{bmatrix} \}$$
---

$$V=\{ M_{22} | \text{ set of all 2 X 2 real symmetric matrices } V(R) \}$$
$$\{ \begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix}, \begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}, \begin{bmatrix}
0 & 0 \\
0 & 1
\end{bmatrix} \}$$
# Dimensions
The number of vectors in a basis of V(F) is called the dimensions of the vector space V(F).
- Dimension of Rn(R) is n
- Dimension of vector space M(nxm) over R is mXn
- Dimensions of vector space P is infinite

# Important Results
## Theorem
Let {v1,v2,...,vn} be a basis of given V(F). If S be a subset of vectors having more than n vectors, then the set S is linearly dependent.
## Theorem
Let {v1,v2,...,vn} be a linearly independent subset of an n-dimensional vector space V(F), where  k < n. Then S can be extended to a basis of V(F).
## Theorem
Let V(F) be a finite-dimensional vector space. Then any two bases of V have the same number of vectors.
## Theorem
Let V(F) be a finite-dimensional vector space and let S1 and S2 be two subspaces of V. Then
$$dim(S_{1})+dim(S_{2})=dim(S_{1}+S_{2})+dim(S_{1}\cap S_{2})$$
---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                        | created        |
| ----------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear Transformations.md\|Linear Transformations]]                                             | March 30, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]                                                         | March 31, 2025 |
| [[Resources/Orthogonal Complement and Projection Mapping.md\|Orthogonal Complement and Projection Mapping]] | March 31, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]                                 | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]]                           | April 02, 2025 |

tab: Previous Lectures
| File                                              | created        |
| ------------------------------------------------- | -------------- |
| [[Resources/Vector Subspace.md\|Vector Subspace]] | March 30, 2025 |
| [[Resources/Vector Space.md\|Vector Space]]       | March 30, 2025 |
| [[Resources/Matrix Algebra.md\|Matrix Algebra]]   | March 30, 2025 |
| [[Resources/Vectors.md\|Vectors]]                 | March 30, 2025 |

`````
---
# References

![](https://www.youtube.com/watch?v=Ji6FDYXs1pY)  
$$$
