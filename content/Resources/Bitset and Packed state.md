---
publish: true
title: Bitset and Packed state
created: 2026-10-13
modified: 2026-10-16T15:51:59.102Z
published: 2026-10-16T15:51:59.102Z
tags:
  - resource
  - dsa
  - bits
description: ""
author:
reference:
project: "[[Projects/DSA|DSA]]"
lecture: 7
type: permanent
---

# Core Idea

Bitsets and packed states represent many boolean values or small pieces of state using bits packed into a compact representation.

instead of storing one integer or boolean variable per property, we store multiple properties inside the bits of one or more integers.

For example, suppose you need to track whether 8 tasks are completed, following can be the ways:

- Bit masking: use a number of width = 8, i.e. $[0,255]$ can represent the state of 8 tasks
- Bit sets: representing a collection of 8 boolean flags as bits.
- Packed states: encoding several state variables into compact representation, potentially using multiple bits per variable

> [!important]
> C++ provices `std::bitset<N>` for working with a fixed number of bits.

**Choosing between mask and bitset**

| Requirement                                                  | Choice                                 |
| ------------------------------------------------------------ | -------------------------------------- |
| small state that fits in an integer                          | unsigned integer mask                  |
| fixed number of bits, with convenient bit operation          | bitset                                 |
| number of bits determined at runtime                         | bitset                                 |
| need individual values with several possible states          | packed state encoding                  |
| need a straightforward resizable collection of boolean flags | vector<bool> or any suitable container |

# Packed states

Not every state is simply on or off, sometimes each item can have several possible values

| Value | State   |
| ----- | ------- |
| 00    | empty   |
| 01    | wall    |
| 10    | visited |
| 11    | special |
