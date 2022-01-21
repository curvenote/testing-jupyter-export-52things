---
title: A Geological Model is a Single Hypothesis - of Many Possible Ones
description: A discussion on the development and importance of stochastic
  methods in geomodelling.
date: 2021-01-27T15:27:40.084Z
author:
  - " Florian Wellmann"
name: wellmann-a-geological-model-is-one-of-many
oxa: oxa:5w7N97WoctdHdShYPn5p/GG3611uqGMgSPyyJsBJi
---

# A Geological Model is a Single Hypothesis - of Many Possible Ones

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/bAeK0FOrD1TgfOQDaKGl.2","pinned":false}

Geological models are widely used in both science and industry to represent main structural features in the subsurface \[see {cite:p}`Wellmann20183` for a recent overview\] . And in a comforting way, they give us the idea that we know very accurately how the world below our feet looks like - a dangerously misleading conception. The perceived reality of geological models is intriguing, and this aspect is getting even more pronounced in times of better 3-D visualisation of models on the computer, and probably increasingly so when we will soon all have our VR glasses on our heads - and the models look ever more realistic: we can turn them around, inspect them from all sides - just like models of a car, a house - reality!

Just with the important difference that these models are, in fact, often highly uncertain. They are based on limited information that is combined with pre-existing concepts and knowledge and implemented in a way that the respective geological modelling tool allows. Even though this aspect may be obvious to the person creating the model, it is difficult to understand for those who are not trained in a geoscientific subject and may not be aware of the underlying difficulties and uncertainties. And it gets even more intriguing for people who merely inspect the model, or use it to as a basis for potentially important economic decisions.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/EPgHUWkTWvocSYi3EGuV.2","pinned":false}

For us as modellers, it is also often tempting to assign a high value of trust to our models. After all, we often spend many weeks and even months with a model, so how can it be wrong? So we defend it against all other perceptions or the idea that they somehow could be uncertain and brush criticism aside! Actually, this problem has been recognised more than 100 years ago and discussed in a paper describing the concept of multiple working hypotheses {cite:p}`chamberlin_studies_1897` perpetuating the idea that we should never only propose one scientific hypothesis, but many different ones, so that we do not fall prey to the misconception that a single hypothesis is correct. And, here an interesting fact: the author of this article, T.C. Chamberlin, was actually a geologist!

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/aInDmuoQeHNgcQEoLqNS.2","pinned":false}

So, how does this insight transfer to our problem at hand, the modeling of geological structures? Most importantly, we can (and should) consider a geological model as what it is: a hypothesis about the geometric distribution of geological structures in the subsurface (or a sand/shale layering, facies distribution, etc. - whatever our specific objective is). If we take this step, then we can also clearly and openly communicate that this is merely one possible model of many - and by definition, it is wrong. But it does show, on the basis of all our information, data, knowledge, and technical possibilities, one interpretation about the subsurface that can well be illuminating and useful(At this point, the well-known aphorism attributed to George Box of course comes to mind that “All models are wrong, but some are useful”.) - but subject to uncertainties.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/djNlDbzGMx5TbUDhLLtP.1","pinned":false}

Once we take this step, then several aspects suddenly become clear: (1) a model is never completely finished, it is always “work in progress” and (2) it should be possible to revise the model when more data becomes available; Furthermore, (3) if a model is only a hypothesis, then we should be able to test it against other information, to see if it supports our hypothesis or if our hypothesis has to be revised, and (4) in the ideal of multiple working hypotheses, we should actually be able to generate more than one hypothesis and consider multiple working hypotheses at the same time. So: how can all of these aspects be realised? And: where is the button for all of this in my geological modelling software?

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/NCPebuOxzMV66DF8N2WP.2","pinned":false}

This is the stage where, at the moment, we are at a truly exciting time of development. There are now more and more geological modelling and simulation methods available in open-source projects \[e.g. {cite:p}`de_la_varga_gempy_2019`, {cite:t}`ailleres_loop_2019`\] - with a capability and complexity that will increasingly rival the methods that are now locked-away in commercial (and very expensive) software packages(This aspect should not be understood as “open-source methods replacing commercial packages” - as the latter ones contain so much more capabilities and well-established interfaces. Here, I only refer to the interpolation algorithms.). These open geocomputing tools give us the flexibility to express and test completely new approaches - as we can embed and combine them with all the other powerful open-source tools that are currently so actively developed. One example of our own work is the combination of a sophisticated geological interpolation algorithm with the probabilistic programming framework `pymc` {cite:p}`patil_pymc_2010` to obtain a framework for geological inference {cite:p}`wellmann_uncertainty_2018` which allows us now to efficiently test multiple geological hypotheses against additional information - and if we can encode the hypotheses in the form of prior probabilities and the additional information in the form of likelihood functions, then this quickly leads to an interpretation of structural geological modelling as a Bayesian inference problem, with completely new possibilities to express our geological understanding and thoughts in computer code.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Re9g4fBR7sXvzAFMHLQL.2","pinned":false}

With more and more powerful computational tools available, this way of thinking has the potential to completely change the way in which we work with geological models - and combined with the active developments in the field of geocomputing, it provides us with a new freedom to test novel ideas and to combine information in ways that far exceed what has been possible to date.

### References

```{bibliography}
:filter: docname in docnames
```

