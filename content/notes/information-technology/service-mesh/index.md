---
title: "Service Mesh"
author: glennji
date: 2019-05-24T08:24:45+10:00
draft: false
type: note
crosslink: "true"
categories:
  - Networking
---
A _service mesh_ is a network of cooperative and interacting services (i.e. microservices) and the communications between them, or the system for managing such a collection. Service meshes often include service discovery and runtime-configurable routing, allowing for things like:

  * load-balancing & failure recovery
  * A/B testing
  * "canary", blue-green and other deployment patterns
  * authentication & access control
  * request tracing
  * dark releases

Istio and Traeffik are examples of service meshes on Kubernetes.
