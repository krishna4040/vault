---
publish: true
title: Lecture
description: All about convlution and CNN and images
created: 2025-03-10
modified: 2025-03-10 18:25
published: 2026-10-15T16:16:14.552Z
tags:
  - resource
  - AI
  - DL
updated: 2025-03-10 18:25
author: IIT Roorkee
source: https://chatgpt.com/c/682615a6-0b34-8005-a9a8-0b4c2abe6bda
lecture: 9
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Convolution Operation

At its core, **convolution** is a way to combine two functions to produce a third one. In deep learning, it typically refers to applying a **filter (kernel)** to an **input (like an image)** to produce a **feature map (activation map)**.
Mathematically, convolution is a **sliding dot product** between an input signal f and a filter (also called a kernel) g.
$f*g=\int_{-\infty}^{\infty}f(x)g(t-x) \, dx $

### 🔚 **Summary Table of Convolutions (with Padding and Stride)**

| **Dim**                              | **Input Shape**                                          | **Kernel Shape**                                                        | **Padding**                               | **Stride**                                | **Output Shape Formula**                                                                                                                                                                                                                                                                                       |
| ------------------------------------ | -------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------- | ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1D**                               | $x∈Rnx \in \mathbb{R}^{n}x∈Rn$                           | $w∈Rkw \in \mathbb{R}^{k}w∈Rk$                                          | $p∈Np \in \mathbb{N}p∈N$                  | $s∈Ns \in \mathbb{N}s∈N$                  | $⌊n+2p−ks⌋+1\left\lfloor \frac{n + 2p - k}{s} \right\rfloor + 1⌊sn+2p−k​⌋+1$                                                                                                                                                                                                                                   |
| **2D**                               | $X∈RH×WX \in \mathbb{R}^{H \times W}X∈RH×W$              | $K∈RkH×kWK \in \mathbb{R}^{k_H \times k_W}K∈RkH​×kW$​                   | $pH,pW∈Np_H, p_W \in \mathbb{N}pH​,pW​∈N$ | $sH,sW∈Ns_H, s_W \in \mathbb{N}sH​,sW​∈N$ | $(⌊H+2pH−kHsH⌋+1, ⌊W+2pW−kWsW⌋+1)\left(\left\lfloor \frac{H + 2p_H - k_H}{s_H} \right\rfloor + 1,\ \left\lfloor \frac{W + 2p_W - k_W}{s_W} \right\rfloor + 1\right)(⌊sH​H+2pH​−kH​​⌋+1, ⌊sW​W+2pW​−kW​​⌋+1)$                                                                                                   |
| **3D**                               | $X∈RD×H×WX \in \mathbb{R}^{D \times H \times W}X∈RD×H×W$ | $K∈RkD×kH×kWK \in \mathbb{R}^{k_D \times k_H \times k_W}K∈RkD​×kH​×kW​$ | $pD,pH,pWp_D, p_H, p_WpD​,pH​,pW​$        | $sD,sH,sWs_D, s_H, s_WsD​,sH​,sW$​        | $(⌊D+2pD−kDsD⌋+1, ⌊H+2pH−kHsH⌋+1, ⌊W+2pW−kWsW⌋+1)\left( \left\lfloor \frac{D + 2p_D - k_D}{s_D} \right\rfloor + 1,\ \left\lfloor \frac{H + 2p_H - k_H}{s_H} \right\rfloor + 1,\ \left\lfloor \frac{W + 2p_W - k_W}{s_W} \right\rfloor + 1 \right)(⌊sD​D+2pD​−kD​​⌋+1, ⌊sH​H+2pH​−kH​​⌋+1, ⌊sW​W+2pW​−kW​​⌋+1)$ |
| **2D in 3D**  <br>(Multi-Channel 2D) | $X∈RC×H×WX \in \mathbb{R}^{C \times H \times W}X∈RC×H×W$ | $K∈RC×kH×kWK \in \mathbb{R}^{C \times k_H \times k_W}K∈RC×kH​×kW​$      | $pH,pWp_H, p_WpH​,pW​$                    | $sH,sWs_H, s_WsH​,sW​$                    | $(⌊H+2pH−kHsH⌋+1, ⌊W+2pW−kWsW⌋+1)\left( \left\lfloor \frac{H + 2p_H - k_H}{s_H} \right\rfloor + 1,\ \left\lfloor \frac{W + 2p_W - k_W}{s_W} \right\rfloor + 1 \right)(⌊sH​H+2pH​−kH​​⌋+1, ⌊sW​W+2pW​−kW​​⌋+1)$ (per filter → multiple channels)                                                                |

# CNN

A **Convolutional Neural Network (CNN)** is a neural architecture specialized for processing grid-like data—such as 1D time series, 2D images, or 3D volumes. It leverages three main ideas:

