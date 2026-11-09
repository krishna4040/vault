---
publish: true
title: How does a browser work ? | Engineering side
description: "Welcome to a youtube channel dedicated to programming and coding related tutorials. We talk about tech, write code, discuss about cloud and devops. That’s what we do all day, all year. We roll out a lot of series and videos on our channel.All the learning resources such as code files, documentations, articles and community discussions are available on our website:https://chaicode.com/You can find our discord link, github link etc on the above website. Twitter/X link: https://x.com/hiteshdotcomDiscord link: https://hitesh.ai/discordLearn React with 10 projects: https://www.youtube.com/watch?v=eCU7FfMl5WU&list=PLRAV69dS1uWQos1M1xP6LWN6C-lZvpkmqLearn Docker: https://youtu.be/rr9cI4u1_88?si=fSK00PNOt0gqBXp6Learn Kubernetes: https://www.youtube.com/watch?v=7XDeI5fyj3wHow does a browser works: https://youtu.be/5rLFYtXHo9s?si=UW1HrwGUzkk4E7qhHow nodejs works: https://youtu.be/ooBxSg1Cl1w?si=Ks6Wih1smJZSDz4VLearn Redux-toolkit: https://www.youtube.com/watch?v=pX0SBJF01EULearn NextJS: https://www.youtube.com/watch?v=iPGXk-i-VYU&list=PLRAV69dS1uWR7KF-zV6YPYtKYEHENETyELearn Typescript: https://www.youtube.com/watch?v=j89BvWz8Eag&list=PLRAV69dS1uWRPSfKzwZsIm-Axxq-LxqhWLearn Javascript: https://www.youtube.com/watch?v=2md4HQNRqJA&list=PLRAV69dS1uWSxUIk5o3vQY2-_VKsOpXLDLearn React Native: https://www.youtube.com/watch?v=kGtEax1WQFg&list=PLRAV69dS1uWSjBBJ-egNNOd4mdblt1P4cLearn Zustand: https://www.youtube.com/watch?v=KCr-UNsM3vA&list=PLRAV69dS1uWQMXekDgw7fRAsHmsbKWkwuLearn Golang: https://www.youtube.com/watch?v=X4q1OM0voO0&list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N"
created: 2025-10-11
modified: 2026-10-15T16:16:14.555Z
published: 2026-10-15T16:16:14.555Z
tags:
  - resource
  - system-design
  - HLD
socialImage: https://i.ytimg.com/vi/5rLFYtXHo9s/maxresdefault.jpg
source: https://www.youtube.com/watch?v=5rLFYtXHo9s&t=1689s
author: shreyansh jain
cover: https://i.ytimg.com/vi/5rLFYtXHo9s/maxresdefault.jpg
lecture: 30
genre: Science & Technology
project: "[[System Design]]"
reference:
type: literature
---

# Browser

# How Browser works?

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Network
    participant Server
    participant HTMLParser
    participant CSSParser
    participant JSInterpreter
    participant RenderEngine
    participant Screen

    User->>Browser: Enter URL / Request Page
    Browser->>Network: HTTP Request
    Network->>Server: Fetch Resources
    Server-->>Network: Response (HTML, CSS, JS)
    Network-->>Browser: Receive Resources

    Browser->>HTMLParser: Parse HTML
    HTMLParser-->>Browser: DOM Tree

    Browser->>CSSParser: Parse CSS
    CSSParser-->>Browser: CSSOM

    Browser->>RenderEngine: Combine DOM + CSSOM
    RenderEngine-->>Browser: Render Tree

    Browser->>JSInterpreter: Execute JS
    JSInterpreter-->>DOMParser: Update DOM/CSSOM if needed

    RenderEngine->>RenderEngine: Layout & Paint
    RenderEngine->>Screen: Display Page

```

---

# Follow up

```tabs
tab: Next Lectures
| File | created |
| ---- | ------- |

tab: Previous Lectures
| File                                                                        | created           |
| --------------------------------------------------------------------------- | ----------------- |
| [[Resources/Web servers and API gateways.md\|Web servers and API gateways]] | February 08, 2025 |
| [[Resources/Authentication.md\|Authentication]]                             | October 11, 2025  |
| [[Resources/API gateway.md\|API gateway]]                                   | February 19, 2025 |
| [[Resources/Thunder herd effect.md\|Thunder herd effect]]                   | February 19, 2025 |
| [[Resources/JWT.md\|JWT]]                                                   | February 19, 2025 |

```

---

# References

![](https://www.youtube.com/watch?v=5rLFYtXHo9s\&t=1689s)
