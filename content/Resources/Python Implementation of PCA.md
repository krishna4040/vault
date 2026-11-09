---
publish: true
title: "Lecture 18: Python Implementation of PCA"
description: In this lecture, we have discussed the implementation PCA in python.
created: 2025-04-02
modified: 2026-10-15T16:16:14.558Z
published: 2021-07-26
tags:
  - resource
  - algorithm
  - AI
  - ML
source: https://www.youtube.com/watch?v=ZRxtIy00qEg&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=20
author: IIT Roorkee
lecture: 18
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# PCA ~ Python implementation

```python
import numpy as np

# Creating dataset
X = np.array([[1,3,5,7,9,13,20,20,21,24,26],[5,7,11,14,15,17,18,19,21,22,26]])

X = X.T
print(X)
# First column represent Feature1 and Feature2

import matplotlib.pyplot as plt
plt.scatter(X[:,0],X[:,1])

X_meaned = X - np.mean(X, axis=0)
print(X_meaned)
plt.figure
plt.scatter(X_meaned[:,0],X_meaned[:,1])

# Calculate covariance matrix
C = np.cov(X-meaned, rowvar=False)
print(C)

# Calculate eigen values and eigen vector of covariance matrix
eval, evec = np.linalg.eig(C)
print(eval, evec)

sorted_index = np.argsort(eval)[::-1]
sorted_eval = eval[sorted_index]
sorted_evec = evec[:,sorted_index]

n = 1
evec_subset = sorted_evec[:,0:n]
print(evec_subset)

# Transform Data
X_reduced = np.dot(evec_subset.transpose(), X_meaned.transpose()).transpose()
print(X_reduced)

# A Direct method
from sklearn.decomposition import PCA
pca = PCA(n_components=1)
pca.fit(X_meaned)
Xr = pca.transform(X_meaned)
print(Xr)
```

# A Famous Problem

R.A. Fisher's Iris Dataset

- 3 classes
- 4 features: petal length; Petal width; sepal length; sepal width
- 50 of each class

```python
from sklearn import datasets
iris = datasets.load_iris()

iris.get("feature_names")
iris.target

from sklearn.decomposition import PCA
import matplotlib.pyplot as plt

pca = PCA(n_components=1)
pca.fit(iris.data)
X = pca.transform(iris.data)

plt.scatter(X[:,0],X[:,1],c=iris.target)
plt.scatter([X[10][0]],[X[10][1]], s=[200],c=["r"],alpha=0.5)
```

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                                     | April 05, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                                       | April 08, 2025 |

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

![](https://www.youtube.com/watch?v=ZRxtIy00qEg)
