---
publish: true
title: "Lecture 20 : Python Implementation of LDA"
description: In this lecture, we have discussed the implementation of LDA in python.
created: 2025-04-02
modified: 2026-10-15T16:16:14.558Z
published: 2021-07-26
tags:
  - resource
  - algoritm
  - AI
  - ML
source: https://www.youtube.com/watch?v=EC7AalPAyLY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=22
author: IIT Roorkee
lecture: 20
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# PCA vs LDA

| **PCA**                                                    | **LDA**                                                                         |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------- |
| PCA do the feature classification                          | LDA do data classification                                                      |
| PCA is a type of unsupervised learning technique           | LDA is a supervised learning technique                                          |
| It projects the data in the direction of maximum variation | It projects the data in a direction which providea max inter class seperability |
| Can be used to reduce data up to any dimensions            | Can reduce data up to number of class 1 dimensions                              |

# LDA ~ Python Implementation

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([[0,1,2,3,4,5,6,7,8],[1,2,3,3,5,5,0,1,2,3,5,6,6]])
y = np.array([0,0,0,0,0,0,1,1,1,1,1,1,1,1])
x = x.T

plt.scatter(x[:,0],x[:,1],c=y)

# Apply pca
from sklearn.decomposition import PCA
pca = PCA(n_components=1)
pca.fit(x)
xr = pca.transform(x)
print(xr)
plt.scatter(xr[:,0],xr)
```

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
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]         | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]         | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]] | April 02, 2025 |
| [[Resources/Low Rank Approximations.md\|Low Rank Approximations]]                   | April 02, 2025 |
| [[Resources/Singular Value Decomposition.md\|Singular Value Decomposition]]         | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=EC7AalPAyLY)
