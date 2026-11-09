---
publish: true
title: "Lecture 48: Review on Probability"
description: "In this lecture, we review basic concepts of probability: addition rule, conditional probability, independent events, theorem of total probability."
created: 2025-04-18
modified: 2026-10-15T16:16:14.558Z
published: 2021-09-14
tags:
  - resource
  - maths
  - probability
  - AI
  - ML
source: https://www.youtube.com/watch?v=xtAMLTYrlKU&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE&index=49
author: IIT Roorkee
lecture: 48
project: "[[Artificial Intelligence]]"
reference:
cover:
type: literature
---

# Random Experiment

Several processes are random in nature, where the total possible outcomes are known but the occurrence of an outcome is uncertain. Such processes or experiments are called Random Experiments
Example: Tossing of a coin, Roll a die

# Classical Approach to Probability

$Probalility = \frac{\text{Number of favourable outcomes}}{\text{Total number of outcomes}}$

# Definitions

1. **Sample Space** The set S of all possible outcomes of a random experiments
2. **Event** Any subset E of the sample space $E\subset S$
3. Types of events
   - **Sure Event** → Event which is certain to occur, $P(E) = 1$
   - **Impossible Event** → Event which is impossible to occur, $P(E)=0$
   - **Mutually Exclusive Events** → Events E and F are ME if they can not occur simultaneously, $E\cap F=\phi$
   - **Mutually Exhaustive Events** → Events E and F are ME if they exhaust the whole sample space, $E \cup F=\phi$

# Addition rule of probability

$P(A\cup B)=P(A)+P(B)-P(A\cap B)$
$P(A\cup B\cup C)=P(A)+P(B)+P(C)-P(A\cap B)-P(B\cap C)-P(C\cap A)+P(A\cap B\cap C)$

# Conditional Probability

For any two events E and F associated with a Sample space S of a random experiment, the probability of event E given event F has occurend is termed as conditional probability of E given F, denoted as $P(E|F)$
$P(E|F)=\frac{\text{Favaouraable outcomes where both E and F occur}}{\text{Total outcomes where F occured}}$
when we have prior information that an event has occurred the size of sample space reduces, making it a all new random experiment, with the sample space being the subset of sample space of the original event
Let the new sample space be $S'\subset S$ and new Event $E'$ then,
$n(S') = n(F)$
$n(E') = n(E\cap F)$
$P(E')=\frac{n(E')}{n(S')}=\frac{\frac{n(E\cap F)}{n(S)}}{\frac{n(F)}{n(S)}}=\frac{P(E\cap F)}{P(F)}=P(E|F)$

## Properties of CP

1. for any non empty event E, $P(E|E)=P(S|E)=1$
2. for any events A,B and F $\neq \phi$, $P((A \cup B)|F)=P(A|F)+P(B|F)-P((A\cap B)|F)$
3. for any event A and F $\neq \phi$, $P(A^{c}|F)=1-P(A|F)$

# Multiplication Theorem on Probability

$P(E\cap F)=P(E).P(F|E)=P(F).P(E|F)$
$P(E\cap F\cap G)=P(E).P(F|E).P(G|E\cap F)$

# Independent Events

Two events E and F are said to be independent if,
$P(E\cap F)=P(E).P(F)$
“The occurrence (or non-occurrence) of one event gives **no information** about the other.”
The new sample space remain unchanged and $S'=S$

> [!important]
> if two events are mutually Exclusive then they cannot be independent vice versa is not true

# Partition of a sample space

$\{ E_{1},E_{2},\dots,E_{n} \}$ is said to be a partition of the sample space S if

- $E_{i}'$s are exhaustive events: $E_{1}\cap E_{2}\cap\dots \cap E_{n}=S$
- $E_{i}'$s are mutually exclusive: $E_{i}\cap E_{j}=\phi \text{ for } i\neq j$

# TPT

Consider $\{ E_{1},E_{2},\dots,E_{n} \}$ to be a partition of the sample space S associated with a random experiment. For any event $A\subset S$, the total prob of A is given as
$P(A)=\sum_{i=1}^{n}P(E_i)P(A|E_{i})$
![[System/Assets/Pasted image 20250418203954.png]]

---

# Related

---

# Follow up

```tabs
tab: Next Lectures
| File                                                                                                          | created        |
| ------------------------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Bayes' theorem and Random variables.md\|Bayes' theorem and Random variables]]                     | April 18, 2025 |
| [[Resources/Expectation and Variance.md\|Expectation and Variance]]                                           | April 18, 2025 |
| [[Resources/Discrete probability distributions.md\|Discrete probability distributions]]                       | April 18, 2025 |
| [[Resources/Continuous probability distributions.md\|Continuous probability distributions]]                   | April 18, 2025 |
| [[Resources/Joint probability distribution and covariance.md\|Joint probability distribution and covariance]] | April 18, 2025 |

tab: Previous Lectures
| File                                                                                        | created        |
| ------------------------------------------------------------------------------------------- | -------------- |
| [[Resources/Newton's and Penalty function method.md\|Newton's and Penalty function method]] | April 17, 2025 |
| [[Resources/Steepest Descent method.md\|Steepest Descent method]]                           | April 17, 2025 |
| [[Resources/Constrained Optimization-II.md\|Constrained Optimization-II]]                   | April 17, 2025 |
| [[Resources/Constrained Optimization-I.md\|Constrained Optimization-I]]                     | April 16, 2025 |
| [[Resources/Unconstrained Optimization.md\|Unconstrained Optimization]]                     | April 16, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=xtAMLTYrlKU\&list=PLLy_2iUCG87D1CXFxE-SxCFZUiJzQ3IvE\&index=49)