- **Local receptive fields** (convolution)
- **Weight sharing**
- **Spatial invariance**

## 🔷  How CNN Works (Step-by-step)

### 📌 Convolution Layer

Input: $X∈RC×H×WX \in \mathbb{R}^{C \times H \times W}X∈RC×H×W$
Filter: $K∈RC×kH×kWK \in \mathbb{R}^{C \times k_H \times k_W}K∈RC×kH​×kW​$
$Y[i,j]=∑c=0C−1∑m=0kH−1∑n=0kW−1K[c,m,n]⋅X[c,i+m,j+n]Y[i, j] = \sum_{c=0}^{C-1} \sum_{m=0}^{k_H-1} \sum_{n=0}^{k_W-1} K[c, m, n] \cdot X[c, i+m, j+n]Y[i,j]=c=0∑C−1​m=0∑kH​−1​n=0∑kW​−1​K[c,m,n]⋅X[c,i+m,j+n]$
Multiple such filters give output tensor:
$Y∈RCout×Hout×WoutY \in \mathbb{R}^{C_{\text{out}} \times H_{\text{out}} \times W_{\text{out}}}Y∈RCout​×Hout​×Wout$​

### 📌 Activation Layer

Applies nonlinear transformation (e.g., ReLU):
$ReLU(x)=max⁡(0,x)\text{ReLU}(x) = \max(0, x)ReLU(x)=max(0,x)$

### 📌 Pooling Layer (e.g., Max Pooling)

Reduces spatial dimensions, e.g.:
$Y[i,j]=max_{0\leq m<k_{H},0\leq n<k_{W}}X[i.s+m,j.s+n]$

### 📌 Fully Connected (Dense) Layer

Final layers often flatten and use traditional dense connections:
$y=σ(Wx+b)y = \sigma(Wx + b)y=σ(Wx+b)$
The output Layer activation is softmax, and the Loss function is cross entropy

# Visualizing CNN

Each **filter** (kernel) in a CNN slides over the input and produces a feature map. Each **patch** of the input it looks at is a **receptive field**.

For example:

- Input: $32×3232 \times 3232×32$
- Filter: $3×33 \times 33×3$
- Stride: 1
- Each output pixel is a function of a $3×33 \times 33×3$ **patch** of the input.

So the convolution extracts localized features (like edges, corners).

### Visual Insight:

- First layers learn **edges**, **textures**
- Middle layers learn **shapes**, **patterns**
- Deeper layers learn **object parts**, **high-level concepts**

## 🧭 Finding Influence of Input Pixels Using BP

### **Training and Prediction vs. Understanding**

When we train a CNN, we optimize the parameters $\theta$  by minimizing a loss function, But once the model is trained:

> We might ask: **Why did the network make this prediction for this input image?**

That’s where **input influence analysis** comes in.

### So What Does Vanilla Backprop Give?

It computes the full gradient of the output score (e.g., for "cat") with respect to **each input pixel**. That gives:
$S_{i,j}=∣ \frac{\delta f(x)}{\delta x_{ij}}∣$
This is known as **Saliency Map**

#### 🔍 How is it visualized?

- It's visualized as a **heatmap** or grayscale image overlaid on the original input image.
- Bright or warm colors indicate pixels that had a **large influence** on the prediction.
- Dark or cool colors indicate less influential pixels.

### 🌈 Why Use Guided Backpropagation?

Guided Backpropagation is a **refinement** for better _visual interpretability_.

#### Problems with Vanilla Gradients:

- They flow **through all paths**, including ones that don’t actually contribute much to the final activation.
- They include **negative contributions** that may cancel out meaningful signals.

#### Guided BP Improves This By:

- Letting gradients flow **only where ReLU activations are positive** (i.e., neuron fired)
- And **only if** the gradient from the output is positive (i.e., contributing positively to the decision)

This **filters** out irrelevant or destructive gradient paths. The result:

- ✅ Sharper
- ✅ Cleaner
- ✅ More interpretable saliency maps
- ✅ Better localization of object parts in the image

# Optimization over Images

Normally we optimize the **model weights θ**. But here we **freeze θ** and optimize the **image** directly
$max_{I}(S_{C}(I)-\lambda\Omega(I))$
$i_{k}=i_{k}-\eta\frac{ \delta S_{C}}{\delta i_{k}}$

### 🎯 **Deep Dream AND DeepArt**

![[System/Assets/Pasted image 20250515233524.png]]
![[System/Assets/Pasted image 20250515233559.png]]

# Fooling CNN

![[System/Assets/Pasted image 20250515234741.png]]

---

# Follow up

```tabs
tab: Next Lectures
| File | created |
| ---- | ------- |

tab: Previous Lectures
| File | created |
| ---- | ------- |

```

---

# References

undefined
