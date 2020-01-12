---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Open Lumify"
subtitle: ""
summary: ""
authors: [glennji]
crosslink: "true"
tags: ["inprogress", "hobby", "software"]
categories: [Opensource]
date: 2019-11-14T00:17:54+11:00
lastmod: 2019-11-14T00:17:54+11:00
featured: false
draft: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: "https://github.com/glennji/openlumify"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

I worked for a "data discovery and analytics platform" company[^1] for a couple of years, and got to see first-hand the power of graph-based datastores for analysis, hypothesis-testing and pattern discovery. It truly was an example of intelligence amplification and allowed the analysts I worked with to work more effectively than ever.

Since that day I've had a desire to map things out, to build a kind of mega-mindmap[^2] to really understand some of the more complex and complicated situations — ancient and modern history, the middle east, US politics, the powerful people behind every conspiracy theory imaginable...

So I was quite happy to see that someone somewhere had started an opensource graph-based analysis suite of a similar sort. Unfortunately by the time I found it, it had become abandonware, moving from open- to (assumed) closed-source by the IP owner, who was then bought by another company, then again, renamed, _ad absurdum infinitum_. I grabbed the last opensource I could find and have started on the long journey to revive it.

So far I've updated the build (Maven! Eek) to work with Java 9+ and refactored everything to the`org.openlumify` package. It builds, it runs ... but I can't login.

If only there were more hours in the night or day!

## Some plans 

In no particular order ...

* get it running
* build containers
* make it work in Kubernetes
* add dark mode
* make sure it has a timeline and a map (at least!)
* pick a decent backend datastore and implement it
* setup a project website
* replace Maven with Gradle
* host it somewhere online e.g. for investigative journos
* ...
* karma!

[^1]: I don't want to say their name, even after all these years, since I once tweeted the name — quite innocuously — and it eventually came back through the 'peer network' (no hierarchies, man). Probably not a huge deal, but I was super creeped out that they were actively watching for public mentions and performing sentiment analysis and someone _with fewer than a hundred followers_ would actually catch any attention at all.
[^2]: Hey, I've loved mindmaps since the day I discovered them. Feels like I've been drawing and redrawing the same few maps — with alterations — for most of my life, anytime I was feeling lost or overwhelmed. Most recently I've recreated them in Simplemind, but there are notebooks upon notebooks exploring my plans, desires, perceived strengths and weaknesses. 