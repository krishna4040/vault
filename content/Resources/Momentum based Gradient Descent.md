---
publish: true
title: "Deep Learning(CS7015): Lec 5.4 Momentum based Gradient Descent"
description: lec05mod04
created: 2025-04-23
modified: 2026-10-15T16:16:14.557Z
published: 2018-10-24
tags:
  - resource
  - AI
  - DL
socialImage: https://i.ytimg.com/vi/ewN0vFYFJ7A/maxresdefault.jpg
source: https://www.youtube.com/watch?v=ewN0vFYFJ7A&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU&index=37
author: IIT Roorkee
cover: https://i.ytimg.com/vi/ewN0vFYFJ7A/maxresdefault.jpg
lecture: 5.4
project: "[[Artificial Intelligence]]"
reference:
type: literature
---

# Momentum Based GD

- If i am repeatedly being asked to move in the same direction then I should probably gain some confidence and start taking bigger steps in that direction
- Just as a ball gains momentum while rolling down a slope
  $\theta_{t+1}=\theta_{t}-\eta\left( \nabla\theta_{t}+\sum_{i=0}^{t}\gamma^{t-i}\nabla\theta_{i} \right)$

# Python Implementation

```python
def MGD():
	w, b, eta, = init_w, init_b, 1.0
	prev_v_w, prev_v_b, gamma = 0,0, 0.9
	for i in range(max_epochs):
		dw += grad_w(w,b,x,y)
		db -= grad_b(w,b,x,y)
	v_w = gamma * prev_v_w + eta * dw
	v_b = gamma * prev_v_b + eta * db
	w = w - v_w
	b = b - v_b
	prev_v_w = v_w
	prev_v_b = v_b 
```

![[System/Assets/Pasted image 20250423043026.png]]

# Observations

- Even in the regions having gentle slopes, MGD is able to take large steps
- moving fast is not always good

# Sharp Error boundries

- MGD oscillates in and out of the minima valley as the momentum carries it out
- Takes a lot of u turns before finally converging
- Despite these u turns it still converges faster than vanilla greadient descent
  ![[System/Assets/Pasted image 20250423043529.png]]
  ![[System/Assets/Pasted image 20250423043750.png]]

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                                        | created        |
| --------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Stochastic And Mini-Batch Gradient Descent.md\|Stochastic And Mini-Batch Gradient Descent]]                     | April 23, 2025 |
| [[Resources/Introduction To Eigenvalues and Eigenvectors.md\|Introduction To Eigenvalues and Eigenvectors]]                 | April 23, 2025 |
| [[Resources/Linear Algebra  Basic Definitions.md\|Linear Algebra  Basic Definitions]]                                       | April 23, 2025 |
| [[Resources/Eigenvalue Decompositon.md\|Eigenvalue Decompositon]]                                                           | April 24, 2025 |
| [[Resources/Principal Component Analysis and its Interpretations.md\|Principal Component Analysis and its Interpretations]] | April 24, 2025 |

tab: Previous Lectures
| File                                                                                      | created        |
| ----------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Contours Maps.md\|Contours Maps]]                                             | April 23, 2025 |
| [[Resources/Backpropagation Pseudo code.md\|Backpropagation Pseudo code]]                 | April 23, 2025 |
| [[Resources/Backpropagation Computing Gradients.md\|Backpropagation Computing Gradients]] | April 23, 2025 |
| [[Resources/Backpropagation (Intuition).md\|Backpropagation (Intuition)]]                 | April 23, 2025 |
| [[Resources/Output functions and Loss functions.md\|Output functions and Loss functions]] | April 22, 2025 |

```

## ![[System/Assets/Pasted image 20250516103238.png]]

# References

![](https://www.youtube.com/watch?v=ewN0vFYFJ7A\&list=PLEAYkSg4uSQ1r-2XrJ_GBzzS6I-f8yfRU\&index=37)
