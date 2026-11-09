---
publish: true
title: "Deep Learning(CS7015): Lec 3.4 Learning Parameters: Gradient Descent"
description: lec03mod04
created: 2025-04-21
modified: 2026-10-15T16:16:14.556Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/giZD8yzXEZ4/maxresdefault.jpg
source: https://www.youtube.com/watch?v=giZD8yzXEZ4&list=PLyqSpQzTE6M9gCgajvQbc68Hk_JKGBAYT&index=23
author: IIT Roorkee
cover: https://i.ytimg.com/vi/giZD8yzXEZ4/maxresdefault.jpg
lecture: 3.4
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Gradient Descent

We start from random weights $\theta=[w, b]$ move in the direction where the loss function decreases $\Delta\theta=[\Delta w,\Delta b]$ by a small amount $\eta$ known as the learning rate
$\theta_{new}=\theta+\eta.\Delta\theta$
![[System/Assets/Pasted image 20250421154113.png]]
What is $\Delta\theta$ or the right direction of change, it is negative $\nabla \mathcal{L}(w,b)$ or negetive direction of gradient of Loss function

$$$\theta_{t+1}=\theta_{t}+\eta(-\nabla \mathcal{L}(\theta)) \implies \begin{bmatrix}
w_{t+1} \\
b_{t+1}
\end{bmatrix}=\begin{bmatrix}
w_{t} \\
b_{t}
\end{bmatrix}-\eta\begin{bmatrix}
\frac{\delta \mathcal{L}(w,b)}{\delta w} \\
\frac{\delta \mathcal{L}(w,b)}{\delta b}
\end{bmatrix}$$
![[System/Assets/Pasted image 20250421155356.png]]
for sigmoid function, and loss as MSE
$$\nabla w=\frac{\delta \mathcal{L}(w,b)}{\delta w}=(\hat{y}-y).\hat{y}.(1-\hat{y}).x$$
$$\nabla b=\frac{\delta \mathcal{L}(w,b)}{\delta w}=(\hat{y}-y).\hat{y}.(1-\hat{y})$$
# Python Implementation
```python
X = [0.5, 2.5]
Y = [0.2, 0.9]

def f(w,b,x):
	return 1/(1+np.exp(-(w*x+b)))

def error(w,b):
	error = 0.0
	for x,y in zip(X,Y):
		fx = f(w,b,x)
		err += 0.5 * (fx-y)**2
	return err

def grad_b(w,b,x,y):
	fx = f(w,b,x)
	return (fx-y)*fx*(1-fx)

def grad_w(w,b,x,y):
	fx = f(w,b,x)
	return (fx-y)*fx*(1-fx)*x

def gradient_descent():
	w, b, eta, max_epochs = -2, -2, 1, 1000
	for i in range(max_epochs):
		dw, db = 0, 0
		for x,y in zip(X,Y):
			dw += grad_w(w,b,x,y)
			db += grad_b(w,b,x,y)
		w = w - eta * dw
		b = b - eta * db	
```

---
# Follow up
`````tabs
tab: Next Lectures
| File                                                                                                                                                      | created        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Representation Power of Multilayer Network of Sigmoid Neurons.md\|Representation Power of Multilayer Network of Sigmoid Neurons]]             | April 21, 2025 |
| [[Resources/Feedforward Neural Networks (a.k.a multilayered network of neurons).md\|Feedforward Neural Networks (a.k.a multilayered network of neurons)]] | April 22, 2025 |
| [[Resources/Learning Paramters of Feedforward Neural Networks (Intuition).md\|Learning Paramters of Feedforward Neural Networks (Intuition)]]             | April 22, 2025 |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]]                                                                 | April 22, 2025 |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                                                                                 | April 23, 2025 |

tab: Previous Lectures
| File                                                                                                                | created        |
| ------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Learning Parameters (Infeasible) guess work.md\|Learning Parameters (Infeasible) guess work]]           | April 21, 2025 |
| [[Resources/A typical Supervised Machine Learning Setup.md\|A typical Supervised Machine Learning Setup]]           | April 21, 2025 |
| [[Resources/Sigmoid Neuron.md\|Sigmoid Neuron]]                                                                     | April 21, 2025 |
| [[Resources/Representation Power of a Network of Perceptrons.md\|Representation Power of a Network of Perceptrons]] | April 19, 2025 |
| [[Resources/Linearly Separable Boolean Functions.md\|Linearly Separable Boolean Functions]]                         | April 19, 2025 |

`````

---
# References
![](https://www.youtube.com/watch?v=giZD8yzXEZ4&list=PLyqSpQzTE6M9gCgajvQbc68Hk_JKGBAYT&index=23)
$$$
