---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.554Z
published: 2026-10-15T16:16:14.554Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 16
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# Interview Questions Based on Messaging Queues

1. What is messaging queue? why its needed and its advantages?
2. what is the difference **Pub/Sub** and **point to point** messaging queues?
3. How messaging queues work? **Kafka** and **Rabbit MQ**
4. What happens when queue size limit is reached?
5. What happens to messages when queue goes down
6. What happens when consumer goes down?
7. What happens when consumer not able to process message?
8. How **Retry** works? Different ways to retry?
9. How Distributed Messaging Queues works?
10. What is **Dead Letter Queue** ?

# Messaging Queues And Why it is needed?

```mermaid
flowchart LR
Producer -->|MSG| Queue --> Consumer
```

![ms](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb6eab95c-f56f-45c7-9248-7e6070c1979b_1614x702.png)

## USAGE

- **Asynchronous nature** -> latency gets reduced
- Producer can send message directly to consumer? **No Retry Capability** Messaging queues bring Retry capability, when consumers unable to consume message, it put it back in the queue

# Point To Point VS PubSub

### P2P

Message can be consumed by only 1 consumer

```mermaid
flowchart LR
Publisher -->|msgA| Queue
Queue -->|msgA ✔️| Consumer1
Queue -->|msgA ❌| Xonsumer2
```

## PubSub

Message can be consumed by multiple consumers

```mermaid
flowchart LR
Publisher --->|msgA| Exchange --> Queue1 & Queue2
Queue1 -->|msgA ✔️| Consumer1
Queue2 -->|msgA ✔️| Consumer2
```

# Message Queues Working

---

## KAFKA

> Kafka is Pull based approach

**Components**

1. Producer
2. Consumer
3. Consumer Groups
4. Topic
5. Partition
6. Offset
7. Broker(Kafka server)
8. Cluster
9. Zookeeper

**Architecture**

```mermaid
flowchart LR
	producer
	subgraph broker
		subgraph topic1
			subgraph partition11
				o1@{label: offset 1}
				o2@{label: offset 2}
				o3@{label: offset 3}
			end
			subgraph partition12
				o4@{label: offset 1}
				o5@{label: offset 2}
				o6@{label: offset 3}
			end
		end
		subgraph topic2
			subgraph partition21
				o7@{label: offset 1}
				o8@{label: offset 8}
				o9@{label: offset 9}
			end
			subgraph partition22
				o10@{label: offset 1}
				o11@{label: offset 2}
				o12@{label: offset 3}
			end
		end
	end
	producer --> broker
	subgraph consumer-group-1
		c1@{label: consumer 1}
		c2@{label: consumer 2}
	end
	subgraph consumer-group-1
		c3@{label: consumer 1}
		c4@{label: consumer 2}
	end
	c1 --> partition11
	c1 -->|❌| partition12
	c2 --> partition12

	c3 --> partition11
```

```mermaid
flowchart LR
subgraph cluster
	broker1
	broker2
	broker3
	broker4	
end
producer --> cluster
broker1 & broker2 & broker3 & broker4 --> zookeeper
```

**Working**

```bash
msg = {
	key?: "id",
	value: "msg",
	partition?: "partition1",
	topic: "topic name"
}
```

```mermaid
flowchart LR
producer
subgraph TopicA
	subgraph P0
		o1
		o2
		o3
	end
	subgraph P1
		o4@{label: o1}
		o5@{label: o2}
		o6@{label: o3}
	end
	subgraph P2
		o7@{label: o1}
		o8@{label: o2}
		o9@{label: o3}
	end
end
producer -->|msg hash key or partition or round robin| o1
subgraph consumer-group-1
	consumer1
end
zookeeper(
	zookeeper
	consumer1
	CG1
	TopicA
	P0
	Committed offset = 3
)
```

if Consumer 1 goes down then zookeeper will pick another consumer from the same consumer group and it will start consuming data from the committed offset where the previous consumer left reading

**Distributed system case**

```mermaid
flowchart LR
P0L(P0 Leader)
P0R(P0 Replica)
P1L(P1 Leader)
P1R(P1 Replica)
	subgraph cluster
		subgraph broker1
			subgraph topic11
				P0L
			end
		end
		subgraph broker2
			subgraph topic11
				P0R
			end
			subgraph topic12
				P1L
			end
		end
	end
	P0L --->|Replica|P1R
```

---

## RabbitMQ

> RabbitMQ is Pull based approach

```mermaid
flowchart LR
exchange1{exchange1}
exchange2{exchange2}
producer --> exchange1 & exchange2
exchange1 --> Queue1 & Queue2
exchange2 --> Queue2 & Queue3
```

**Fanout** -> It will push the message to all the queues related to a message
**Direct Exchange** -> Routing key is defined for msg schema and queue
**Topic Exchange** -> wildcard matching to push a msg to specific queue
**Consumer Fails** -> it put backs in the queue back for retry when retry exceeds it puts in the dead letter queue
