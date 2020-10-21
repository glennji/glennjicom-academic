---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Ortholinear Awkwardness"
subtitle: ""
summary: ""
authors: [glennji]
tags: []
categories: []
date: 2020-08-19T16:16:10+10:00
lastmod: 2020-08-19T16:16:10+10:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [idobo75]
---

My new keyboard arrived last night, and I've been awkwardly typing on it ever since.

The keyboard arrived in several pieces -- the PCB, keycaps and case all neatly packed in a large white box -- and it was a pleasant couple of minutes putting it together with Kailh brown switches I already had on hand in the layout shown above. And then I realised I had no idea how to flash the thing.

Because, naturally, this is a programmable keyboard. QMK-compatible in fact!

A Google-search later and I had QMK Toolbox installed; a few more minutes and I'd downloaded my prepared layout firmware from an online editor flashed it! A working keyboard! Hurrah!

Assembling the 'board and having a bit of a play with it made me realise that I already wanted to change the layout. Which would be fine (that's the point) except for the fact that the keyboard needs to be booted into 'flash' mode for firmware changes, and the only way to do that is by pressing the appropriate button.

On the bottom of the PCB.

Which I'd just screwed into the aluminium case. Oops.

So I left the layout as it was for a couple of days, thinking that perhaps I would be able to reprogramme _myself_ instead, but tonight I bit the bullet and took the thing apart again for reflashing. This time, however, I made sure I designed a layout that included a flash-mode key combination!

I still haven't gotten the hang of things yet, but I'm already less awkward and think it's just a matter of time now. So much fun and experimentation to be had!