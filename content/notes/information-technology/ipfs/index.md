---
title: "IPFS"
author: glennji
date: 2019-07-16T11:17:54+10:00
draft: false
type: note
crosslink: "true"
categories:
  - Technology
  - Networking
---
> The *InterPlanetary File System* is a peer-to-peer distributed file system that seeks to connect all computing devices with the same system of files ... [which] could be seen as a single BitTorrent swarm, exchanging objects within one Git repository.

IPFS attempts to address the distribution problems associated with centralised (client-server) file sharing, such as HTTP. It is composed of components which implement existing concepts:

  - Distributed hash tables
  - Block exchanges
  - Merkle DAG

Read: https://hackernoon.com/a-beginners-guide-to-ipfs-20673fedd3f

In short, content is stored on multiple machines in an IPFS system/network and referenced by a cryptographic hash of the content. This ensures content cannot be modified without detection.

Additionally, the IPNS (name system) associates an (signed) indirect link URI to a changeable IPFS address, allowing content creators to update content without needing to redistribute URIs on every change.
