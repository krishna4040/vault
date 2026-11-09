---
publish: true
title: "Lecture 19 : Linear Discriminant Analysis"
description: This lecture explains the concept of LDA including between-class variance, within-class variance and related examples.
created: 2025-04-02
modified: 2026-10-15T16:16:14.556Z
published: 2021-07-26
tags:
  - resource
  - maths
  - LA
  - stats
  - AI
  - ML
source: https://www.youtube.com/watch?v=JpLjNJGNDqk&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=21
author: IIT Roorkee
lecture: 19
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# LDA

- PCA finds the most accurate data representation in a lower dimensional space by projecting data in the directions of maximum variance
- However the directions of maximum variance may be useless for classification

**Main Idea**
If data is linearly separable in higher dimension then by applying PCA and reducing in lower dimension it should be linearly separable

**LDA ~ Definition**
Suppose we have two classes and a d-dimensional samples x1,x2,...,xn, where

- n1 samples are coming from class1 c1
- n2 samples are coming from class2 c2

Now if $x_{i}$ be a data point; then its projection on the line having direction given by unit vector v is given as $v^{T}x_{i}$
Let $\mu_{1}$and $\mu_{2}$ be the means of class c1 and c2 respectively before projection.
If $\tilde{\mu}$ denote the mean of samples of calss c, after projection, then
$\tilde{\mu_{1}}=\frac{1}{n_{1}}\sum_{x_{i}\epsilon c_{1}}^{n_{1}}v^{T}x_{i}=v^{T}\mu_{1}$
similarly we have,
$\tilde{\mu_{2}}=v^{T}\mu_{2}$
In LDA, we need to normalize $|\tilde{\mu_{1}}-\tilde{\mu_{2}}|$ by scatter. Let $y_{i}=v^{T}x_{i}$ be the projected samples then, scatter for samples of class c1 is
$\tilde{s_{1}}^{2}=\sum_{y_{i}\epsilon c_{1}}(y_{i}-\tilde{\mu_{1}})^{2}$
$\tilde{s_{2}}^{2}=\sum_{y_{i}\epsilon c_{1}}(y_{i}-\tilde{\mu_{2}})^{2}$
Thus, we need to project our data onto a line having direction v which maximizes
$J(v)=\frac{(\tilde{\mu_{1}}-\tilde{\mu_{2}})^{2}}{\tilde{s_{1}}^{2}+\tilde{s_{2}}^{2}}$
If we find v which makes J(v) large, we are guaranteed that the classes are well separated.
Define the separate class scatter matrices s1 and s2 of classes c1 and c2
By concept of covariance matrices
$s_{1}=\sum_{x_{i}\epsilon c_{1}}(x_{i}-\mu_{1})(x_{i}-\mu_{1})^{T}$
$s_{2}=\sum_{x_{i}\epsilon c_{1}}(x_{i}-\mu_{2})(x_{i}-\mu_{2})^{T}$
Now, define within the class scatter matrix as
$s_{w}=s_{1}+s_{2}$
Now,
$\tilde{s_{1}}^{2}=v^{T}s_{1}v$
$\tilde{s_{2}}^{2}=v^{T}s_{2}v$
then,
$\tilde{s_{1}}^{2}+\tilde{s_{2}}^{2}=v^{T}(s_{1}+s_{2})v=v^{T}s_{w}v$
Define between the class scatter matrix
$S_{B}=(\mu_{1}-\mu_{2})(\mu_{1}-\mu_{2})^{T}$
Now,
$(\tilde{\mu_{1}}-\tilde{\mu_{2}})^{2}=(v^{T}\mu_{1}-v^{T}\mu_{2})^{2} = v^{T}(\mu_{1}-\mu_{2})(\mu_{1}-\mu_{2})^{T}v = v^{T}S_{B}v$
then,
$J(v)=\frac{(\tilde{\mu_{1}}-\tilde{\mu_{2}})^{2}}{\tilde{s_{1}}^{2}+\tilde{s_{2}}^{2}}=\frac{v^{T}S_{B}v}{v^{T}s_{w}v}$
To find max v, $\frac{d}{dv}J(v)=0 \implies s_{B}v-\frac{v^{T}s_{B}v}{v^{T}s_{W}v}s_{W}v=0 \implies s_{B}v-\lambda s_{w}v=0 \implies s_{w}^{-1}s_{B}v=\lambda v$
from definition of eigen vectors and eigen values,
v is the eigen vector of sw^-1 sb corresponding to largest eigen value

But SbX points in the same direction as mu1-mu2 then,
$S_{B}X=(\mu_{1}-\mu_{2})(\mu_{1}-\mu_{2})^{T}X=\alpha(\mu_{1}-\mu_{2})$
$v = s_{w}^{-1}(\mu_{1}-\mu_{2})$

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                                       | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]                 | April 08, 2025 |

tab: Previous Lectures
| File                                                                                | created        |
| ----------------------------------------------------------------------------------- | -------------- |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]         | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                     | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=JpLjNJGNDqk)
