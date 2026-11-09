---
publish: true
created: 2025-02-19
modified: 2026-10-15T16:16:14.551Z
published: 2026-10-15T16:16:14.551Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 28
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

IF **API Gateway** a single entry point, how does it handle millions of request per second?
also
How **API Gateway** is different from load balancer? Does it comes before or after load balancer?

# What is API Gateway

In simple terms, it accepts the client API request and routes them to correct backend service based on API endpoint.

```mermaid
flowchart LR
gateway[API Gateway]
s1[invoice service]
s2[order service]
s3[sales service]
client ---> gateway ---> s1 & s2 & s3
```

**Isn't this what load balancer also does?**
No, Generally load balancer simply distribute the traffic to the multiple instances of  a microservice based on various factors like health, traffic load, etc.
But usually they dont have capability to understand an API and then take decision to route it.

```mermaid
flowchart LR
n@{shape: text, label: " "}
s1[invoice microservice 1]
s2[order microservice 2]
s3[payment microservice 3]
n --->|api| LB ---> s1 & s2 & s3
```

Apart from routing api gatewaus does more

## 1. API Composition

problem: lets say, we are visiting **My orders** page.

```mermaid
flowchart LR
t1@{shape: text, label: "Mobile device client"}
api[REST API]
t2@{shape: text, label: "Api to fetcj Product Details"}
t3@{shape: text, label: "Api to fetch invoice Details"}
t1 ---> api ---> t2 & t3
```

```mermaid
flowchart LR
t1@{shape: text, label: "PC device client"}
api[REST API]
t2@{shape: text, label: "Api to fetcj Product Details"}
t3@{shape: text, label: "Api to fetch invoice Details"}
t4@{shape: text, label: "Api to fetch Reccomendation Details"}
t5@{shape: text, label: "Api to fetch Rating Details"}
t1 ---> api ---> t2 & t3 & t4 & t5
```

Solution using api composition

```mermaid
flowchart LR
t1@{shape: text, label: "PC device client"}
api[Gateway for configuration]
t2@{shape: text, label: "Api to fetch Product Details"}
t3@{shape: text, label: "Api to fetch invoice Details"}
t4@{shape: text, label: "Api to fetch Reccomendation Details"}
t5@{shape: text, label: "Api to fetch Rating Details"}
t1 ---> api ---> t2 & t3 & t4 & t5
```

## 2. Authentication

```mermaid
flowchart LR
AS[Authorization server]
api[API Gateway]
client --->|2 - pass token in request| api
client --->|1- get access token| AS
AS ---> api --->|3- validates token| AS
api --->|4- if token is valid| s1 & s2 & s3
```

## Rate limiting

We can set rules like:

#### Manage Burst limit:

Use to limit the Burst traffic, means max no. of concurrent request that AOU Gateway can handle before it returns 429(Too many requests)

#### API Throttling

Limiting the number of requests from an individual or an application by temp blocking the request, once they ceossed the allowed request rate.

#### IP Based blocking

#### API Queues

Hold requests to an API, which can not be processed immediately. It helps to handle the Thundering herd effect

## Service Discovery

As mivrosevices can scale up and down, its necessary to know the location(IP  address and Port). Service Discovery keep tracks of those.

- **Approach1** -> Each Microservice register or de register themselves.
- **Approach2** -> Service Discovery, keeps health check of all the registered microservices and keep only active microservices location.

```mermaid
flowchart LR
sd[Service discovery]
client --->|"1- /api/order"| api
api ---> sd ---> api
api ---> s1 & s2 & s3
```

And many other capabilities like:

- Request Response transformation
- Response caching
- Logging

Now lets come back to question
**If api gateway is a single  entry point, how does it handle millions of requests per second?**

```mermaid
flowchart LR
client
lb1[Load Balancer]
lb2[Load Balancer]
lb3[Load Balancer]
lb4[Load Balancer]
lb5[Load Balancer]
lb6[Load Balancer]
lb7[Load Balancer]
lb8[Load Balancer]

s1@{shape: st-rect, label: service1}
s2@{shape: st-rect, label: service2}
s3@{shape: st-rect, label: service3}
s4@{shape: st-rect, label: service4}
s5@{shape: st-rect, label: service5}
s6@{shape: st-rect, label: service6}
s7@{shape: st-rect, label: service7}
s8@{shape: st-rect, label: service8}

api[API Gateway]
sd[Service discovery]
api1[API Gateway]
sd1[Service discovery]

subgraph Reigon1
	subgraph AZ1
		lb1 ---> s1
		lb2 ---> s2
	end
	subgraph AZ2
		lb3 ---> s3
		lb4 ---> s4
	end
	sd --> api --> sd
	api --> AZ1 & AZ2
end

subgraph Reigon2
	subgraph AZ3
		lb5 ---> s5
		lb6 ---> s6
	end
	subgraph AZ4
		lb7 ---> s7
		lb8 ---> s8
	end
	sd1 --> api1 --> sd1
	api1 --> AZ3 & AZ4
end

client --> DNS --> Reigon1 & Reigon2
```

---

# Related

[[Web servers and API gateways]]

---

# References / Sources

![Yt Video](https://www.youtube.com/watch?v=dkgxvnk8cWw\&list=PL6W8uoQQ2c63W58rpNFDwdrBnq5G3EfT7\&index=28\&t=253s)
