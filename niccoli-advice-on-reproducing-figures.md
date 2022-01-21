---
title: Some advice on reproducing figures
description: ""
date: 2021-01-27T15:24:49.946Z
author:
  - "@mycarta"
name: niccoli-advice-on-reproducing-figures
oxa: oxa:5w7N97WoctdHdShYPn5p/dVYdJ705MavOhIUzxCtR
---

# Some advice on reproducing figures

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/bGvQGJKxPC5NOjsFdI5o.1","pinned":false}

This work stems from my experience reproducing Figure 1 (shown below) from Froner et al. (2013), using python, and from my desire to give some advice on the reproducibility process. In the following I suggest six steps to reproduce figures from publications.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Hg353yPHPvu66dDgwWB5.2","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-QEBDpH5RttEaZf20JTWR-v1.png
  :name: 1ea15f74
```

*Figure 1 - xxxxxxx*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/YXSlH2ZiCtb7IP3zqSlE.2","pinned":false}

**Step 1.** Get permission. Before embarking into a project, if you think you will need the original data, ask for permission to use it, to get the lay of the land. If that is not possible, and if you cannot make up similar data, this may not be the right project for you. Conversely, if you can work with made-up or modelled data, ask for permission to show the original figure alongside the reproduced one. I have requested permission to reuse figures many times, both from publishers and from professional societies, and have never received a negative response. For this chapter, I got a response from the European Association of Geoscientists and Engineers (EAGE) in less than 24 hours, granting permission to show the original figure both in the notebook and in the book. The Society of Exploration Geophysicists (SEG) follows the permission guidelines from the International Association of Scientific, Technical, and Medical Publishers (STM), granting republication rights for up to 3 figures (and other contents) without the need for [explicit permission](https://seg.org/Publications/Policies-and-Permissions/Permissions).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/vAi2HWcf4ANvEBSfaMRw.2","pinned":false}

**Step 2.** Figure out the math. Define, study and test the equations, functions, and other computations necessary to replicate the figure. Often times I start with an online graph tool like [Desmos](https://www.desmos.com/calculator) (at: https://www.desmos.com/calculator). I study each parameter both with large ranges of values, to understand their full impact, and subsequently in the specific ranges required to reproduce the figure, and try to come up with sensible default values when necessary. I later replicate the whole process in a Jupyter notebook with interactive widgets, for this case see: [*Interactive parameter exploration exponential function*](https://curvenote.com/@swung/52-things-geocomputing/interactive-parameter-exploration-exponential-func "https://curvenote.com/@swung/52-things-geocomputing/interactive-parameter-exploration-exponential-func")*.*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/YpP1oxGTzFJcFVNphSG5.1","pinned":false}

**Step 3.** Get the plots right. Figure out the specific plotting stuff to replicate the figure and the best library or libraries to get it done. In this work, I used the python library `matplotlib` to plot this figure. To get it right, apart from plotting I recognized I needed, among other things, to:

* Perform color space conversions
* Plot the Lightness magnitude of the colormap as a line
* Get the index, or colormap sample number, corresponding to 50% lightness

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/enYpK5bCk1lNolH8Z5jE.2","pinned":false}

The first two items I’d already figured out for my Geophysical tutorial [*How to evaluate and compare colormaps*](https://curvenote.com/@swung/52-things-geocomputing/how-to-evaluate-and-compare-colormaps-ipynb). For the last item, the function `numpy.searchsorted` provided the solution. The figure below shows the result.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/KCPt7xgZonSBrGNoiYLJ.2","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-HpBdU38akmMLElbiIbiW-v1.png
  :name: 56b32fb0
```

*Figure 2 -*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Y7nnaz3muNk9Q03NZZvb.2","pinned":false}

You can work through the entire process in the notebook [*How to make exponential grayscale*](https://curvenote.com/@swung/52-things-geocomputing/how-to-make-exponetial-grayscale-ipynb "https://curvenote.com/@swung/52-things-geocomputing/how-to-make-exponetial-grayscale-ipynb")*.*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/PhepdxNIpp05fqLU8qqg.2","pinned":false}

**Step 4.** Test the results. Test on the data that come with the paper, if you got permission, or other data, either made up or real. In this case I tested the colormap on a time slice from the Netherlands F3 open seismic dataset (available [here](https://terranubis.com/datainfo/Netherlands-Offshore-F3-Block-Complete)).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/LlaQp8VMe87166qtc52G.1","pinned":false}

**Step 5.** Do some extra work. Go further, improve the plots or add interactivity so that others can experiment too. For example: to improve on the original figure I made the Lightness plot color change in parallel with the colormap, rather than being just one color. Also, I made a separate interactive notebook, where the colorbar plot, Lightness profile plot, and seismic time slice plot are updated in real time so that users can experiment with the parameters and make their own colormap.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/kr9yp0bIEdOaDNF4TQgQ.1","pinned":false}

**Step 6.** Pay it forward. Share your results. More than that, do it with a permissive license, ideally a Creative Commons Attribution (CC-BY). In my case, I am clearly identifying the original figure as copyrighted material, reused with permission, and my figure and the notebooks as CC-BY, which allows others to distribute, remix, adapt, and build upon the original work, even commercially, as long as proper credit be is given for the original creation.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/fvNFW6CcJegPtYAnI91E.2","pinned":false}

In the end, have fun with it. For me, it was a wonderful experience, and empowering. To quote from [Matt Hall](https://curvenote.com@kwinkunks)’s [slides](https://agilescientific.com/blog/2011/3/25/geo-floss.html): “...now I can read an article in Geophysics, or The Leading Edge, and - assuming the authors reveal their methods openly - I can try them out immediately on my own data. I can improvise, tweak and improve. This is powerful: Now I can test ideas on the fly… I am free!”

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/gasoWoXso57pBXvLKR54.2","pinned":false}

**Reference** Froner, B., [Purves, S.](https://curvenote.com/@stevejpurves), Lowell, J., and Henderson, J. (2013). Perception of visual information: The role of colour in seismic interpretation. First Break, 31(4), 29-34. doi: 10.3997/1365-2397.2013010.

