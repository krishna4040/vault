---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.555Z
published: 2026-10-15T16:16:14.555Z
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

GNU protect guard is a command line utility to manage public and private keys across internet
it enables us to

- create public and private keys
- provide a symmetric encryption over private key using pass phrase
- send public keys to a gnu remote server
- import public key from a gnu remote server into a system
- encrypt and decrypt message using public key of other by importing them into our system
- sign a [[Digital signatures|DS]] using encrytption of hash using private key of user and verify other's DS using other's public key, see [[Github  verified commits]]
- export and import public and private keys
- used for password encryption in utilities like pass and gopass

---

# Connected Ideas

---

# References / Sources

[Docs](https://www.gnupg.org/documentation/)
