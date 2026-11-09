---
publish: true
title: "Deep Learning(CS7015): Lec 5.6 Stochastic And Mini-Batch Gradient Descent"
description: lec05mod06
created: 2025-04-23
modified: 2026-10-15T16:16:14.559Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/Vc-jG_LdOLw/maxresdefault.jpg
source: https://www.youtube.com/watch?v=Vc-jG_LdOLw&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=38&t=24s
author: IIT Roorkee
cover: https://i.ytimg.com/vi/Vc-jG_LdOLw/maxresdefault.jpg
lecture: 5.6
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Vanilla GD / Batch GD

```python
def gd():
	w, b,eta, max_epochs = 2, -2, 2.0, 1000
	for i in range(max_epochs):
		dw, db = 0, 0
		for x, y in zip(X, Y):
			dw += grad_w(w,b,x,y)
			db += grad_b(w,b,x,y)
		w = w - eta * dw
		b = b - eta * db
```

The algorithm goves over the entire data once before making an update, this is the original essence of the GD,  sum of the gradients of the losses corresponding to each data point

| x    | y   | $\hat{y}=\frac{1}{1+e^{-wx+b}}$ | $(\hat{y}-y)^{2}$ | $dw=(\hat{y}-y).\hat{y}.(1-\hat{y}).x$ | $db=(\hat{y}-y).\hat{y}.(1-\hat{y})$ |
| ---- | --- | ------------------------------- | ----------------- | -------------------------------------- | ------------------------------------ |
| 1.5  | 0   | 0.8808                          | 0.7768            | 0.1390                                 | 0.0927                               |
| -0.5 | 1   | 0.2689                          | 0.5338            | -0.0724                                | -0.1448                              |
| 0.8  | 1   | 0.6457                          | 0.1251            | -0.0471                                | -0.0588                              |
| 2.0  | 0   | 0.9820                          | 0.9643            | 0.0688                                 | 0.0344                               |
Imagine we have a million points in training data, to make update to w,b algorithm makes a million calculation

# Stochastic GD

```python
def stochastic_gd():
	w, b,eta, max_epochs = 2, -2, 2.0, 1000
	for i in range(max_epochs):
		dw, db = 0, 0
		for x, y in zip(X, Y):
			dw += grad_w(w,b,x,y)
			db += grad_b(w,b,x,y)
			w = w - eta * dw
			b = b - eta * db	
```

Parameter updated are done for every data points, this will converge much faster, flipside these are not the true gradients, true gradient is summation of all grad, it can be assumed an approx of true grad
![[System/Assets/Pasted image 20250516093707.png]]
**Problem**
There are so many oscillations! We are taking greedy decisions, we look at one point which says move in this direction to decrease loss and we blindly move another point says in another direction, this makes so many oscillations

# Mini Batch GD

Improving SGD, Instead of updating parameters for every data point, we update for a mini batch

```python
def mini_batch_gd():
	w, b,eta, max_epochs = 2, -2, 2.0, 1000
	mb_size, points_seen = 2, 0
	for i in range(max_epochs):
		dw, db = 0, 0
		for x, y in zip(X, Y):
			dw += grad_w(w,b,x,y)
			db += grad_b(w,b,x,y)
			points_seen += 1
			if points_seen % mb_size == 0:
				w = w - eta * dw
				b = b - eta * db	
```

# Summary

- 1 epoch = one pass over the entire data
- 1 step = one update of the parameters
- N = number of data points
- B = Mini batch size

| Algorithm  | steps in 1 epoch |
| ---------- | ---------------- |
| Vanilla GD | 1                |
| Stocashtic | N                |
| Mini Batch | N/B              |

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                        | created        |
| --------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]]                 | April 23, 2025 |
| [[Resources/Linear Algebra  Basic Definitions.md\|Linear Algebra  Basic Definitions]]                                       | April 23, 2025 |
| [[Resources/Eigenvalue Decompositon.md\|Eigenvalue Decompositon]]                                                           | April 24, 2025 |
| [[Resources/Principal Component Analysis and its Interpretations.md\|Principal Component Analysis and its Interpretations]] | April 24, 2025 |
| [[Resources/Regularization.md\|Regularization]]                                                                             | March 10, 2025 |

tab: Previous Lectures
| File                                                                                      | created        |
| ----------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Momentum based Gradient Descent.md\|Momentum based Gradient Descent]]         | April 23, 2025 |
| [[Resources/Contours Maps.md\|Contours Maps]]                                             | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                 | April 23, 2025 |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]] | April 23, 2025 |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                 | April 23, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=Vc-jG_LdOLw\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=38\&t=24s)
