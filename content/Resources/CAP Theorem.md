---
publish: true
aliases:
  - CAP
created: 2025-02-08
modified: 2026-10-15T16:16:14.552Z
published: 2026-10-15T16:16:14.552Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 2
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

> Desirable property of distributed systems with replicated data

\--- start-multi-column: ID\_xqwq

```column-settings
Number of Columns: 3
Largest Column: standard
```

Consistency
![[System/Assets/osl0x5dc.bmp]]

\--- column-break ---

Availability
![[System/Assets/cuzpkjyt.bmp]]

\---column-break---

Partial Tolerance
![[System/Assets/pvo3qh18.bmp]]

\--- end-multi-column

---

# Trade offs

All distributed system can have at most two capabilities

- CA - User should not query until when partition happens
- AP - User can query from any node when partition happens with inconsistency
- PC - User can query from only available nodes when partition happens with consistency

Partition tolerance is the main component of any distributed system which cannot be traded off AP and PC are important factors

```mermaid
graph TD
    A[Consistency]:::consistency
    B[Availability]:::availability
    C[Partition Tolerance]:::partition

    A --> AB[CA: No Partition Tolerance]:::tradeoff
    B --> AB
    A --> AC[CP: No Availability]:::tradeoff
    C --> AC
    B --> BC[AP: No Consistency]:::tradeoff
    C --> BC

    classDef consistency fill:\#FFCCCB,stroke:#000,stroke-width:2px
    classDef availability fill:\#CCE5FF,stroke:#000,stroke-width:2px
    classDef partition fill:\#CCFFCC,stroke:#000,stroke-width:2px
    classDef tradeoff fill:\#FFF9C4,stroke:#000,stroke-width:1px
```
