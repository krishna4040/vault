---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.559Z
published: 2026-10-15T16:16:14.559Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 5
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

```mermaid
flowchart LR
    API@{shape: flag, label: API gateway}
    LB1@{shape: notch-rect }
    LB2@{shape: notch-rect }
    LB3@{shape: notch-rect }
    s1@{ shape: st-rect, label: service 1 }
    s2@{ shape: st-rect, label: service 2 }
    s3@{ shape: st-rect, label: service 3 }
    browser@{shape: win-pane}
    CDN((CDN))
    kafka@{shape: rect}
    redis1@{shape: curv-trap, label: redis}
    redis2@{shape: curv-trap, label: redis}
    redis3@{shape: curv-trap, label: redis}
    subgraph db1
	    master1@{shape: db, label: master}
	    slave11@{shape: db, label: slave1}
	    slave12@{shape: db, label: slave2}
	end
	subgraph db2
		master2@{shape: db, label: master}
		slave21@{shape: db, label: slave1}
		slave22@{shape: db, label: slave2}
	end
	subgraph db3
		master3@{shape: db, label: master}
		slave31@{shape: db, label: slave1}
		slave32@{shape: db, label: slave2}
	end
    browser --> CDN --> API ---> LB1 & LB2 & LB3
    LB1 --> s1 --> redis1 --> db1
    LB2 --> s2 --> redis2 --> db2
    LB3 --> s3 --> redis3 --> db3
    s1 & s2 & s3 --> kafka
```

---

# Database Scaling

---

## Vertical Scaling

> CPU, RAM, Storage

---

## Horizontal Scaling

> Creating multiple instances of stateful DBs

Horizontal partitioning is recommended over vertical partitioning

![[System/Assets/b2h3rafm.bmp]]

![[System/Assets/uzpeyk6v.bmp]]

![[System/Assets/we7h7ney.bmp]]

## Challenges

1. Clustering → Consistent Hashing
2. Joining → Denormalization of Data
