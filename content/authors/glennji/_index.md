---
# Display name
name: ✍️ Glenn J. Mason

# Username (this should match the folder name)
authors:
- glennji

# Is this the primary user of the site?
superuser: true
crosslink: "true"

url: /about

# Role/position
role: Cloud + Data Geek / Coder / Futurist / Biohacker / Entrepreneur

# Organizations/Affiliations
#organizations:
#- name: Stanford University
#  url: ""

# Short bio (displayed in user profile at end of posts)
bio:

interests:
- "Dev: [Python](/notes/software-engineering/python), [Java](/notes/software-engineering/java), [React](/notes/software-engineering/react)"
- "[DevOps](/notes/devops) / [Kubernetes](/notes/kubernetes)"
- "[Big Data](/notes/big-data) / [AI](/notes/artificial-intelligence)"
- "[Robotics](/categories/robotics) & [Transhumanism](/notes/transhumanism)"

education:
  courses:
  - course: BSci (applied)
    institution: Swinburne University of Technology
    year: 2000
  - course: MBA
    institution: Swinburne University of Technology
    year: In Progress

# Social/Academic Networking
# For available icons, see: https://sourcethemes.com/academic/docs/widgets/#icons
#   For an email link, use "fas" icon pack, "envelope" icon, and a link in the
#   form "mailto:your-email@example.com" or "#contact" for contact widget.
social:
- icon: envelope
  icon_pack: fas
  link: "mailto:glenn@glennji.com"
- icon: twitter
  icon_pack: fab
  link: https://twitter.com/glennji
- icon: facebook
  icon_pack: fab
  link: https://www.facebook.com/glennji
- icon: github
  icon_pack: fab
  link: https://github.com/glennji
- icon: linkedin
  icon_pack: fab
  link: https://linkedin.com/in/glennji/


# Link to a PDF of your resume/CV from the About widget.
# To enable, copy your resume/CV to `static/files/cv.pdf` and uncomment the lines below.
# - icon: cv
#   icon_pack: ai
#   link: files/cv.pdf

# Enter email to display Gravatar (if Gravatar enabled in Config)
email: "glenn@glennji.com"

# Organizational groups that you belong to (for People widget)
#   Set this to `[]` or comment out if you are not using People widget.
user_groups: []

summary: Read more [about me](/about)
---

{{< figure src="/images/little-me.png" class="floatright" >}}**Well this was unexpected: I'm in my 13th incarnation[^3]!**

_This is the personal website of **Glenn J. Mason**, a technologist and unrepentant geek living and working in [Sydney](/places/inner-west-sydney) with his wife[^1] and son[^2]. He also rarely speaks about himself in the third-person..._

[^1]: "common law" wife; for some reason, we've never gotten around to actually "tieing the knot", although it's arguably the best excuse for bringing a bunch of old friends from around the world together for a party.

[^2]: Age eight and with greater mastery of a PS4 controller than I've ever seen, let alone the Wii U, iPad, phone ... how many platforms can you get Minecraft on these days? God, I love that kid.

[^3]: Oh, you don't reincarnate every prime multiple of years? 2,3,5,7,11,13,17,19,23,29,31,37,41

Somehow you've stumbled onto my (oft-ignored) website, and then have clicked on the "about" link to find out more about me – so thanks!! You probably won't find much of interest here I'm afraid, but you're welcome to have a poke around anyway. Let's see, what can I tell you about myself?

> _A highly-motivated and intelligent computer scientist with a keen interest in all aspects of information technology and more than a decade of commercial experience in developing software, providing 24×7 support, establishing standards and building infrastructure. I like “big data” systems, resilient cloud infrastructure (AWS, GCP), machine learning and AI, and “speak” a couple of programming languages. I’m a Linux/UNIX オタク (although have now spent years in MacOS), an open-source advocate (and very occasional contributor) and a generally geeky kind of guy._

(Yeah, I should probably update this, especially since I had a job interview once in which the lead engineer gave me a `vi` session and a problem statement and said "go for it".  No IDE? What are we, savages?)

I've a long list of hobbies, including science-fiction, motorcycles, camping, software engineering, devops, craft beer & brewing, robotics and boardgames. I've travelled a few places, although there are plenty more things I'd like to try.

***

## Spoilers

{{< figure src="/images/timeline.png" lightbox="true" caption="Figure 1: One possible timeline">}}

***

## About this website

I've had a 'blog for a while (check the archives), and have over the years migrated it from one platform to another: Blogspot to Drupal to Wordpress and beyond. These days, it's a static site built by Hugo, using a hacked up version of the hello-friend-ng theme that I've never gotten around to forking. If you haven't checked out Hugo, or static site generators in general (I hear Jekyll is good too) then you definitely should: setting this one up was pretty easy and is currently hosted for free on Firebase. Thanks, Googs!

In fact, there's really only one neat feature that I'm exploring, which is automagic crosslinks between posts and "terms", another content type I created to try to get some notes in order. In short, any mention of the title of a piece of content will become a link to that content. To do this, add the content to the "crosslink" index via frontmatter:
```
---
title: "About"
author: glennji
date: 2019-03-05T15:54:31+11:00
draft: false
crosslink: "true"
categories:
  - whoami
---
```

... and use some derivation of the following in the layout for the content:

```
{{ if .Params.crosslink }}
  {{ $related := .Site.Pages.RelatedIndices . "crosslink" }}
  {{ .Scratch.Set "content" .Content }}
  {{ with $related }}
    {{ range . }}
      {{ if .Params.title }}
        {{ $title := .Params.title }}
        {{ $permalink := .Permalink }}

        {{ $content := replaceRE (printf "(%s)/" (lower $title)) "meeeeeeeeeeeep" ($.Page.Scratch.Get "content") }}
        {{ $.Page.Scratch.Set "content" $content }}

        {{ $content := replaceRE (printf "(.*)\\b(%s|%s|%s)\\b" (lower $title) $title (title $title)) (printf "$1[$2](%s)" $permalink | markdownify ) ($.Page.Scratch.Get "content") }}
        {{ $.Page.Scratch.Set "content" $content }}

        {{ $content := replaceRE "meeeeeeeeeeeep" (printf "%s/" (lower $title)) ($.Page.Scratch.Get "content") }}
        {{ $.Page.Scratch.Set "content" $content }}
      {{ end }}
    {{ end }}
  {{ end }}
  {{ .Scratch.Get "content" | safeHTML }}
{{ else }}
  {{ .Content }}
{{ end }}

```

## Geek Selfie
{{% figure src="/images/bg3.jpg" caption="Figure 2: Yep, that's what we call 'Movember'" %}}

