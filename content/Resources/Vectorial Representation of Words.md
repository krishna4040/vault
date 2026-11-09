---
publish: true
title: Vectorial Representation of Words
description: Different Types of Vectorial representation of words
created: 2025-03-10
modified: 2025-03-10 18:25
published: 2026-10-15T16:16:14.559Z
tags:
  - resource
  - AI
  - DL
updated: 2025-03-10 18:25
author: IIT Roorkee
source:
lecture: 8
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# 🔤 What is One-Hot Encoding?

In **one-hot encoding**, each word in a vocabulary is represented as a vector that is:

- All **zeros** except for a single **one** at the index corresponding to that word.
- The length of the vector is equal to the size of the vocabulary.

### 💡 Example

Suppose you have a vocabulary of 4 words:

```
["cat", "dog", "fish", "bird"]
```

Then the one-hot encodings would be:

| Word | One-Hot Vector |
| ---- | -------------- |
| cat  | \[1, 0, 0, 0]   |
| dog  | \[0, 1, 0, 0]   |
| fish | \[0, 0, 1, 0]   |
| bird | \[0, 0, 0, 1]   |

### ✅ Pros

- Simple to implement.
- Doesn't assume relationships between words.

### ❌ Cons

- **Sparse and inefficient**: Mostly zeros, especially with large vocabularies.
- **No semantic meaning**: It treats all words as equally unrelated (no similarity between, say, “cat” and “dog”).
- no cosine similarity and eucledian dis always $\sqrt{ 2 }$

# ✅ **Distributed Representation**

A **distributed representation** of a word is a **dense vector** (usually low-dimensional) where:

- Each dimension captures **some aspect of the word’s meaning**
- Similar words have **similar vectors**.

> ⚠️ Contrast with **one-hot vectors**, which are **sparse**, high-dimensional, and have no inherent meaning or similarity.

Distributed representations can be:

- Learned from **co-occurrence statistics** (e.g. GloVe)
- Learned via **neural prediction models** (e.g. Word2Vec)

## 📊 **Co-occurrence Matrix**

This is a large matrix that counts how often each word appears near every other word.

### Example:

Suppose you have the sentence:

> "The cat sat on the mat."

You could count how often each word appears within a **window size** (e.g., ±2) of each other.

||the|cat|sat|on|mat|
|---|---|---|---|---|---|
|the|0|1|1|1|1|
|cat|1|0|1|0|0|
|sat|1|1|0|1|0|
|on|1|0|1|0|1|
|mat|1|0|0|1|0|
So the row vector for "cat" is its **context**: \[1, 0, 1, 0, 0]

## 🔄 **PPMI: Positive Pointwise Mutual Information**

**Raw co-occurrence counts** are not ideal — they’re biased toward high-frequency words. So we **weight** them with **PMI** (Pointwise Mutual Information):

$PMI=X=\log \frac{count(w,c)}{count(w).count(c)}.N$
Then we use **PPMI** (Positive PMI) to avoid negative values:

$$$PPMI=\begin{cases}
PMI, PMI>0 \\
0, \text{ otherwise}
\end{cases}$$

### Why?

PPMI gives **higher values for meaningful associations** and removes noisy or uninformative co-occurrences.

## 🔻 **SVD: Singular Value Decomposition**

After building a **PPMI-weighted co-occurrence matrix**, we apply **SVD** to **reduce dimensionality** and extract useful features.

$X=U\Sigma V^{T}$

- X is the PPMI matrix
- U and V are orthogonal matrices
- Σ Sigma is a diagonal matrix of **singular values**
We keep only the top **k** components to get dense, low-dimensional **distributed word embeddings**.

LRA: $\hat{X}=\sum^{k}\sigma_{i}u_{i}v_{i}^{T}$
Dimensionality Reduction: $W_{word}=U\Sigma, W_{count}=V^{T}$

# 🔠  **Word2Vec**
**Word2Vec** is a technique to convert words into **dense vector embeddings** that capture **semantic relationships** between words — such that similar words end up with similar vectors.

Developed by **Mikolov et al. at Google (2013)**, it trains small neural networks on large text corpora in one of two ways:
## 🧠 1. CBOW (Continuous Bag of Words)
### ➡️ Predicts a word from its context.
Given a **window of context words**, the model learns to predict the **target (center) word**.

### Example:
Sentence: `"The cat sits on the mat"`
With a context window size of 2, for the word `"sits"`, the context is: `["The", "cat", "on", "the"]`
**Input:** Context words → `["The", "cat", "on", "the"]`  
**Output:** Predict center word → `"sits"`
> It **averages the context word vectors** and tries to predict the center word.

### 📌 Characteristics:
- **Efficient for large datasets**
- **Smoother representations** for frequent words
- Works well when the context is rich
## 🧠 2. Skip-Gram
### ➡️ Predicts context words from a single target word.
Given a center word, it tries to predict the **words around it**.
### Example:
Sentence: `"The cat sits on the mat"`
Center word: `"sits"`, Context window: ±2
**Input:** `"sits"`  
**Outputs:** `["The", "cat", "on", "the"]`

> Tries to maximize probability of context words given the center word.
### 📌 Characteristics
- **Better for small datasets**
- Learns good representations for **rare words**
- More computationally intensive than CBOW
## ⚙️ Training Mechanism
Word2Vec trains using:
- **Negative Sampling** or **Hierarchical Softmax**
- These help efficiently approximate softmax over huge vocabularies
## 🔢 Representation Format

Each word gets two vectors:
- One when it's a **target word** (center)
- One when it's a **context word**
After training, usually only the **input/target word vectors** are kept.

## 📈 Summary: CBOW vs Skip-Gram

| Feature    | CBOW                    | Skip-Gram                |
| ---------- | ----------------------- | ------------------------ |
| Predicts   | Target from context     | Context from target      |
| Input      | Context words (bag)     | Center word              |
| Output     | Center word             | Context words            |
| Faster?    | ✅ Yes                   | ❌ No (slower)            |
| Good for   | Frequent words          | Rare words               |
| Common use | High-speed applications | More accurate embeddings |

## ✅ Key Outcome of Word2Vec

The resulting vectors capture **linguistic patterns** like:
- `king - man + woman ≈ queen`
- `Paris - France + Italy ≈ Rome`
Would you like to see how to implement CBOW or Skip-Gram in code or using libraries like Gensim or PyTorch?
# Glove Representations

---
# Follow up
`````tabs
tab: Next Lectures
| File | created |
| ---- | ------- |

tab: Previous Lectures
```dataview
TABLE created
FROM #literature DL maths
where lecture < this.lecture
SORT lecture DESC
LIMIT 5
```
`````
---
# References
undefined
$$$
