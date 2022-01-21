---
title: Tailor your teaching with Jupyter Notebooks
description: ""
date: 2021-01-27T15:25:01.079Z
author:
  - "@japhiolite"
name: niederau-tailor-your-teaching-with-jupyter
oxa: oxa:5w7N97WoctdHdShYPn5p/LtuLbpJJzlcviDuufXQF
---

# Tailor your teaching with Jupyter Notebooks

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/OCgqnZhdcNYVXB8B3j5s.2","pinned":false}

I'm a self-taught coder, but a geologist by education. So there were people who taught me how to analyse rocks, how to use GIS, how to interpret seismics (or a thin section, or an XRD difractogram). But during my studies, everything with programming, all *quantitative* lectures were done in Excel. It wasn't until I studied abroad in France, that I learned about [Scilab](http://www.scilab.org/)(<https://www.scilab.org/>) and programming. And that really got me into coding. Since then, I moved from Scilab to Matlab (as my university had free licenses for students), to Python.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/FLfpwE9ud04fmYB7uUIy.1","pinned":false}

I started teaching courses in geothermics, and realized that most of the students in my exercise courses had little to no experience with programming, even though they had mandatory introduction courses about programming, now taught in Matlab instead of Excel. Still, that course was given in a frontal lecture style, where students are passive consumers, and follow the lecturer's code displayed on the projector, often step-by-step. So similar to a math lecture, where students try to not fall behind copying the professor's hand-written lemmas and derivations.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/jFsmDtV5uY9jPDhLmIPu.2","pinned":false}

That's the traditional way, the way they're used to. But it has been shown, that it is also one of the least efficient ways of teaching students to code {cite:p}`jacobs_experiences_2016`. So for improving a student's skills in programming efficiently, they have to actively solve problems in a self-determined way.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/YyWpaBBlefGzkHjRAtHG.2","pinned":false}

Achieving this in my courses turned out to be way more difficult than previously thought. When confronted with a problem and the IDE's *white wall editor*, many students were lost. One key conclusion for me is, that the initial obstacle for students to start coding and learn programming is really high. Then I got the chance to work together with [Professor Wellmann](https://www.stifterverband.org/digital-lehrfellows/2017/wellmann)(https://www.stifterverband.org/digital-lehrfellows/2017/wellmann, retrieved: 2020-03-23) from RWTH-Aachen University on projects supported by the [Exploratory Teaching Space Program](https://goo.gl/C5yry9) and the [Stifterverband](https://www.stifterverband.org/digital-lehrfellows/2017/wellmann) (in German). In these projects, we created concepts of teaching code interactively using Jupyter Notebooks, and to generally lower *teething troubles* when it comes to coding.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/r5KKqTDl1GuJvXfDFv2t.2","pinned":false}

Jupyter notebooks combine code, formatable text, and images/plots in one single document format, making them the ideal tool for teaching. However, they work smoother with Python than with Matlab. But considering Python's ever growing popularity, teaching students to code in Python instead in Matlab, might even be better. Especially, because basic coding skills become more and more prerequisite, Python is becoming more and more popular in the geosciences {cite:p}`lin_why_2012`, and finally, because it is - in contrast to Matlab - free.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/N1eaS0LCHYFc1iNDawFk.1","pinned":false}

In our projects, we tested combining task-definition together with predefined solution cells in a Jupyter Notebook instead handing out a single PDF file with the task-definition. The passively spent presence time during the exercise evolved to active working sessions. By using some of the many great notebook-extensions, such as [exercise, and exercise2](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/exercise/readme.html), solutions to exercises could be shipped with the notebook.\
This is particularly useful for creating a notebook with increasing level of difficulty. Imagine the concept/topic/process to be taught is broken down in three stages. First, it is presented in a simple working example, where students can follow **at their own speed**. Based on this, they're presented with a further example, where they have to code the answer, but a solution is provided, yet hidden until shown. The third stage, would then be a bit more complex example building on the previous learned content. Due to the linear structure of notebooks, such a concept can easily be implemented.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/mPa4boUSZSrVFmfi2Xtf.2","pinned":false}

The feedback by the students to using notebooks was great, so we increased their use, also for graded assignments. Due to the flourishing community of Jupyter-developers, there exists a tool called [nbgrader](https://github.com/jupyter/nbgrader)(https://github.com/jupyter/nbgrader/, retrieved: 2020-03-23.) which perfectly fitted our needs. Notebooks could now be autograded (with the occasional manual grading step)! To ensure that students are working under the same conditions for these graded assignments, we set up a server with [jupyterhub](https://jupyter.org/hub). Students then just had to log in and could start their assignments, which could be distributed and collected remotely by the advisor.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Tbbv3evBSMj76g2EjYEh.1","pinned":false}

Next to assignment notebooks equiped with autograding, we created a number of notebooks accompanying the content of the lecture as a opportunity of self-assessment for the students. In my opinion, a lot of geoscience students are *haptic* people (just think of rock-identification courses) appreciating visual input. Geological processes are often taught using analogue models, e.g. folding with modeling clay. Crystal systems are taught by using geometrical bodies made out of wood.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/91oMsNFj0nysHxh16ScR.2","pinned":false}

Jupyter Notebooks enable haptic ways of teaching programming by using widgets. For example, we created [notebooks in structural geology](https://github.com/Japhiolite/stress-and-strain)(https://github.com/Japhiolite/stress-and-strain, retrieved: 2020-03-23.) with sliders and boxes, so students can e.g. directly experience the response of a strain ellipse, when they changed the deformation tensor. Since this all started, I transferred some exercises from my [geothermics course to notebooks](https://github.com/Japhiolite/geothermics)(https://github.com/Japhiolite/geothermics, retrieved: 2020-03-23.). And I am quite late with this move. There is a constantly growing amount of teaching resources, such as [python for geosciences](https://github.com/koldunovn/python_for_geosciences)(Koldunov, N. Python for geosciences, https://github.com/koldunovn/python_for_geosciences, retrieved: 2020-03-23.), [Geo Python](https://geo-python.github.io/site/)(Department of Geosciences and Geography, University of Helsinki: Geo Pyhon, https://geo-python.github.io/site/, retrieved: 2020-03-23.), and above all the great course [12 steps to Navier-Stokes by Lorena Barba](https://lorenabarba.com/blog/cfd-python-12-steps-to-navier-stokes/) {cite:p}`barba_cfd_2018`. Lorena Barba and some co-authors even wrote a book about [Teaching and Learning with Jupyter](https://jupyter4edu.github.io/jupyter-edu-book/)(Barba, Lorena A., Barker, Lecia J., Blank, Douglas S., Downey, Allen B., George, Timothy, Heagy, Lindsey J., Mandli, Kyle T., Moore, Jason K., Lippert, David, Niemeyer, Kyle E., Watkins, Ryan R., West, Richard H., Wickes, Elizabeth, Willing, Carol, and Zingale, Michael, 2019. Teaching and Learning with Jupyter, https://jupyter4edu.github.io/jupyter-edu-book/, retrieved: 2020-03-23.), which is an excellent read and resource, if you want to *jupyter-up your teaching*.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/pNJyiZCJKxQb1cBvr5jN.3","pinned":false}

One key take-away message for me was: Students had fun experimenting with these notebooks, from altering functions to trying to break them. And connecting the lecture content with a (strong) emotion, increases the learning effect demonstrably {cite:p}`christianson_handbook_1992`.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/m8C3XBBkx7MYKgZ1SebL.2","pinned":false}

During the last couple of years, we've come a long way in terms of teaching geoscience-students to code. Programming tools changed from Excel, over a Matlab IDE to Notebooks. Notebooks are used for different purposes, from lecture-accompanying notebooks, to (auto-)graded assignment notebooks. The influx of Python in our faculty is remarkable. Oh, and the programming and statistics course is now taught in Python, using Jupyter Notebooks.

### References

```{bibliography}
:filter: docname in docnames
```

