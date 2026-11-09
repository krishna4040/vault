---
publish: true
created: 2025-02-12
modified: 2026-10-15T16:16:14.557Z
published: 2026-10-15T16:16:14.557Z
tags:
  - resource
  - system-design
  - HLD
author: shreyansh jain
lecture: 24
project: "[[System Design]]"
description:
reference:
cover:
type: literature
---

# OAUTH

OAUTH stands for _Open authorization_
Why it is used?

- It's a Authorization framework
- Enables secure third party access to user protected data

```mermaid
flowchart LR
third["Third party website with sign in with google"]
gmail["contains user protected data"]
user -->|gives permission to access his protected data| third --> gmail --> third
```

4 important roles or actors involved in it:

- Resource owner
- client
- Authorization server
- Resource hosting server

Authorization Grant Types(mechanism used by client to get access token):

- Authorization code grant

## Authorization code grant

```mermaid
sequenceDiagram
participant R as Resource owner
participant C as Client(instagram)
participant AS as Gmail (Authorization server)
participant RS as Gmail (Resource server)
C -->> AS: 1. Registration
AS -->> C: 2. client Id & secret
R -->> C: 3.Sign in using Gmail
C -->> AS: 4. Redirect owner to AS
AS -->> C: 5.provides Authorization code
C -->> AS: 6.Request token using Authorization code
As -->> C: 7. provides Access token & Refresh token
C -->> RS: 8. Request protocted data using Access token
RS -->> AS: 9. validate the Access token
As -->> RS: 10. valid/ invalid
RS -->> C: 11.if valid provide protected data else 4XX error
```

### Sample API

#### Registration process:

```http
POST /register
Request 
{
	client_name: {my app name},
	redirect_uris: ["https://mywebsite.com/"]
}
Response 
{
	client_name: {my app nam},
	client_id: {unique id assigned},
	client_secret: {confidential info client and AS know},
}
```

#### Fetch Authorization code

```http
GET /authorize?
	response_type=code
	&client_id={id which}
	&
```

---

# Related

---

# References / Sources

[Yt Video](https://www.youtube.com/watch?v=3Gx3e3eLKrg\&list=PL6W8uoQQ2c63W58rpNFDwdrBnq5G3EfT7\&index=24)
