---
publish: true
created: 2025-02-09
modified: 2026-10-15T16:16:14.556Z
published: 2026-10-15T16:16:14.556Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 18
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# Load Balancer?

```mermaid
	flowchart LR
	subgraph clients
		client1
		client2
		client3
	end
	server@{shape: st-rect}
	client1 & client2 & client3 ---> Load-balancer ---> server
```

# Types of Load balancer

## 1. Network Level Load balancer (L4 balancer)

It can read packets TCP port, UDP port, IP address of source and destination, based on this it routes or balance the request accordingly
It is much more faster than Application Load balancer

## 2. Application Level Load Balancer (L7 balancer)

It can take decision to distribute traffic based upon Header/ session/ cookies/ data. It can also perform caching. It is much more advanced

---

# Load balancing Algorithms

## 1. Static Algorithms

### Round robin

```mermaid
flowchart LR
client1 --->|1| LB
client2 --->|2| LB
client3 --->|3| LB
client4 --->|4| LB
client5 --->|5| LB
LB --->|1,3,5| server1
LB --->|2,4| server2
```

#### Advantages

- Very Easy to implement
- Equal load balancing distribution

#### Disadvantages

- one server with high capacity and one with low will be treated as equal
- chance that low capacity server will go down is high

### Weighted Round robin

it tries to solve the drawback of round robin by giving wights to the server acc to resources

```mermaid
flowchart LR
w3@{shape: text, label: weight3}
w1@{shape: text, label: weight1}
client1 --->|1| LB
client2 --->|2| LB
client3 --->|3| LB
clientn --->|n| LB
LB --->|1,2,3,5,6,7| server1 ~~~ w3
LB --->|4,8| server2 ~~~ w1
```

#### Advantages

- Low capacity server will get saved from receiving the large num of requests
- easy to implement as weights are static, no dynamic computation

#### Disadvantages

- If requests have different processing time, it is possible that low capacity server might get high processing requests, and possible it might get exhausted soon

### IP HASH

```mermaid
flowchart LR
ip1@{shape: text, label: 192.278.10.4}
ip2@{shape: text, label: 182.178.14.2}
ip3@{shape: text, label: 172.178.10.242}
ipn@{shape: text, label: 152.198.10.14}
hash@{shape: text, label: ip_hash}

ip1 ~~~ client1
ip2 ~~~ client2
ip3 ~~~ client3

client1 & client2 & client3 & clientn ---> LB ---> server1 & server2
LB ~~~ hash
```

#### Advantage

- Good for use cases, where same client need to connect to same server
- easy to implement

#### Disadvantage

- If client request is coming through **PROXY** then all the client will be assigned the same server which might create overload
- cannot ensure equal distribution

```mermaid
flowchart LR
ip1@{shape: text, label: 192.278.10.4}
ip2@{shape: text, label: 182.178.14.2}
ip3@{shape: text, label: 172.178.10.242}
ipn@{shape: text, label: 152.198.10.14}
iproxy@{shape: text, label: 183.23.12.13}
hash@{shape: text, label: ip_hash}

ip1 ~~~ client1
ip2 ~~~ client2
ip3 ~~~ client3

client1 & client2 & client3 & clientn ---> proxy ---> LB ---> server1 & server2
proxy ~~~ iproxy
LB ~~~ hash
```

## 2. Dynamic Algorithms

### Least connection

```mermaid
flowchart LR
rule@{shape: text, label: "Has Less Active Connection"}
s2@{shape: text, label: "Active connections: client2"}
s1@{shape: text, label: "Active connections: client1, client3"}

client1 & client2 & client3 & clientn ---> LB ---> server1 & server2
LB ~~~ rule
server1 ~~~ s1
server2 ~~~ s2
```

#### Advantages

- dynamic, as it considers the load on each server, so chance of over burden of the server is less when each server has equal capacity

#### Disadvantages

- TCP connections can be active but possible have no traffic (requests)
- unable to differenciate BW low capacity and high capacity server. chance that low capacity server will get over burdened.

### Weighted Least connection

```mermaid
flowchart LR
rule@{shape: text, label: "Calculate ratio of num if active connections to weights, server with min ration get the requests"}
s2@{shape: text, label: "Active connections: client2"}
s1@{shape: text, label: "Active connections: client1, client3"}
w1@{shape: text, label: "weight 10"}
w2@{shape: text, label: "weight 1"}

client1 & client2 & client3 & clientn ---> LB ---> server1 & server2
LB ~~~ rule
server1 ~~~ s1 & w1
server2 ~~~ s2 & w2
```

### Least response time

```mermaid
flowchart LR
rule@{shape: text, label: "pick server with min(active conn * Least TTFB) for equal follow round robin"}
s2@{shape: text, label: "Active connections: 1"}
s1@{shape: text, label: "Active connections: 2"}
w1@{shape: text, label: "TTFB: 1"}
w2@{shape: text, label: "TTFB: 2"}

client1 & client2 & client3 & clientn ---> LB ---> server1 & server2
LB ~~~ rule
server1 ~~~ s1 & w1
server2 ~~~ s2 & w2
```

**TTFB** -> Time to first byte i.e. time interval BW sending a request and receiving response from the server, it is computed dynamically

---

# Related

---

# References / Sources

![Yt Video](https://www.youtube.com/watch?v=vJYycNWAYZU\&list=PL6W8uoQQ2c63W58rpNFDwdrBnq5G3EfT7\&index=18)
