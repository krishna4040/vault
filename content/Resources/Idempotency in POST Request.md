---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.555Z
published: 2026-10-15T16:16:14.555Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 14
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

## Idempotency VS Concurrency

> [!Idempotency]
> Help us to take care of duplicate Request

```mermaid
flowchart LR
service((service))
user1 -->|original| service
user1 -->|duplicate| service
```

> [!Concurrency]
> Accessing a service at a same time

```mermaid
flowchart TD
	s@{shape: circle, label: service}
	user1 --> s
	user2 --> s
	usern --> s
```

## What is Idempotency?

> [!Defination]
> It enables client to safely **Retry** an operation without worrying about the side effect of operation can cause.

By default GET, PUT, DELETE methods are Idempotent in nature, but POST method is not Idempotent.

```mermaid
	sequenceDiagram
		participant client
		participant server
		client -->>+server: PAY10
		server -->>-client: Debit 10
		client -->>server: PAY10 (Duplicate)
		client -->>server: PAY10 (Duplicate)
```

### Side Effects

> How duplicate can come?

\--- start-multi-column: ID\_0daj

```column-settings
Number of Columns: 2
Largest Column: standard
```

**Sequential**
Duplicate request occur due to original request timeout

```mermaid
sequenceDiagram 
participant client
participant server
client ->>server: POST(original)
client ->>server: POST(duplicate)
```

\--- column-break ---

**Parallel**
Requests coming at the same time

```mermaid
sequenceDiagram
participant client
participant server
client ->>+server: POST(Add Item to cart)
Note over client,server: Timeout
client ->>server: POST(Retry)
server ->>-client: Action completed
```

\--- end-multi-column

## Approach for Idempotency Handling

> Using Idempotency Key??

> \[!Idempotency key]
> It is a Unique id UUID

Agreement with the client

1. Client should generate the IK
2. For each operation new TK should be generated

## Flow

```mermaid
flowchart TD
	client@{shape: win-pane}
	user(user)
	server[server]
	validation1{IK present in request}
	validation2{IK present in DB}
	validation3{Check IK status}
	error1(HTTP 400/ validation error)
	error2(HTTP 409/ Conflict)
	success1(HTTP 201/ resource created)
	success2(HTTP 200/ action already completed)
	create(Put an Entry into DB with status created)
	use(Update DB IK status to consumed)
	delete(Delete IK from DB)
	operation{operation}

	user -->|action| client -->|2 set IK in request header| server
	server --> validation1
	validation1 -->|No| error1
	validation1 -->|Yes| validation2
	subgraph critical-section
	validation2 -->|No| create --> operation
	operation -->|success| use --> success1
	operation --> |failed| delete
	validation2 -->|Yes| validation3
	validation3 -->|Created|error2
	validation3 -->|Consumed|success2
	end
```

### Follow up ques?

1. For parallel requests coming we utilize concept of critical section and mutual exclusion using some setx, mutex
2. In case of distributed service -> using caching

```mermaid
	flowchart LR
	cache((IK cache DB))
	db1@{shape: db}
	db2@{shape: db}
	db3@{shape: db}
	client --> s1 & s2 & s3
	s1 & s2 & s3 --> cache
	s1 --> db1
	s2 --> db2
	s3 --> db3
	db1 -.sync.-> db2 -.sync.-> db3
```
