---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.553Z
published: 2026-10-15T16:16:14.553Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 15
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# It can be asked in many other forms like:

- Design Data Resiliency Architecture
- Design Architecture to achieve 99.999% Availability
- Design to avoid **Single Point of failure**
- Active-Passive vs Active-Active architecture
- Etc

# Single node case

```mermaid
flowchart LR
service@{shape: st-rect}
DB@{shape: db}
client --> LB --> service --> DB
```

It has a single point of failure, If it fails it might take hours to come over the failure so it is not data resilient

# Multi node case

## Active-Active Artitecture

```mermaid
flowchart LR
client --> LB --> data-center-1 & data-center-2
subgraph data-center-1
	s1@{shape: st-rect, label: service 1}
	s2@{shape: st-rect, label: service 2}
	s3@{shape: st-rect, label: service 3}
end
subgraph data-center-2
	s11@{shape: st-rect, label: service 1}
	s22@{shape: st-rect, label: service 2}
	s33@{shape: st-rect, label: service 3}
end
subgraph primary
	db1@{shape: db, label: database}
end
subgraph replicas
	db2@{shape: db, label: database}
end
data-center-1 --> primary
data-center-2 --> primary
primary -.-|sync| replicas
```

**Why we cannot use the secondary DB?**
Oracle/ MySQL/ Postgres are not multi master. Whenever any write request comes these DBs can write them to live DB/ primary DB
But Reading can happen from replica nodes, which can be a better architecture

**What happens when primary DB goes down?**
We move our all traffic to Disaster recovery data center and make the replica DB layer as primary DB layer
as the live DB layer recover from failure we make it the replica DB layer

**Drawbacks**
Latency Addon

```mermaid
flowchart LR
client --> LB --> DC1 & DC2
DC1 --> s1 --> DB
DC2 --> s2 -->|latency addon| DB
```

Delay when DB failure occur when shifting from Live to replicas
Cannot handle more traffic when compared to Active-Active Architecture

## Active Active Architecture

NoSQL DBs like MongoDB and Cassandra are multi-master and can write to multiple live DBs

```mermaid
flowchart LR
client --> LB --> data-center-1 & data-center-2
subgraph data-center-1
	s1@{shape: st-rect, label: service 1}
	s2@{shape: st-rect, label: service 2}
	s3@{shape: st-rect, label: service 3}
end
subgraph data-center-2
	s11@{shape: st-rect, label: service 1}
	s22@{shape: st-rect, label: service 2}
	s33@{shape: st-rect, label: service 3}
end
subgraph primary1
	db1@{shape: db, label: database}
end
subgraph primary2
	db2@{shape: db, label: database}
end
data-center-1 --> primary1
data-center-2 --> primary2
primary1 <--->|sync| primary2
```

**Complexity**
The sync part is the most complex and a disadvantage of this architecture

- change can happen to same row at same time so conflict on sync
- read from one and write at one at same time, so read is wrong

**Advantage**
We are totally utilizing are resources well, so we can handle more traffic for sure

# Related

[[Scale from 0 to 1M users]]
