---
categories:
- rstats
- teaching
comments: true
date: 2019-08-06T10:57:00
tags:
- rstats
- econometrics
- data science
- causal inference
- DAGs
- blog
title: Econometrics, Data Science, and Causal Inference
---

This summer, I am overhauling my econometrics class in many ways, in part because I was pleased to recieve a teaching grant from my college to make more R resources for my econometrics class. [Last Fall](http://ryansafner.com/courses/ECON480) was the first time I had taught it using R, and I've learned a ton since then. Expect a flurry of posts in the coming weeks more on those topics. 

This post, however, explores some of the trends that I have been thinking about in teaching econometrics, and something monotonous that I have been struggling with that encapsulates the tension in these trends: what to name my course. I of course need to officially stick to the Procrustean Bed of the title in my college's course catalog: ECON 480 - Econometrics, but in more causal conversation, or perhaps as a course subtitle, I have been torn between **"data science"** and **"causal inference."** This class is an introduction to econometrics, and assumes students have taken basic statistics, so this "problem" is really just marketing on my part — it's just a run-of-the-mill introductory econometrics course, but I like to add in a few bells and whistles! 

After thinking on this more, it seems to me there that we might be able to delineate a few possible directions that our field is heading. I hasten to qualify that I am thinking about this much more as a *teacher,* of these topics, less as a *practitioner*, as my own research niche is applied economic theory, albeit with a steadily-growing fascination with these methods. Nor am I a historian of econometric thought. 

These two trends or approaches I'll call "data science" and "causal inference." For the purposes of wrestling with this post, I will examine each of these forward-looking trends separately. I don't want to rule out the possibility at all that these are entirely complementary, and I am making a big deal out of nothing. Nonetheless, I think it is an interesting distinction to examine. 

## "Data Science"

["Data science"](https://www.google.com/search?q=data+science) is the hip new catchall term for using statistical software to analyze data for a variety of purposes. It is commonly interpreted as [the intersection of statistics, computer science, and domain expertise (e.g. business, biology, etc)](https://www.google.com/search?q=data+science+venn+diagram). I personally like the definition offered by the following tweet:

{{< tweet 198093512149958656 >}}

The modal "data scientist" seems to be a young practitioner in industry or academia that use programming languages like R and Python to wrangle, visualize, and present data to solve empirical problems in their domain of expertise. On the academic/teaching side, self-styled "data scientists" seem to be trendy statisticians, computer scientists, or biologists (e.g. "bioinformatics"). [New masters degrees and certifications](https://www.google.com/search?q=data+science+certificate) in "Data Science" or "Data Analytics" seem to be popping up left and right at major universities.

A large part of me wants to ride the coattails of this cool new trend and call/subtitle my class something like "Introduction to Data Science." I decided against it for a few reasons that I think are instructive.

First, I would be encroaching the turf of my colleagues in Statistics and Computer Science departments that often have courses with explicit titles like this. These classes are often a rehash of classic introductory statistics classes (probability, the normal distribution, $t$-tests, the central limit theorem, etc) but where software and simulation tend to replace pure theory and statistical proofs in a much more student-friendly way. It is a lot more intuitive and less tedious to understand a $p$-value via programming commands or simulating a null distribution of 10,000 bootstrapped samples than to learn the theoretical Student's $t$-distributions and look up critical values from a table (as I once had to!).

Second, although some econometrics textbooks do teach introductory econometrics this way^[[*Stock and Watson*](https://www.pearson.com/us/higher-education/product/Stock-Introduction-to-Econometrics-3rd-Edition/9780138009007.html), for example, which I taught with for 2 years], a good econometrics class, in my opinion, is much more than just an introductory statistics class (first review probability, distributions, statistical estimators, hypothesis testing, linear regression) that finally bleeds into the models that empirical econometricians *actually* — oh no, the semester's already over! 

Econometrics has a particularly opinionated view of statistical models, and often uses them to a very different end than most "data science"-type uses. This is precisely what distinguishes uses of statistics in *economics* from its use in other domain areas^[Epidemiology is perhaps closest to economics in this regard.], the focus on the second major trend I discuss below, **causal inference.** 

Perhaps the paradigmatic application of "data science" beyond mere descriptive statistics and causal inference is "machine learning" and associated terms and techniques (e.g. "big data," "neural networks," "artificial intelligence," etc). These issues often deal with massive "wide" datasets, frequently with more variables than observations. Take a website such as Facebook, which has a ton of information about a user -- locations they visit the website from, who their friends are, what pages they have interacted with, etc. [Machine learning techniques](https://www.youtube.com/watch?v=R9OHn5ZF4Uo) such as neural networks, as I understand them, try to identify what characteristics predict a certain outcome. Facial recognition software seems to me to operate similarly: take a large number of pre-identified images (e.g. a human at some point determined the image indeed contained a face) for *training* an algorithm, pass those images through $n$-number of layers to detect common characteristics of "faces" vs. "not-faces", and then additional subtleties that differentiate one face from another, and after $n$-layers and $m$ features are determined (where both $n$ and $m$ are massive numbers!), then the algorithm can take a *new* un-classified image and determine *if* it includes a face, or, if it is a very good algorithm, *whose* face it is. But, as [this excellent video ](https://www.youtube.com/watch?v=R9OHn5ZF4Uo) reiterates, *nobody understands* how the neural network that successfully identifies faces *works*. 

The key feature here is that it these technqiues are atheoretical, they are entirely empirical and judged on their rate of success. The algorithm itself has no underlying theory behind what "causes" a face or determines a face, only a purely *empirical* process of identifying patterns statistically by brute force. Nobody actually knows, or perhaps even could know, *why* or *how* an algorithm works.

## "Causal Inference"

Causal inference, by contrast, whatever some hardcore practitioners might say about merely "letting the data speak for itself", *necessitates* an underlying theory to explain a relationship or a process. 

Without going into a full post on methodology, economics is a theory-driven discipline in a way like few others. This is why I expect that "big data" and "machine learning" techniques will offer only marginal insights in economic research relative to the tried-and-true methods (and I am [in good company](https://mru.org/courses/mastering-econometrics/are-machine-learning-and-big-data-changing-econometrics)). It is certainly true that some theories may be verified or disproven by data, or entirely new theories emerge via analyzing data that may never have otherwise been discovered. However, the main tool of empirical work is to identify and measure causal effects *already* theorized or hypothesized from solid economic theory.^[I don't want to take the hardcore position here that there is *no* validity to empirical work in economics. Sometimes multiple economic principles might be operating in combination or against each other through multiple channels in the real world - empirical work helps us to tease them out in a useful way.] Data can never "speak for itself," because we wouldn't know *what data* is worth collecting in the first place. I like to think about it with the ([attributed](https://en.wikiquote.org/wiki/Immanuel_Kant#section_24)) Immanuel Kant quote: 

> Experience without theory is blind, while theory without experience is mere intellectual play.

Economists and econometricians have always emphasized the role of causal inference in econometrics. I recall learning - to my surprise - as an undergraduate and as a graduate in my courses that with clever identification strategies (instrumental variables, regression discontinuity, differences-in-differences, fixed effects, etc), we *can* do a lot more than just say things are "correlated," and thus gore the sacred refrain of statistics professors everywhere (*"correlation does not imply causation"*). I never experienced what learning econometrics was like in the 1980s or 1990s, but this view has only grown stronger with the "credibility revolution" described by Angrist and Pischke (2010, 4):

> Empirical microeconomics has experienced a credibility revolution, with a consequent increase in policy relevance and scientific impact…[A]s we see it, the primary engine driving improvement has been a focus on  the quality of empirical research designs.

Having much more omnipresent and higher-quality micro-level data has also helped. 

However, I have noticed in recent years in a particular strand of econometrics teaching has gotten more pathological about causal inference (I don't mean to use that term pejoratively!). Not all of the work in this trend is by economists, but it seems to finally be seeping into econometrics pedagogy. 

I think the quintessential tools for this new wave of teaching causal inference are the [Directed Acyclic Graphs (DAGs)](https://en.wikipedia.org/wiki/Directed_acyclic_graph) popularized by famed computer scientist Judea Pearl, or the ["do-calculus"](https://www.google.com/search?client=q=do+calculus) for more advanced treatments. I see this now showing up in excellent teaching materials like Scott Cunningham's [*Causal Inference: the Mixtape*](https://scunning.com/cunningham_mixtape.pdf), [this great but technical blog post](http://www.michaelnielsen.org/ddi/if-correlation-doesnt-imply-causation-then-what-does/) by Michael Nielson, a lecture in Andrew Heiss' [class](https://econw19.classes.andrewheiss.com/class/27-class/), and Nick Huntington-Klein's excellent [lecture slides](http://www.nickchk.com/econ305.html) for his course in Economics, Causality, and Analytics (now there's a good title!). More and more people also seem to be linking to the great [daggity.net](http://dagitty.net) tool for drawing and interpreting DAGs.

After reading Pearl and Mackenzie (2018)'s *The Book of Why*, I briefly felt much more zealous about claiming that we can indeed argue "*X does cause Y, dammit!"*. The review of DAGs by [Imbens (2019)](https://arxiv.org/abs/1907.07271) brought me back down to earth. DAGs are a great pedagogical tool^[There are limitations to them, such as the inability to add cutoff variables for regression discontinuity design models, or interaction terms. Huntington-Klein seems to fudge this by creating nodes like $X<c$, or $X * Z$, for the respective problems mentioned)] but aren't the silver bullet for clarifying empirical work. Imbens makes a compelling case that DAGs have very little practicality beyond "toy models" such as those in Pearl and Mackenzie (2018) and standard econometric research designs since the "credibility revolution" (Angrist and Pischke, 2010) work far better in practice. For the moment, that's fine for me — I may make a post later about the benefits^[Namely, 1. making model assumptions explicit, 2. using proper correlations in the data to falsify a proposed causal model, and 3. showing that there are not all variables need to be controlled for, indeed controlling for certain types of variables actually *introduces* bias!] — I think my students will find them very useful. I am more convinced with Pearl's argument that causal models are a necessary ingredient to the progress of artificial intelligence.

## A Compromise

In any case, thinking about these two strands makes the development of the field seem richer and more dynamic. I again add that I am not trying to artificially carve out an antagonism between these two approaches, in fact I hope to marry them into the latest iteration of my econometrics course. One of the appeals I try to make to my students (some of whom are Economics majors, some Business majors, and a mixture of others such as Biology or Environmental Science) is that the tools we learn in this class will not only make you better consumers of science and studies, but also may be invaluable in the emerging job market. "Data science" again is one of the sexy trends of the 2010s and beyond. Learning how to import, wrangle, analyze, and present data with statistical software and programming languages like R already makes students budding "data scientists." Futhermore, *causal inference* with empirical models and research designs is the *economist's* comparative advantage that will set *economics* majors apart from your average "data science" or "data analytics" certificate-holder. 

# References

Angrist, Joshua D, and Jorn-Steffen Pischke, 2010, "The Credibility Revolution in Empirical Economics: How Better Research Design is Taking the Con out of Econometrics," *Journal of Economic Perspectives* *24*(2), 3–30. 

Imbens, Guido W, 2019, "Potential Outcome and Directed Acyclic Graph Approaches to Causality: Relevance for Empirical Practice in Economics," Manuscript

Pearl, Judea and Dana Mackenzie, 2018, *The Book of Why*, Allen Lane

