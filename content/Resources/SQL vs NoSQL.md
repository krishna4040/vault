---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.558Z
published: 2026-10-15T16:16:14.558Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 10
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa81088b7-a188-4089-845a-63936e930a71_1632x1076.png)

---

## SQL

> Structured Query Language used to manage RDBMS (Relation database management system)

### Structure

Tables, rows, columns, predefined schema, plan schema before hand, There are relations between different tables

### Nature

Concentrated, Centralized nature

### Scalability

Vertical scaling is well suited
![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8748d4e2-55b5-4d96-bf15-61cf1b2725d2_950x546.png)

### Property

1. **A** - Atomicity
2. **C** - Consistency
3. **I** - Isolation
4. **D** - Durability

---

## NoSQL

> Non relational SQL, Not only SQL

### Structure

No SQL works on unstructured data

#### Types

5. Key value DB
   Query on the key, value can be anything text, image, blob, ETC
6. Document DB
   Query on the key as well as value
7. Column-wise DB
8. Graph DB

### Nature

Decentralized, distributed in nature
![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3f8ed9eb-fb45-45de-b846-32fea5c87aaa_2130x854.png)

### Scaling

Horizontal scaling is best fit

### Property

9. **BA** - Basically available - Highly available
10. **S** - Safe state - state of data can be changed without interaction itself
11. **E** - Eventual consistency - we might get stale data but after sometime syncing we get the latest data

---

## When to use which one

|       | Query   | Data nature    | Data integrity | Avability |
| ----- | ------- | -------------- | -------------- | --------- |
| SQL   | Complex | Relational     | present        | Low       |
| NoSQL | Easy    | Non relational | absent         | High      |
![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F25e22daa-b6d5-4382-81ba-be90a1a21bb2_3008x2924.png)
