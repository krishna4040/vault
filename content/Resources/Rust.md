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

# Moving Semantics

## 1

```rust
fn foo(vec: Vec<i32>)        // ownership, immutable
fn bar(mut vec: Vec<i32>)    // ownership, mutable
fn baz(vec: &Vec<i32>)       // shared reference
fn qux(vec: &mut Vec<i32>)   // mutable reference
```

## 2

```rust
let mut x = Vec::new();
let y = &mut x;   // First &mut borrow
y.push(42);       // Last use of y
let z = &mut x;   // ✅ Allowed: y's lifetime ends here
z.push(13);
```

After y is used the compiler sees that y is not used again and hence allows another mutable borrow for x

# Structs

## 1

```rust
struct Person {
	id: i32,
	name: String
};
struct Color(i32, i32, i32);
struct Marker;
```

There are three types of structs in Rust: C-structs, tuple-structs, Unit-structs

# Enums

## 1

```rust
enum Message {
    Resize { width: u64, height: u64 },    // struct-like variant
    Move(Point),                           // tuple-like variant
    Echo(String),                          // tuple-like variant
    ChangeColor(u8, u8, u8),               // tuple-like variant
    Quit,                                  // unit-like variant
}

let messages = [
    Message::Resize {
        width: 10,
        height: 30,
    },
    Message::Move(Point { x: 10, y: 15 }),
    Message::Echo(String::from("hello world")),
    Message::ChangeColor(200, 255, 255),
    Message::Quit,
];
    
match message {
    Message::Resize { width, height } => self.resize(width, height),
    Message::Move(point) => self.move_position(point),
    Message::Quit => self.quit(),
    Message::Echo(s) => self.echo(s),
    Message::ChangeColor(r, g, b) => self.change_color(r, g, b),
}
```

# Strings

## 1

```rust
let name: &'static str = "Alice";
let s1: String = "hello".into(); // Into::into("hello") // String::from("hello")
let s2: String = "hello".to_string(); // ToString::to_string("hello")
let leeter: char = 'A';
let invalid = 'AB';
let s: Vec<char> = s1.chars().collect(); 
```

`&'staic str` is an immutable reference to string stored in ROM

```rust
// &str
let s1 = "blue";
let s2 = &String::from("abc")[0..1];
let s3 = "hello".trim();

// String
let S1 = "read".to_string();
let S2 = String::from("hi");
let S3 = "hello".to_owned();
let S4 = "hello".into();
let S5 = format!("interpolation {}", "Station")
let S6 = "Happy Monday!".replace("Mon", "Tues");
let S7 = "mY sHiFt KeY iS sTiCkY".to_lowercase();
```

|Feature|`&str`|`String`|
|---|---|---|
|Type|String **slice** (borrowed)|**Owned**, growable string|
|Ownership|Borrowed (`&`)|Owns the data|
|Mutability|Immutable by default|Mutable if declared `mut`|
|Stored where?|Read-only memory or heap|Heap|
|Length|Fixed (can't grow/shrink)|Growable/shrinkable|
|Conversion|Comes from string literals|Use `.to_string()` / `.to_owned()`|
|Common usage|Passing read-only string views|Storing/modifying string data|

# Rust API

Rust have 4 crates, namely

- std
- alloc
- core
- test
- proc\_macro

unless working on hardware level, we use std crate

## Rust Std Lib

### Important

- primitive types: array, bool, char, str, slice, tuple, reference, pointer, float, signed, unsigned
- any: Any, type\_name
- utils: arr, char, slice, str
- borrow: Borrow, BorrowMut, ToOwned Traits
- boxed: Box (prelude)
- cell: Cell, LazyCell, OneCell, RefCell, RefMut Structs
- clone: Clone (prelude)
- cmp: Eq, PartialEq, Ord, PartialOrd (already in prelude), max, min, min\_by, max\_by, Reverse, Ordering structs
- collections, string, vec: DSA
- convert: AsMut, AsRef, From, Into, TryFrom, TryInto
- default: Default trait and macro
- Error: Error trait
- fmt: Debug, Display
- future, option, result
- hash: Hash
- marker: Copy Trait and macro (prelude)
- ops: Drop, Fn, FnOnce, FnMut (prelude)
- prelude: already exported by default
- rc
- f64: :constants

### Other

ffi, env, hint, fs, io, iter, mem, net, num, panic, path, pin, process, ptr, range, random, simd, sync, task, thread, time, alloc, arch, ascii,  assert\_matches,  backtrace

### Good to know

env, fs, io, iter, mem, net, path, sync, thread, os, backtrace

---

# Related Resources
