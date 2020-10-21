---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Reviving an Opensource Project"
subtitle: ""
summary: ""
authors: [glennji]
tags: []
categories: []
date: 2020-01-18T13:00:44+11:00
lastmod: 2020-01-18T13:00:44+11:00
featured: false
draft: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [openlumify]
---

For the last couple of weeks I've been attempting to revive an opensource project called **[Openlumify](/projects/openlumify)**.

The project is an "[intelligence amplification](/notes/terms/intelligence-amplification) platform" — import a bunch of data about "stuff", then explore connections (graph), proximity (map) and temporality (timeline) in a human-directed investigation from any one data-point, such as starting with an "known POI", expanding the search to associates (via call records, emails, aliases, sightings, co-ownership, etc), and plotting related events on a timeline and/or map to test a hypotheses, gather evidence or just understand a given situation.

(IMO, the value largely comes from the import ("ingestion") — pulling from different sources including OSINT and in-house datastores and programmatically deriving entities and their relationships. We had a similar system at [a company I used to work for](/cv) and it was surprisingly satisfying to see it work:  thousands of documents being ingested and processed to match IP addresses, phone numbers and names against log files, call records and criminal databases. I might not have access to these datasources any more, but it could still be fun to process my personal mailbox, or plot political machinations, or analyze history, or ... there are just so many use-cases.)

So yeah, I've wanted a platform for this for ages, obsessed as I am with mind-maps and relationship graphs, and have kept an eye on the precursor to Openlumify for a number of years. The codebase was originally an opensource ([Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0.html)) product called Lumify, by the company of the same name, but was subsumed and/or renamed by Altamira, then Visallo, before the source was closed. (Assume it is still being worked on behind closed-doors, but haven't even attempted to confirm that.) 

The codebase I have, then, is a fork of a fork (...) that has at least the most basic functionality — and I've finally managed to get it building again! (If that doesn't sound exciting to you, I'm guessing you've never worked on a multi-module Maven project from 2015.)

I'm driven to ensure it remains opensource, so I'll be doing whatever I can to make it easier for other developers to get started using the platform, and hopefully some will get involved in the project. To this end, I've created a [organization on Github](https://github.com/openlumify) to host any/all repos, [manage bugs and features](https://github.com/openlumify/openlumify/projects), and collect and author documentation. I've also made a start on a [product website](https://openlumify.org/), which definitely needs work.

