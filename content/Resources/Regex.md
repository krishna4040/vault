---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.558Z
published: 2026-10-15T16:16:14.558Z
tags:
  - resource
  - system-design
  - backend
project: "[[System Design]]"
description:
author:
reference:
cover:
type: literature
---

1. char, digits, spaces, special char
2. . => exactly one char
3. - \=> range
4. () => grouping
5. \ => escape char for ., -, (, ), ^, \$, , d, s, w, b, D, S, W, B
6. d => digits, s => whitespaces, w => alphanumeric
7. anchors: specify pos in string
   ^ => start of string
   \$ => end of string
8. Quantifiers: num of repetitions
   1. - \=> 0 or more rep
   2. - \=> 1 or more rep
   3. ? => 0 or 1 occurrence
   4. {n} => exact n rep
   5. {n,} => n or more rep
   6. {n,m} => between n, m reps
9. grouping
   1. capturing: ()
   2. non-capturing: (?:...)
10. Lookahead: (?=...), (?!...)
11. lookbehind: (?<=...), (?\<!...)
12. modes
    1. i: case-insensitive
    2. g: global

```regex
email = r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"
phone = r"^\d{3}-\d{3}-\d{4}$"
url = r"https?://[^\s]+"
pwd = r"^(?=.[a-z])(?=.[A-Z])(?=.*\d).{8,}$"
```
