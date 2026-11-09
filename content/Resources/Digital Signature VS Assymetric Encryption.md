---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.554Z
published: 2026-10-15T16:16:14.554Z
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

| **Feature**              | **Encryption**               | **DS**                   |
| ------------------------ | ---------------------------- | ------------------------ |
| **Goal**                 | Confidentiality              | Authentication           |
| **Key used by sender**   | Receivers Public key         | senders private key      |
| **Key used by receiver** | receivers private key        | senders public key       |
| **Visibility**           | hidden only receiver can see | public anyone can verify |
