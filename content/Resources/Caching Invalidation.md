---
publish: true
created:
modified: 2026-10-15T16:16:14.552Z
published: 2026-10-15T16:16:14.552Z
tags:
  - resource
  - system-design
  - HLD
project: "[[System Design]]"
description:
author:
reference:
cover:
type: literature
---

| **Factor**                    | **Deleting and Re-Caching**                                         | **Updating the Cache**                                             |
| ----------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Implementation Simplicity** | **Simple**: Only delete and re-fetch. No special logic.             | **Complex**: Must ensure cache consistency, handle concurrency.    |
| **Performance**               | Can be **slower** due to repeated database hits.                    | **Faster reads** after first cache update, reduces DB load.        |
| **Cache Consistency**         | No issue—always fresh.                                              | Needs to ensure data consistency between cache and DB.             |
| **Handling Edge Cases**       | None—just re-fetch.                                                 | More complexity to handle race conditions, partial updates.        |
| **Best for**                  | Low-to-medium traffic, simple logic, no critical consistency needs. | High traffic, frequent reads, or when cache freshness is critical. |
