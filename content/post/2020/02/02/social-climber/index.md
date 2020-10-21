---
title: "Social Climber"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-02-02T18:00:43+11:00
lastmod: 2020-02-02T18:00:43+11:00
featured: false
draft: false
crosslink: "true"

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
projects: []
---

I was speaking to a friend over bubble tea on Friday, and started trying to explain the unexpected side-effect of practicing "sufficiency meditation"[^1] — that is, generating a feeling of satisfaction (with the moment, life, career, hobbies, physical fitness, abilities, bank balance and/or whatever) and then "sitting with" that feeling, putting enough energy into it to keep the feeling "on", and carefully but strongly steering thoughts away from doubts and disatisfaction. "I always felt like there were things I *should* be doing," I lamented, "but now I'm trying to be happy with what *is*. Ironically, perhaps, it has lead to me actually *doing* some of the things I thought I 'should' be — rather than the opposite."

Even better, I explained, because I'm satisfied with my place in life I am actually free to think about things more creatively, such as e.g. finding ways to combine family fun time with my son with the hobbies and stuff I've always wanted to try. To this end, we've just had a weekend of robotics, games dev and climbing, all "dad and boy"-time and all super fun.

## Robotics

Yesterday we built a "[Mini Tank Robot](/projects/mini-tank-robot)" together, although truth be told I did almost all of the building. It was surprisingly straightforward, and I even integrated an extra servo that I had lying around from an Arduino experimenters kit, then hacked together some basic code using the ultrasonic sensor[^3]  and the two "neck" servos. The bot doesn't have a name yet, so I'm going to call him Wally (WALL-E) until Jules objects and picks something else. He doesn't move yet either, but I've ordered the Li-ion batteries he needs for his DC motors so soon he'll be fully autonomous.

There's a "Blockly-like" programmng kit as well, which I'd love for Jules to try, but in the meantime it does look like the Arduino IDE will do anything I can think of doing. (Anybody know a good pattern for "state machine" operation? I'll Google it.) And if he's not into it, well, we're also building a game with Unity.

## Games Development

I can't remember *exactly* how the conversation that kicked off this activity went, but J has been a pretty big gamer for a while now: first on the Playstation, then his Xbox One (birthday) and now the Nintendo Switch (Christmas). Some of his creations in Minecraft are startling, and he's been building levels in Super Mario Maker 2 for his mother to try to beat, so when we started talking about making a game he was really into it.

Inspired by Mario, we're building a 2D platformer (based on the Unity tutorial level) called ***Super Mecha Bros*** in which two brothers don Ironman-like mech-suits to rescue their kittens from an armoured menace ... named "Super Mecha Bowser" (working title). As our intrepid warriors progress they'll find armour powerups — missiles, rocket boosters, climbing spikes — and face robotic enemies and automated security systems as they break into a high-tech stronghold. Save the kittens!

Right now, well, we've changed the colour of the standard "player" sprite in the Unity platformer tutorial and mucked about with speed and jump settings to great amusement: launching our little red man off the map and into "glitch space" with reckless abandon. But fun! So much fun!

## Climbing

Today we headed to Skyzone, got into our harnesses and scaled the walls.

It's an indoor climbing "playground" with an automated belay system, so the idea is that you climb a variety of walls (what, 12 metres?) and hit the buzzer at the top, then *let go* and be lowered slowly to the ground ... but of course it's a lot scarier than that! Jules was such a trooper, although really scared and didn't get too far off the ground at all, but by the end of our hour we were both exhausted, sweaty and in need of an ice-cream.

## What's next?

So that's that! Finding stuff Jules and I can do together continues and I'm absolutely loving it. We have a few ideas for the future, too: skateboarding, drum lessons, maybe the climbing thing at the zoo? Bouldering, go-karting, making (and sailing) some paddlepop-stick boats, even perhaps an underwater ROV. All fun, and all things I kind of want to do anyway, so getting to do them with the fam is just a cherry on top.



[^1]: If you've ever done *metta* or "loving kindness" meditation,  it's the same technique, just a different feeling that is continually generated. I also suspect it's possible to do with any feeling, so may be a future avenue of experimentation.
[^3]: HC-SR04, which seems to be the most common sensor of this type but is also tricky to get accurate. Temperature adjustment libraries exist however, so maybe I have a thermometer in the experimenters' kit too?
