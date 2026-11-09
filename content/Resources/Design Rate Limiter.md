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
lecture: 12
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

## Problem

```mermaid
flowchart LR
	user
	attacker
	server

	attacker --> server
	attacker --> server
	attacker --> server
	user -->|❌| server
```

---

## Rate limiting algorithms

1. Token Bucket
2. Leaking Bucket
3. Fixed window counter
4. Sliding window log
5. sliding window counter

### Token Bucket
