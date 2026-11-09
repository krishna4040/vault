---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.551Z
published: 2026-10-15T16:16:14.551Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 8
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# What is BOE?

> It drives our decision for system design

### Considerations (Basics)

- Rough/ T-shirt size/ High level estimation
- Do not spend much time
- Keep the assumption values simple

### Cheat sheet

\--- start-multi-column: ID\_um3y

```column-settings
Number of Columns: 2
Largest Column: standard
```

| Zeroes | Traffic  | Storage |
| ------ | -------- | ------- |
| 3      | Thousand | KB      |
| 6      | Million  | MB      |
| 9      | Billion  | GB      |
| 12     | Trillion | TB      |
| 15     | Quallion | PB      |

\--- column-break ---

**DATA**

- char = 2bytes
- long/double = 8bytes
- Image/ audio/ video = 300kb

\--- end-multi-column

### Computations

- Number of servers
- RAM
- Storage
- Trade off CAP

### Important formula

$$
x \text{Million} \times y \text{KB} = xy \text{GB}
$$

# Difference between different estimation techniques

|Aspect|Back of the Envelope (BoE) Estimation|Parametric Estimation|Analogous Estimation|Bottom-Up Estimation|
|---|---|---|---|---|
|Speed|Quick turnaround for rough estimates|Moderate|Moderate|Time-consuming|
|Precision|Low; provides rough approximations|Moderate to High|Moderate to High|High|
|Complexity Handling|Limited; suitable for simple systems|Moderate|Moderate|High|
|Dependency on Expertise|Medium; relies on basic principles|High|High|High|

---

# Estimation of Facebook

1. Total users = 1Billion
2. DAU = 25% of total users = 250M
3. Traffic estimations
   - Reads operations per day per user = 5
   - Writes operations per day per user = 2
   - Total operations per day per user = 7
   - Query per seconds$\text{QPS} = \frac{250\text{Million users} \times 7 \text{queries}}{60 \times 60 \times 24 \text{seconds}} = 18\text{qps}$
4. Storage assumptions
   - Every DAU doing 2 posts = 500 chars = 500chars X 2bytes = 1000bytes = 1KB
   - 10% DAU uploads 1 Image = 300KB
   - $\text{Total memory} = 1\text{KB} \times 250\text{Million DAU} = 250\text{GB/day}$
   - $\text{Total storage} = 300\text{KB} \times 10\% 250\text{Million DAU} = 7500GB = 8TB/day$
   - For 5years = 500TB for posts and 16PB for Images and media
5. RAM Estimation
   - For each DAU last 5 post we cache
   - 1 post = 500 bytes, 5 posts = 3kb
   - Total memory = 250M X 3kb = 750GB
6. CPU estimation
7. Trade off we can drop consistency
