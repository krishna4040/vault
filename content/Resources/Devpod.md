---
publish: true
created: 2025-02-08
modified: 2026-10-15T16:16:14.554Z
published: 2026-10-15T16:16:14.554Z
tags:
  - resource
  - system-design
  - cloud
project: "[[System Design]]"
description:
author:
reference: https://devpod.sh/docs/what-is-devpod
cover:
type: literature
---

# What is Devpod?

DevPod uses the [open `devcontainer.json` standard](https://containers.dev/) to allow users to customize their development containers.
Development containers are Docker containers that provide a user with a fully featured development environment. so they are stored in as container in local machine
Within DevPod, this container is created based on the underlying provider either locally, in a remote virtual machine or even in a Kubernetes cluster.

You can configure this development container for a certain git repository so that each workspace gives you a custom development environment completely configured with the tooling and runtimes you need for working on that specific project.
If DevPod doesn't find any configuration for the project it will automatically detect the programming language and provide a sane default configuration.
