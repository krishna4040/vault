---
publish: true
title: "Lecture 02 : Basics of Matrix Algebra"
description: In this lecture, we have discussed different types of matrices, matrix algebra consisting matrices addition, multiplication etc. Transpose of a matrix and determinant have also been discussed.
created: 2025-03-30
modified: 2026-10-15T16:16:14.557Z
published: 2021-07-12
tags:
  - resource
  - maths
  - LA
  - AI
  - ML
source: https://www.youtube.com/watch?v=VviJTNbznjE
author: IIT Roorkee
lecture: 2
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Matrix

A matrix is a 2D array of scalers with one or more row or column
elements of matrix is represented as
$\{ a_{ij} \}_{m\times n}$
$i = 1,2,\dots,m \text{ and }j=1,2,\dots,n$

# Types of matrices

## Diagonal matrices

A square matrix whose off diagonal elements are all zeroes

## Triangular matrices

All elements below (upper triangular) or above (lower triangular) diagonal are zero

## Identity Matrix

A Diagonal matrix who's all diagonal entries are all 1

# Matrix Algebra

## Equivalence

Two matrices are said to be equal if their dimensions are equal and all corresponding elements are equal
$a_{ij}=b_{ij} \forall i,j$

## Addition and subtraction

The addition or sub of two matrices A and B of the same size yields a matrix C of the same size
$c_{ij}=a_{ij}\pm b_{ij}$

> [!tip]
> **Commutative** A+B = B+A
> **Assosiative** A+(B+C) = (A+B)+C

## Scaler Multiplication

$A = \{ a_{ij} \}_{m\times n} \implies\alpha A=\{ \alpha a_{ij} \}_{m\times n}$

## Matrix multiplication

- The product of two matrices is another matrix
- The necessary condition for multiplication of two matrices A and B is that _the number of columns of A must equal the number of rows of B_
  $C = A \times B$
  $c_{ij}=\sum_{k=0}^{n} a_{ik}\times b_{kj}$

> [!tip]
>
> 1. AI = IA = A
> 2. A(BC) = (AB)C = ABC
> 3. A(B+C)=AB+AC
> 4. (A+B)C = AC + BC

> [!caution]
>
> 1. AB not generalyy equal to BA, BA may not be defined
> 2. if AB=0, neither A nor B necessarily = 0
> 3. if AB=AC, B not necessarily = C

## Transpose of matrix

$A = \{ a_{ij} \}_{m\times n} \implies A^{T}=\{ a_{ji} \}_{n\times n}$

> [!important]
> $(A+B)^{T}=A^{T}+B^{T}$
> $(AB)^{T}=B^{T}A^{T}$
> $(kA)^{T}=kA^{T}$
> $(A^{T})^{T} = A$

## Determinant of a matrix

- Every square matrix has a determinant
- The determinant of a matrix is a number

## Inverse of a matrix

- If Det of a matrix is zero it is called **singular** and _inverse does not exist_
- If Det of a matrix is non-zero it is called **non-singular** and _inverse exists_

> [!important]
> $(AB)^{-1}=B^{-1}A^{-1}$
> $(A^{-1})^{-1}=A$
> $(A^{T})^{-1}=(A^{-1})^{T}$
> $(kA)^{-1}=\frac{1}{k}A^{-1}$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                            | created        |
| --------------------------------------------------------------- | -------------- |
| [[Resources/Vector Space.md\|Vector Space]]                     | March 30, 2025 |
| [[Resources/Vector Subspace.md\|Vector Subspace]]               | March 30, 2025 |
| [[Resources/Basis and Dimension.md\|Basis and Dimension]]       | March 30, 2025 |
| [[Resources/Linear Transformations.md\|Linear Transformations]] | March 30, 2025 |
| [[Resources/Norms and Spaces.md\|Norms and Spaces]]             | March 31, 2025 |

tab: Previous Lectures
| File                              | created        |
| --------------------------------- | -------------- |
| [[Resources/Vectors.md\|Vectors]] | March 30, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=VviJTNbznjE)
