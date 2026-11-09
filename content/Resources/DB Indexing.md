---
publish: true
created: 2025-02-10
modified: 2026-10-15T16:16:14.553Z
published: 2026-10-15T16:16:14.553Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 21
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# Database Indexing?

Few things we have to understand first, before we see how indexing works.

1. How table data (rows) are actually stored?
2. What type of indexing present?
3. understanding the data structure used for indexing and how it works?

# How table data is actually stored?

Table is just a logical representation this is not how the data is stored in the database, this is not the physical representation

- DBMS creates **Data Pages** (generally its 8KB but depends upon DB to DB)
- Each data page can store multiple table rows in it

## structure of data page

```mermaid
flowchart TD
subgraph block
	Header
	Data@{label: "Data
		Records
	"}
	Offset
end
t1@{shape: text, label: pageNo}
t2@{shape: text, label: "Free space"}
t3@{shape: text, label: checksum}
t4@{shape: text, label: "Actual data is stored in here"}
t5@{shape: text, label: "contains an array, each index of an array holds a pointer to corrsponding data in the data records"}
s1@{shape: text, label: "96 bytes"}
s2@{shape: text, label: "8060 bytes"}
s3@{shape: text, label: "36 bytes"}

Header ~~~ Data ~~~ Offset
Header --> t1 & t2 & t3
Data --> t4
Offset --> t5
Header ~~~ s1
Data ~~~ s2
Offset ~~~ s3
```

so if 1 table is lets say 64 bytes, so in 1 data page we can have ~ 125 DB rows

| Emp ID | Name | Address |
| ------ | ---- | ------- |
| 1      | A    | City A  |
| 2      | B    | City B  |
| 3      | C    | City C  |
| 4      | D    | City D  |

```mermaid
block-beta
columns 3
page["Page ID: 1"]:3
r1["Row 1"]:3
r2["Row 2"]:3
r3["Row 3"]:3
r4["Row 4"]:3
r5[" "]:3
r6[" "]:3
block:group1:3
columns 5
R1["R1
4"] R3["R3
3"] R5["R5
2"] R4["R4
1"] R2["R2
0"]
end
R1 --> r1
R2 --> r2
R3 --> r3
R4 --> r4
```

DBMS creates and manage these data pages. As for storing 1 table data, it can create many data pages
These data pages ultimately gets stored in the Data block in **Physical memory** like disk.

## What is Data block?

- Data block is the minimum amount of data which can be read/ write by an IO operation.
- It is managed by underlying storage system like disk, Data block size can range from _4 kb_ to _32 kb_ (common size is _8 kb_)
- so based on the data block size, it can hold 1 or many data page.

DBMS **mapping** the mapping of Data pages and Data Blocks

| Data Page 1 | Data Block 1 |
| ----------- | ------------ |
| Data Page 2 | Data Block 1 |
| Data Page 3 | Data Block 2 |
| Data Page 4 | Data Block 2 |
Remember, DBMS controls Data pages (like what row goes in which page or sequence of pages etc.) but has no control on Data blocks (data blocks can be scattered over the disk)

# Indexing in RDBMS

## Indexing?

It is used to increase the performance of the database query. so that data can be fetched faster.
without indexing, DBMS has to iterate each and every table row to find the requested data.
i.e. _O(N)_, if there are millions of rows, query can take some time to fetch the data.

### Which DS provides better time complexity then O(N)

B+ Tree, It provides _O(Log N)_ time complexity for insertion, searching & deletion.

### How B(Balanced) Trees work?

- it maintains sorted data
- All leaf are at the same level
- M order B tree means, each node can have at most M childrens
- And M-1 keys per node and M pointers which points to M childrens so a total of _2M-1_ entries

#### Example

Lets store the data in 3 order b tree: _9, 33, 75, 41, 98, 214, 126, 55,72_

```mermaid
block-beta
columns 5
pointer1 key1 pointer2 key2 pointer3
```

- pointer1 < key1
- pointer2 >= key1 & < key2
- pointer3 >= key2

```mermaid
block-beta
columns 2
c1["9"] c2[" "]
```

```mermaid
block-beta
columns 2
c1["9"] c2["33"]
```

```mermaid
block-beta
columns 4
c1["33"]:2 c2[" "]:2
c3["9"] c4[" "] 
c5["75"] c6[" "]
c1 --> c3
c1 --> c5
```

