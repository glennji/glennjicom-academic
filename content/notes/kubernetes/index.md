---
title: "Kubernetes"
date: 2020-01-17T10:37:35+11:00
authors: [glennji]
draft: false
type: note

# layout: quote, tweet, profile ... ?

crosslink: "true"
categories: []
tags: []
---
Kubernetes ("k8s") is an opensource container orchestration platform which allows for the deployment of scalable, fault-tolerant and diverse workloads in the form of containerised services/applications. It provides service-discovery, load-balancing, health monitoring and configuration management (including secrets) and provides compute, network and storage "infrastructure as a platform" which can be deployed to either cloud-based or traditional services/infrastructure.

See also:

- EFK
- Helm
- Istio
- Keel
- Knative
- Prometheus / Thanos
- Awesome Kubernetes Devops

## Components
A Kubernetes cluster consists of several components, which can be grouped into "master" (cluster-level: scheduling, replication, state-maintenance, API) and "node" (i.e. run on every node in the cluster).

### Master components
- kube-apiserver — provides programmatic access to the cluster to add, remove and modify pods, services, configuration, etc.
- etcd — distributed KVS used as configuration store
- kube-scheduler — the work scheduler, which determines which nodes a given pod should be run upon
- kube-controller-manager (KCM) — node controller which responds to node health and replication
- cloud-controller-manager (CCM) — analogous to the KCM above, but cloud-specific implementation
- cluster DNS (technically an "addon", but essential) — provides in-cluster service naming

### Node components
- kubelet — agent that ensures node and pods remain healthy
- kube-proxy — service abstraction via connection forwarding
- container runtime — e.g. docker




