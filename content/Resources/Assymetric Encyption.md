---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.551Z
published: 2026-10-15T16:16:14.551Z
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

```mermaid
sequenceDiagram
    actor Alice
    actor Bob

    Alice->>Bob: Plain Message ("Hello, Bob!")
    Alice->>Alice: Encrypt Message (Using Bob's Public Key)
    Alice--)Bob: Encrypted Message (Only Bob can decrypt it)
    Bob->>Bob: Decrypt Message (Using Bob's Private Key)
    Bob-->>Bob: Read Message ("Hello, Bob!")
```
