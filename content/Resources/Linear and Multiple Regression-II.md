---
publish: true
title: "Lecture 23: Linear and Multiple Regression-II"
description: In this lecture, we will learn the implementation of Linear regression in python.
created: 2025-04-04
modified: 2026-10-15T16:16:14.556Z
published: 2021-08-16
tags:
  - resource
  - algoritm
  - AI
  - ML
source: https://www.youtube.com/watch?v=ADzhz1Wely8&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=25
author: IIT Roorkee
lecture: 23
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Regression ~ Python implementation

## SLR

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Loading csv data
from google.colab import files
uploaded = files.upload()

score = pd.read_csv("student_scre.csv")
score.shape
score.head()
score.describe()

# plot this data
score.plot(x='Hours',y='Scores',style='o')
plt.show()

# Modelling
X = score.iloc[:,:-1].values
y = score.iloc[:,1].values
from sklearn.linear_model import LinearRegression
reg = LinearRegression()
reg.fit(X,y)
print(reg.intercept_, reg,coef_)

y_pred = reg.predict(X)
df = pd.DataFrame({'Actual': y, 'Predicted': y_pred})
df

from sklearn.metrics import mean_squared_error, r2_score
print('MSE: %.2f'%mean_squared_error(y,y_pred))
print('R2_score: %.2f'%r2_score(y,y_pred))
plt.scatter(X,y,color='black')
plt.plot(X,y_pred,color='blue',linewidth=2)
plt.show()
```

## MLR

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Loading csv data
from google.colab import files
uploaded = files.upload()

# reading file
score = pd.read_csv("startup.csv")
score.shape
score.head()
score.describe()

# preparing data
X = score.drop('Profit', axis=1)
y = Score['Profit']
print(X,y)

# modelling
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X,y,test_size=0.2,random_size=0.2)

from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, y_train)
print(regressor.intercept_, regressor.coef_)

# making predictions
y_pred = regressor.predict(X_test)
df = pd.DataFrame({'Actual': y_test, 'Predicted': y_pred})
df

# The Coeff
from sklearn.metrics import mean_squared_error, r2_score
print('Coefficients:', regressor.coef_)
print('MSE', mean_squared_error(y_test, y_pred))
print('R2 Score', r2_score(y_test, y_pred))

# Plotting outputs
plt.scatter(X_test['Administration'], y_test, color='black')
plt.scatter(X_test['Administration'], y_pred, color='blue')
plt.xticks(())
plt.yticks(())
plt.show()
```

## PR

```python
import matplotlib.pyplot as plt
import numpy as np
from sklearn.netrics import r2_score, mean_squared_error

x = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15]
y = [16.08, 33.83, 65.8, 97.2, 191.55, 236.87, 520.53, 590.03, 651.92, 724.93, 699.50]

mymodel = np.poly1d(np.polyfit(x,y,3)) # 3 degree polynomial
myline = np.linespace(1,15,100)

plt.scatter(x,y)
plt.plot(myline, mymodel(myline))
plt.show()
print(f"R2 score: {r2_score(y, mymodel(x))}")
print(f"MSE: {mean_sqaured_error(y, mymodel(x))}")
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

![](https://www.youtube.com/watch?v=ADzhz1Wely8)
