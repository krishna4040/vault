---
publish: true
title: "Lecture 26 : Classification Metrics"
description: In this  lecture, we will learn about various classification metrics used to evaluate the performance of ML classification model. We will also demonstrate the implementation of these metrics in python
created: 2025-04-05
modified: 2026-10-15T16:16:14.552Z
published: 2021-08-17
tags:
  - resource
  - AI
  - ML
source: https://www.youtube.com/watch?v=kmMQtZonqH4&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=28
author: IIT Roorkee
lecture: 26
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Classification metrics

- Classification is a part of _Supervised learning_ through which data inputs can be easily separated into categories. There can be binary classifiers or multi-class classifiers
- some of the classification applications are face recognition, YouTube video categorization, content moderation, medical diagnosis, to text classification, hate speech detection on Twitter
- Some classification models are given as SVM, logistic regression, decision tree, random forest, convolutional neural network, recurrent neural network

# Performance Evaluation

## Confusion matrix

- one of the key concept in classification performance is **Confusion Matrix** which is a tabular visualization of the model predictions versus the actual labels.
- Each row of the confusion matrix represents the instances in an actual class whereas each column represents the instances in a predicted class

### Drawbacks

- There are many cases in which classification accuracy is not a good indicator of your model performance
- One of these scenarios is when your class distribution is imbalanced, one class is more frequent than others
- In this case, even if you predict all samples as the most frequent class you would get a high accuracy rate, which does not make sense at all

## Precision

Precision gives the faction of correctly identifies as positibe out of all predicted as positives.
$Precision = \frac{TP}{TP+FP}$

## Recall

Recall gives the fraction you correctly identifies as positive out of all positives
$Recall=\frac{TP}{TP+FN}$

## F1 score

It is defined as the harmonic mean of the models  precision and recall
$F1 Score=2\times \frac{Precision\times Recall}{Precision + Recall}$
we use HM because it is not sensitive to extremely large values, unlike simple averages.

# Accuracy

$Accuracy = \frac{TP+TN}{TP+TN+FP+FN}$

---

# Python Implementation

```python
from sklearn import metrices
y_actual = ["c","h","f","c","h","f","c","h","h"]
y_pred = ["c","c","f","h","h","c","c","f","f"]
cm = metrics.confusion_matrix(y_actual, y_pred, labels=["c","h","f"])
report = metrices.classification_report(y_actual, y_pred, labels=["c","h","f"])
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

![](https://www.youtube.com/watch?v=kmMQtZonqH4\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=28)
