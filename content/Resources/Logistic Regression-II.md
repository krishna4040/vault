---
publish: true
title: "Lecture 25 : Logistic Regression-II"
description: In this lecture, we will learn the python implementation of Logistic regression especially in the case of classification problem.
created: 2025-04-05
modified: 2026-10-15T16:16:14.556Z
published: 2021-08-17
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=nmuDZZudKuY&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=27
author: IIT Roorkee
lecture: 25
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Logistic Regression ~ Python Implementation

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# upload data
from google.colab import files
uploaded = files.upload()

# read csv
dataset = pd.read_csv("sample.csv")
dataset.shape
dataset.head()

# input
x = dataset.iloc[:, [2,3]].values

# output
y = dataset.iloc[:,4].values

# modelling
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.25)

from sklearn.preprocessing import StandardScaler
sc_x = StandardScaler()
x_train = sc_x.fit_transform(x_train)
x_test = sc_x.transform(x_test)

from sklearn.linear_model import LogisticRegression
classifier = LogisticRegression(random_state=0)
classifier.fit(xtrain, ytrain)

y_pred = classifier.predict(x_test)

from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test, y_pred)
print(f"confusion matrix: {cm}")

from sklearn.metrics import accuracy_score
accuracy_score(ytest, y_pred)
```

## Example2

```python
import numpy as np
```

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                              | created        |
| ----------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Gram Schmidt Process.md\|Gram Schmidt Process]]                                                       | April 05, 2025 |
| [[Resources/Polar Decomposition.md\|Polar Decomposition]]                                                         | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-I.md\|Minimal Polynomial and Jordan Canonical Form-I]]   | April 08, 2025 |
| [[Resources/Minimal Polynomial and Jordan Canonical Form-II.md\|Minimal Polynomial and Jordan Canonical Form-II]] | April 09, 2025 |
| [[Resources/Basic Concepts of Calculus-I.md\|Basic Concepts of Calculus-I]]                                       | April 09, 2025 |

tab: Previous Lectures
| File                                                                                                                            | created        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Linear and Multiple Regression-I.md\|Linear and Multiple Regression-I]]                                             | April 04, 2025 |
| [[Resources/Least Square Approximation and Minimum Normed Solution.md\|Least Square Approximation and Minimum Normed Solution]] | April 04, 2025 |
| [[Resources/Linear Discriminant Analysis.md\|Linear Discriminant Analysis]]                                                     | April 02, 2025 |
| [[Resources/PCA  Derivation and Examples.md\|PCA  Derivation and Examples]]                                                     | April 02, 2025 |
| [[Resources/Principal Component Analysis - I.md\|Principal Component Analysis - I]]                                             | April 02, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=nmuDZZudKuY\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=27)
