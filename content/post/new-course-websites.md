---
categories:
- teaching
- workflow
comments: true
date: 2019-08-22T17:28:00
tags:
- markdown
- websites
- workflow
- blog
title: New Course Websites
---

This Fall semester, I have made dedicated websites for all of my courses at Hood College that host nearly all the course content. You can see them all [here](https://ryansafner.com/#teaching). My interest was sparked when I saw [Andrew Heiss](https://www.andrewheiss.com/teaching/)' amazing course websites.

Until this point, all of my course content has lived on Blackboard for my students, though I have also tried to post syllabi and lecture slides (if not additional resources) on my [personal website](http://ryansafner.com/teaching) over the past few years. This process has been manageable, but has had way too much pointing-and-clicking, unnecessary duplication, and is not very open-source.

For each course website, I am using the (surprisingly painless) combination of [R markdown](https://rmarkdown.rstudio.com/), [GitHub](http://github,com), [Blogdown](https://bookdown.org/yihui/blogdown/), [Hugo](https://gohugo.io/), and [Netlify](http://netlify.com) such that my entire workflow is reduced to:

1. Edit a plain text file with R Markdown (I like doing this in R Studio)
2. Commit and push to GitHub (again, R Studio integrates this seamlessly)
3. The new website is automatically updated by pushing my GitHub repository via Netlify

Step three doesn't even really count because once set up, I don't have to do anything! I paid the fixed costs of extensively figuring out how everything works and experimenting over this past summer. If you are interested, I have attempted to explain the process of duplicating everything in this [README file](https://github.com/ryansafner/classwebtest) in my testing repository on GitHub (automatically rendered on the main page). It assumes some working knowledge of R Markdown, but not much else. One day I may make a better step-by-step guide if there is any interest, but lots of great guides on each feature already exist (and are linked to in the README).

Each course has a page for the syllabus, assignments, reference (guides, links, and other resources to come), and a schedule page that is organized into relevant slides, assignments, or other resources for each class meeting. I have found the schedule page in particular to be a great framework for making all aspects of the course cohere in a single place.

Why have I decided to do this?

For good or ill, I am a slave to aesthetics^[I view lecture slides as a fine artform and have refused to use Microsoft Office products for over 8 years], and think that form matters just as much as function. This is not so much a rational viewpoint of mine as a vice: Producing and perfecting lectures is a *consumption good* for me, not a means-to-an-end investment. I have delighted at learning [Xaringan](http://github.com/yihui/xaringan) this summer for all of my slides (guides and blog posts coming soon), and as they live in `html`, hosting them on a single website made the most sense. I also made sure each course has its own custom hex sticker and workflow map (again, copying some killer design elements from Heiss). As a relevant side note, I have started to see the [limitations](https://www.authorea.com/users/5713/articles/19359-latex-is-dead-long-live-latex-typesetting-in-the-digital-age/_show_article) and [ugliness](https://www.urban.org/urban-wire/your-data-deserve-better-pdf) of [PDFs](https://yihui.name/en/2013/10/markdown-or-latex/) in the age of the web, and have ditched `LaTeX` (admittedly, it was a long and loving relationship) for the elegance and beauty of  `markdown` and `html` wherever possible (posts on that to come). 

The main side effect is that all of my materials will be available to anyone online for free. I have always been committed to free and open source teaching, and have benefitted an extraordinary amount from learning from materials that other academics or practitioners - who I may never meet - have posted online.^[One of my guilty pleasures is to devour anyone's lecture slides posted free online in areas that I teach or research and shamelessly steal what I like (I try to give credit if it is something major!). This confirms to me that I am a true academic.] While they will be without lecture videos (no plans for that, sorry), or original copies of some readings (copyright, my favorite), or answer keys for major assignments (I do recycle some questions), these websites are otherwise complete self-contained courses.

Another reason this made sense for me is that as I have gotten into a rhythm of teaching the same course multiple times, I have started to accumulate a lot of additional resources: guides, tutorials, handouts on more technical concepts, etc. These would kill a lot of trees to print out for students, and it would be nice to have a central repository for them - a website is the natural place. 

There are some limitations, as I can't do *everything* on them. My major limitation is grading. Blackboard's Grading Center is too convenient and centralized not to use (not to mention, secure, individualized, and FERPA-compliant). These new websites are primarily for broadcasting content to everyone, not using it as a personalized experience. Additionally, I will still use Blackboard for mass-emailing students. But my workflow of `1. write in plain text, 2. push to GitHub` available for everyone seems vastly superior to endless mouse clicks and writing of individual items to a page viewable by a single course section (and then duplicating everything for a second section).

It remains to be seen how my students will recieve these, but for now, I am excited.