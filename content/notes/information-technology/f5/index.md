---
title: "F5"
date: 2020-04-14T13:56:43+10:00
authors: [glennji]
draft: false
type: note

# layout: quote, tweet, profile ... ?

crosslink: "true"
categories: []
tags: []
---

# F5

Founded in 1996 with a load balancer ("BIG-IP"). This would detect when a server went down and redirect traffic to another server in the traffic group. Since then, the BIG-IP product family has grown to include:

1. Local Traffic Manager (LTM)
2. Application Security Manager (ASM)
3. Access Policy Manager (APM)
4. Advanced Filewall Manager (AFM)
5. IP Intelligence (IPI)
6. WebSafe
7. BIG-IP DNS

## BIG-IP LTM

Local Traffic Manager

DSC = Device Service Clustering i.e. "active-standby" of the BIG-IP device

# BIG-IP WAF

WAF = "web application firewall"

L7 (application) in the OSI model

Parses the HTTP request

OWASP Top 10

PCI Compliance

Response rewrite/mask (e.g. detect CC numbers and mask them)