---
publish: true
title: "Lecture 15: Python Implementation of SVD and Low - rank Approximation"
description: In this lecture, we will learn a python implementation of SVD and will exploresome of its applications.
created: 2025-04-02
modified: 2026-10-15T16:16:14.558Z
published: 2021-07-26
tags:
  - resource
  - algorithm
  - AI
  - ML
source: https://www.youtube.com/watch?v=zHTe9ehehX8&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=17
author: IIT Roorkee
lecture: 15
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# SVD and LRA ~ Implementation

```python
import numpy as np
np.set_printoptions(precision=4, supress=True)

a = np.array([[1,2,3,4],[1,1,2,3],[0,1,1,0]])
print(a)

# The SVD of this matrix seeks a factorization form
u, s, vh = np.linalg.svd(a, full_matrices=True)
print(u, s, vh)
print(u.dot(u.T)) # This is an identity matrix
print(s) # singluar values

sd = np.diag(s) # makes a 3x3 diagonal matrix x along the diagonal

b = np.zeroes()
b[:,:-1]=sd
sigma = b

print(np.dot(np.dot(u,sigma),vh)) # reconstructing A as product of u, s and vh

## LRA doing a 2 rank approximation
s = [s[0], s[1], 0]
b = np.zeroes(3,4)
b[:,:-1]=sd
sigma=b

print(np.dot(np.dot(u,sigma),vh)) ## Rank 2 approximation of given matrix A
```

# LRA for image processing

```python
import numpy as np
import pandas as pd
import cv2 as cv
from google.colab.patches import cv2_imshow # for image display
from skimage import io
from PIL import Image
import matplotlib.pylab as plt

## Load Image
url = ""
myImg = io.imread(url)
gray_image = cv.cvtColor(myImg, cv.COLOR_BGR2GRAY)
img_mat = np.array(list(gray_image), float)
print(img_mat, img_mat.shape)
plt.imshow(img_mat)
print(img_mat, img_mat.shape)

# scale the image matrix before svd
img_mat_scaled = (img_mat - img_mat.mean())/img_mat.std()

# Perform SVD
U, s, V = np.lingalg.svd(img_mat_scaled)

# Compute Variance explained by each single vector
var_explained = np.rounds(s**2/np.sum(s**2),decimals=3)

import seaborm as sns
sns.barplot(x=list(range(1,11)), y = var_explained[0:10], color="dodgerblue")
plt.xlabel('Singular Vector', fontsize=16)
plt.ylabel('Variance Explained', fontsize=16)
plt.tight_layout()
plt.savefig('svd_screen_plot.png', dpi=150, figsize=(8,8))

# Reconstructing with top 5 singular values
num_components = 5
reconst_img_5 = np.array(U[:,:num_components]).dot(np.diag(s[:num_components]).dot(np.array(V[:num_components,:])))
plt.imshow(reconst_img_5)
```

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]]                                             | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |

tab: Previous Lectures
| File                                                                              | created        |
| --------------------------------------------------------------------------------- | -------------- |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                 | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]       | April 02, 2025 |
| [[Resources/Spectral Decomposition.md\|Spectral Decomposition]]                   | April 02, 2025 |
| [[Resources/Special matrices and Properties.md\|Special matrices and Properties]] | April 02, 2025 |
| [[Resources/Eigenvalues and Eigenvectors.md\|Eigenvalues and Eigenvectors]]       | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=zHTe9ehehX8)
