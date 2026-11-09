---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.554Z
published: 2026-10-15T16:16:14.554Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 4
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# Strangler

```mermaid
flowchart BT
	n1[traffic]
	n2((controller))
	n3[monolith]
	subgraph microservices
		s1
		s2
		s3
	end
	 n1 --> n2
	 n2 --->|10% increase to 100%|microservices
	 n2 --->|90% decrese to 0%|n3
```

---

# Data Management

![[System/Assets/nost91ez.bmp]]

The main **principle** of **microservices data management** is that each microservices should manage **its own data,** we can call this principle as a **database-per-service**
\--- start-multi-column: ID\_6sib

```column-settings
Number of Columns: 2
Largest Column: standard
```

### Shared Database

```mermaid
flowchart TD
	s1((s1))
	s2((s2))
	s3((s3))
	db[(db)]
	
	s1 --> db
	s2 --> db
	s3 --> db
```

Challenges:

- Database scaling is service independent
- Database type is fixed and cannot be modified wrt to different services available

Advantage

- Joining queries
- Transaction management

\--- column-break ---

### Database Per Service

```mermaid
flowchart TD
	s1((s1))
	s2((s2))
	s3((s3))
	db1[(db1)]
	db2[(db2)]
	db3[(db3)]
	
	s1 -->|✔️|db1
	s2 -->|✔️|db2
	s3 -->|✔️|db3

	s1 -->|✔️|s2
	s1 -->|❌|db2
	
	s2 -->|✔️|s1
	s2 -->|❌|db1
	
	s2 -->|✔️|s3
	s2 -->|❌|db3
	
	s3 -->|✔️|s2
	s3 -->|❌|db2
	
	s3 -->|✔️|s1
	s3 -->|❌|db1
	
	s1 -->|✔️|s3
	s1 -->|❌|db1
```

Challenges:

- Joining Queries: CQRS
- Transaction management: SAGA

Advantage

- Scaling becomes service dependent
- Flexibility in choosing multiple databases for different services

\--- end-multi-column

## CQRS

> Command Query Request Segregation

Segregate Command i.e. Create Update Delete from Read operation, by using a common or shared database and query service which updates itself using EDA

![[System/Assets/y0rms9rt.bmp]]

## SAGA

> Sequencing of Transaction

\--- start-multi-column: ID\_cpv6

```column-settings
Number of Columns: 2
Largest Column: standard
```

### Choreographic

![[System/Assets/ueslfuvf.bmp]]

\--- column-break ---

### Orchrestration

![[System/Assets/9q28e4d8.bmp]]

\--- end-multi-column

# Resources

[[Monolith vs Microservices]]
