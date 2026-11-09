---
publish: true
title: If You Still Don’t Understand JWT, Watch This | JWT Crash Course 2025 🔥| In Hindi | Day 39/100
description: "In this video, we’ll understand what JWT (JSON Web Token) is, how it works, and why it’s used for authentication. You’ll learn how JWT ensures secure login and communication between client and server.🌟 Unlock full premium MERN+ course: https://codersgyan.com/courses/mern?coupon=launch&utm_source=youtube&utm_medium=video_description&utm_content=link_in_description&utm_campaign=jwt_day_39🌟Master how to build GENAI products using JS: https://codersgyan.com/courses/genai?coupon=launch&utm_source=youtube&utm_medium=video_description&utm_content=link_in_description&utm_campaign=jwt_day_39Or even better:🎉 Get all current & future course access:https://codersgyan.com/membership?coupon=launch&utm_source=youtube&utm_medium=video_description&utm_campaign=membership&utm_content=link_in_description&utm_campaign=jwt_day_39--------------------- CHAPTERS---------------------00:00 - Intro01:12 - Authentication 02:58 - Stateful approach13:50 - Stateless approach18:57 - What is JWT ???23:15 - Dissect JWT !!33:54 - Most Important Question 138:13 - Most Important Question 244:39 - Most Important Question 346:58 - An Important ConceptHow do I build Scalable JWT Authentication in my applications?Watch this: https://youtu.be/IHc9iYj5wp0Watch the complete playlist 100 days of learning: https://www.youtube.com/playlist?list=PLXQpH_kZIxTUXUW8ZkKy_-tIUeYDSCFP7Follow me 💛: https://discord.gg/YqWdeapPHQhttps://www.linkedin.com/in/codersgyan/https://x.com/codersGyan#100dayschallenge #100daysoflearning"
created: 2025-10-11
modified: 2026-10-15T16:16:14.551Z
published: 2026-10-15T16:16:14.551Z
tags:
  - resource
  - system-design
  - HLD
socialImage: https://i.ytimg.com/vi/j1C8gZkIRKc/maxresdefault.jpg
source: https://www.youtube.com/watch?v=j1C8gZkIRKc&t=3s
author: shreyansh jain
cover: https://i.ytimg.com/vi/j1C8gZkIRKc/maxresdefault.jpg
lecture: 29
genre: Education
project: "[[System Design]]"
reference:
type: literature
---

# Authentication

```mermaid
flowchart TD
Authentication --> Stateful & Stateless
Stateful --> Sessions
Stateless --> JWT
```

# Sessions (Stateful)

```mermaid
flowchart LR
client -->|login| server -->|sessionId in cookie| client
```

It is harder to scale server horizontally, as the server saving the session Id may not serve the authenticated request which was earlier served by the server that generated the session Id.
To solve this we introduced `sticky sessions` in load balancer that ensures the request for a user is served by a server that generates its sessions

```mermaid
flowchart LR
client --> LB --> s
s@{shape: processes, label: server}
LB ~~~ C
C@{shape: text, label: "configured sticky session"}
```

Not to configure sticky sessions, we can store the session ids in an in memory database like Redis

```mermaid
flowchart LR
client --> LB --> s --> D
s@{shape: processes, label: server}
D@{img: https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-original.svg, label: Redis}
```

But this storage is expensive

# JWTs

JWTs can be stateless or semi stateless

```mermaid
sequenceDiagram
    participant User
    participant ClientApp as Client / Frontend
    participant AuthServer as Auth Server
    participant ResourceServer as Resource Server
    participant Attacker as Attacker

    %% --- Normal JWT Flow ---
    Note over User,AuthServer: Normal JWT Authentication Flow
    User->>ClientApp: Login with credentials
    ClientApp->>AuthServer: Send credentials (username/password)
    AuthServer-->>ClientApp: Issue JWT + Refresh Token
    ClientApp->>ResourceServer: Send JWT in Authorization header
    ResourceServer-->>ClientApp: Return protected resource

    %% --- JWT Expiry & Refresh ---
    Note over ClientApp,AuthServer: Token Refresh
    ClientApp->>AuthServer: Send Refresh Token (to get new JWT)
    AuthServer-->>ClientApp: Issue new JWT (and optional new Refresh Token)
    ClientApp->>ResourceServer: Use new JWT
    ResourceServer-->>ClientApp: Resource Access continues

    %% --- JWT Compromise Scenario ---
    Note over Attacker,ResourceServer: JWT Compromise
    Attacker->>ResourceServer: Send stolen JWT
    ResourceServer-->>Attacker: Access granted (until expiry)

    %% --- Refresh Token Compromise Scenario ---
    Note over Attacker,AuthServer: Refresh Token Compromise
    Attacker->>AuthServer: Send stolen Refresh Token
    AuthServer-->>Attacker: Issue new JWT (+ optional new Refresh Token)
    AuthServer-->>ClientApp: Invalidate old refresh token (rotation)

    %% --- Token Rotation Flow ---
    Note over ClientApp,AuthServer: Token Rotation
    ClientApp->>AuthServer: Send Refresh Token A
    AuthServer-->>ClientApp: Issue new JWT + Refresh Token B
    AuthServer-->>AuthServer: Mark Refresh Token A as "used" or "invalid"
    Attacker->>AuthServer: Try using stolen Refresh Token A
    AuthServer-->>Attacker: Rejected (reuse detected)
```

---

# References

![](https://www.youtube.com/watch?v=j1C8gZkIRKc\&t=3s)
