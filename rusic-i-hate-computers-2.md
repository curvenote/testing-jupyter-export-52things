---
title: I hate computers II
description: ""
date: 2021-01-27T15:26:36.510Z
author:
  - Alberto Rusic
name: rusic-i-hate-computers-2
oxa: oxa:5w7N97WoctdHdShYPn5p/2p3ZZwUWNRk1ZA0Zhs2o
---

# I hate computers II

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/qJMdzBl2O3qFIYbnzHwv.1","pinned":false}

Some time after the transition to a mouse and keyboard from punched cards change everything for me, I started to ruminate on the idea of developing a rock physics system.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/v6pDjrj9bvdVlCrPsKX1.1","pinned":false}

I still had to work on projects so I didn’t have much time to devote to the programming side. My intention was to develop short modules and link them later into some sort of framework. In the beginning, I thought rock physics would be relatively easy to implement because a lot of the knowledge is expressed in algebraic formulas, but the project turned out to be more complex than I initially expected.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RMU8bdU12SLLTUjzullJ.1","pinned":false}

To me, *rock physics* includes any physical phenomenon, i.e., electromagnetic properties, nuclear characteristics, the rock's mechanical nature, etc. But in the context of the system I wanted to develop, I reduced the scope to the subset of knowledge that relates seismic amplitudes to geological aspects of the rock such as the mineral composition, amount of porosity, fluid content, and other variables like temperature and pressure. This rather simplified idea felt more approachable.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Dl7h3VZnDEG4yS9tqftt.1","pinned":false}

Now, what is involved in the development of such a system? It’s not just the knowledge we have about a subject, but how this knowledge is interlinked — how the facts interact with each other. We also have to deal with the certainty that our knowledge will evolve, as ideas about a subject change or as more knowledge is uncovered. The system should be able to help us handle that.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/eFt12hf3I22N5NSPSOCt.1","pinned":false}

One example of this is the seismic amplitude. In the beginning, geophysicists just followed reflection events to define the structure of the reservoir: a simple system that helps us understand subsurface structure. Later, geophysicists realized the amplitude of the seismic events may change and that those changes could be related to lithology and fluid properties in the subsurface. We would like a system that incorporates this knowledge and helps us not only to delineate structure but also to reveal whether the structure contains a reservoir of interest or not. As we want to add more knowledge to an existing system, more resources may be needed to develop a really helpful computer program.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/FTKnhrgcO136taUXO02y.1","pinned":false}

Furthermore, we don't only want to encode the knowledge we have, we also need to deal with all the results produced from that knowledge. For example, the AVO response of an interface can be computed with a simple program that implements the Zoeppritz equations, but what about changing the values of the elastic properties of the rocks on either side of the interface? What if we have to do thousands of trials and wish to store the results and compare them? What if we want to query and visualize those results? What if we want these results to be used by another program stored somewhere in the computer waiting for some input? This is not an easy answer and I think at this point the current computer architecture starts to break down and perhaps work against us instead of helping us.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/FxRgeQkYz1sj10LrfXV3.1","pinned":false}

As far as the personal system I'm developing is concerned, at the moment it is a bunch of modules, each one able to solve or perform a single task. But the modules are not related to each other, they don’t talk to each other, and data management has to be done manually. As more modules are developed, it becomes more difficult to integrate all of it into a whole intelligent system.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/rmccFXmJd64RMpEFf0u8.1","pinned":false}

This may be a sad story so far but this story hasn’t ended yet — we have so much room to improve! Of course, we will improve and I’m pretty sure someday we’ll build something that will outsmart us. We have already done it, in narrowly defined ways, with Deep Blue and AlphaGo — and we’ll do it again.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/uyFsAoIICeSVBTqF0ZhD.1","pinned":false}

I strongly believe better computers, and better interactions with computers, are possible. And they are necessary if we would like to solve the complex problems we are facing today in shorter time. We need another leap forward, equivalent to the one we had from punching cards to mouse and keyboards. It occurs to me that a good measure of the usefulness of a computer system could be the number of mouse clicks and keyboard strokes you need to finish a task. Someday I am going to count them, maybe my next project, but now I need to go back to my work, must finish it, click, click, click, tack, tack, tack,…

