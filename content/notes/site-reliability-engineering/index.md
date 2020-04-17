---
title: "Site Reliability Engineering"
date: 2020-02-10T19:40:40+11:00
authors: [glennji]
draft: false
type: note

# layout: quote, tweet, profile ... ?

crosslink: "true"
categories: []
tags: []
---

**Site Reliability Engineering** (**SRE**) is a discipline that incorporates aspects of software engineering and applies them to infrastructure and operations problems. The main goals are to create scalable and highly reliable software systems. According to Ben Treynor, founder of Google's Site Reliability Team, SRE is "what happens when a software engineer is tasked with what used to be called operations." First described and implemented by Google, SRE has become a key part of [DevOps Practices](https://42.industrieit.com/display/ODP/DevOps+Practices) and applies to any sufficiently complex product or service that is supported within, and by, a particular organisation i.e. both customer facing applications and internal systems can be operated according to the principles of SRE.

You can think of SRE as a specific *implementation* of DevOps principles.

## Focus on "engineering"

> By design, it is crucial that SRE teams are focused on engineering. Without constant engineering, operations load increases and teams will need more people just to keep pace with the workload. Eventually, a traditional ops-focused group scales linearly with service size: if the products supported by the service succeed, the operational load will grow with traffic. That means hiring more people to do the same tasks over and over again.

## Principles

Google talks about the following principles:

1. Embracing risk
2. Error budgets, SLOs and SLIs
3. Eliminating toil
4. Monitoring
5. Automation
6. Simplicity