```mermaid
block-beta
columns 4
c1["33"]:2 c2[" "]:2
c3["9"] c4[" "] 
c5["41"] c6["75"]
c1 --> c3
c1 --> c5
```

```mermaid
block-beta
columns 12
c1["33"]:6 c2["75"]:6
c3["9"]:2 c4[" "]:2
c5["41"]:2 c6[" "]:2
c7["98"]:2 c8[" "]:2
c1 --> c3
c1 --> c5
c2 --> c5
c2 --> c7
```

```mermaid
block-beta
columns 12
c1["33"]:6 c2["75"]:6
c3["9"]:2 c4[" "]:2
c5["41"]:2 c6[" "]:2
c7["98"]:2 c8["214"]:2
c1 --> c3
c1 --> c5
c2 --> c5
c2 --> c7
```

```mermaid
block-beta
columns 16
c1["75"]:8 c2[" "]:8
c3["33"]:4 c4[" "]:4 c5["126"]:4 c6[" "]:4
c7["9"]:2 c8[" "]:2 c9["41"]:2 c10[" "]:2 c11["98"]:2 c12[" "]:2 c13["214"]:2 c14[" "]:2
c1 --> c3
c1 --> c5
c2 --> c5
c3 --> c7
c3 --> c9
c5 --> c11
c5 --> c13
```

```mermaid
block-beta
columns 16
c1["72"]:8 c2["75"]:8
c3["33"]:4 c4[" "]:4 c5["126"]:4 c6[" "]:4
c7["9"]:2 c8[" "]:2 c9["41"]:2 c10[" "]:2 c11["98"]:2 c12[" "]:2 c13["214"]:2 c14[" "]:2
c1 --> c3
c1 --> c5
c2 --> c5
c3 --> c7
c3 --> c9
c5 --> c11
c5 --> c13
```

> [!info]
> B+ Trees are similar to B trees, the difference is only the child nodes are also linked together in B+ trees

**DBMS uses B+ trees to manage its Data pages and rows within that pages**
Root node or intermediary node hold the value which is used for faster searching the data. Possible that value might have deleted from DB, but it can be used for sorting the tree.
Leaf node actually holds the indexed column value.

| Emp ID | Emp Name |
| ------ | -------- |
| 19     | e1       |
| 25     | e2       |
| 30     | e3       |
| 17     | e4       |
| 6      | e5       |
| 1      | e6       |
| 5      | e7       |
3 order b tree will look like, for Emp ID to be indexed column

```mermaid
block-beta
columns 16
block:level1:16
	n1["17"]:8 n2[" "]:8
end
block:level2:16
	n3["5"]:4 n4[" "]:4 n5["25"]:4 n6[" "]:4
end
block:level3:16
	n7["1"]:2  n8[" "]:2  n9["5"]:2  n10["6"]:2
	n11["17"]:2 n12["19"]:2 n13["25"]:2 n14["30"]:2
end
n1 --> n3
n1 --> n5
n3 --> n7
n3 --> n9
n5 --> n11
n5 --> n13
```

> [!warning]
> The bottom of the B tree contains the indexed data, the intermediary nodes contain stale data used for b tree construction that is why the indexed node are duplicated intentionally at the leaf level, the intermediary nodes are just for fast searching they will not be updated or deleted as with the data, the leaf node is only updated or deleted

# Type of Indexing

1. Clustered indexing
2. Non Clustered indexing

## Clustered Indexing

Order of rows inside the data pages. match with the order of the index

| Emp ID | Name | Address |
| ------ | ---- | ------- |
| 1      | A    | City A  |
| 4      | B    | City B  |
| 5      | C    | City C  |
| 2      | D    | City D  |
Let Emp ID be the primary key and put index over emp id

| EmpID index |
| ----------- |
| 1           |
| 2           |
| 4           |
| 5           |

```mermaid
block-beta
columns 4
header["Page ID: 1"]:4
r1["Row with empId:1"]:4
r2["Row with empId:4"]:4
r3["Row with empId:5"]:4
r4["Row with empId:2"]:4

block offset:4
 
end
```

---

# Related

[[Transaction Handling in Distributed systems|transaction]]
[[SQL vs NoSQL]]

---

# References / Sources

![Yt Video](https://www.youtube.com/watch?v=6ZquiVH8AGU\&list=PL6W8uoQQ2c63W58rpNFDwdrBnq5G3EfT7\&index=21\&t=142s)
