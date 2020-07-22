---
title: "Operational Readiness"
date: 2020-02-10T19:43:10+11:00
authors: [glennji]
draft: false
type: note

# layout: quote, tweet, profile ... ?

crosslink: "true"
categories: []
tags: []
---

> The capability of a unit/formation, ship, weapon system, or equipment to perform the missions or functions for which it is organized or designed.
>
> — Dictionary of Military and Associated Terms. US Department of Defense 2005.

At an operational level, Operational Readiness refers to the pre-operation activities that ensure a system is ready for use. This may include documentation, handover/training, testing (scalability, concurrency, "destruction testing") and creation of appropriate roles and processes for the successful operation of the system going forward. For a software system which is likely to undergo continuous development and improvement, the activities should include provision of a CI/CD system.

From a DevOps perspective, it should also include systems which support *observability* and *supportability.* This should include monitoring, metrics, dashboards, alerting and escalation procedures.

# Site Reliability Engineering (SRE)

> **Site Reliability Engineering** (**SRE**) is a discipline that incorporates aspects of software engineering and applies them to infrastructure and operations problems. The main goals are to create scalable and highly reliable software systems. According to Ben Treynor, founder of Google's Site Reliability Team, SRE is "what happens when a software engineer is tasked with what used to be called operations."

... *contrast SRE from operations now ...*

# Operational Readiness Review

## Review checklist

- Performance tests for projected peak load complete (and passed)
- DRP created
- Security & encryption (e.g. in transit, at rest) documented
- Platform Register created (part of the knowledgebase)
- Incident management process established
- Monitoring enabled (external)
- Logs are accessible
- On-call and support schedules created
- Automated, repeatable builds (CI/CD)
- Automated regression tests
- Incident management process documented, including escalation and SLAs/SLOs/SLIs
- Playbooks
- Troubleshooting guides
- ...

## Supportability

*What makes a system supportable? Thoughts*.

- Monitoring (dashboards for proactive, "preactive" remediation and projection as well as "current state" analysis)
- Alerting (dashboards, integration with existing messaging systems, escalation)
- Knowledge-base: troubleshooting and playbooks



## Observability

...

## Handover

A typical timeline will involve a certain amount of "crossover" between the project delivery and "production". It's also pretty common these days for project (delivery) engineers to become "operators" to some degree; indeed, that's one of the tenets of [Continuous Delivery](https://42.industrieit.com/display/ODP/Continuous+Delivery) ("you build it, you run it"). As such, the incentives faced by a software engineer may change during the transition from "new features" to "supportable software". Nobody wants to wake up at 3am for no good reason ...