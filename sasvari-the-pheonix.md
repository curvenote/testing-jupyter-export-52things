---
title: The Pheonix
description: ""
date: 2021-01-27T15:28:19.479Z
author:
  - Ágoston Sasvári
name: sasvari-the-pheonix
oxa: oxa:5w7N97WoctdHdShYPn5p/SSxKfXwCzMOpQvHtFVba
---

# The Pheonix

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/HIQuqzOB7YLrZaNBg3qG.2","pinned":false}

*'phoenix: a long-lived bird that cyclically regenerates or is otherwise born again'*, says Wikipedia. In the old mythologies, re-birth of a phoenix became a symbol of eternal life and cyclical re-generation. I'm sure each of us has at least one secret phoenix at home in some form. So let me show mine, of which the recent 'digincarnation' lives in GitHub now.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/ABG98BIpJEBh1bwrav3j.2","pinned":false}

After finishing my first field work in 2006 in the Hawasina Window, Oman, I was facing thousands and thousands of field records: dip and strike measurements, slickensides with movement direction, fold axes, foliation and bedding dips... nice, but how to evaluate them? Using the available out-of-the-box tools I can do them record by record, but it would take forever...

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/CkAIdTv94p7LHtFS270P.2","pinned":false}

1. So I had to recall my coding skills, and create a **batch file** which directly loaded the readings into a **PostScript file**: one reading goes in, one stereonet comes out: that was the birth of my little secret phoenix. The processing happened within the PostScript, and the stereonets were generated one by one for each readings - completely user unfriendly but at least automated.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/LPqs4grI7mz1mic9yH4a.2","pinned":false}

2. The next incarnation was to modify the original PostScript to process **multiple data records** (like a bunch of bed dips measured in an outcrop), and it did the job very well.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/kHPUpVOg4W4ABnXeIzHr.2","pinned":false}

3. The original idea was to create a real and nice open source code for the future use, but which way? **Turbo Pascal**, here we go! I started to recall my almost-forgotten memories from the secondary school years, when we had DOS 5.1 running on 386 machines, and we coded in probably-not-Turbo Pascal. That was something that I gave up really quickly, from a coding point of view that was looking to be a never ending story, therefore this incarnation was very short.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/dinXcuZlW3y2bcfgarCy.2","pinned":false}

4. So what instead of Turbo Pascal? A really good old buddy of mine, a friend since forever, ingenieur and mathematician, recommended me to give a try and go ahead with **C++**, so that's what I did. In the next 10 years, I cannot tell how many working hours were spent on developing and debugging of a structural geology tool for field geologists. I coded paleostress inversion methods, clustering, post script export, matrix operations from scratch... a long list, and at the end of the day, I ended up having 51 cpp files totalling in **24000 rows** with massive 100-rows if-else complexes impossible to understand and debug. So time has come for the next incarnation.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/1u2e0DoShqxSFNzsz6ct.1","pinned":false}

5. First time I heard about Python, I started to resist. Tools in Linux...? No thanks, I'm on Windows! New language, new syntax? Not at all, I have spent a decade fighting with C++! But at the end of the day, I had to replace my good old 32-bit machine, and a new era has begun.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/a0YAhUy1FFGK8bBc3PBr.1","pinned":false}

Now I'm on Linux, and I'm free. I'm coding in Python 3.6 and creating such tools on a daily basis what I was even unable to imagine before. Coding matrix operations or clustering on my own...? Nevermore, just import them, and let's go to the next row! So time has come to re-write my 24000-liner into... 2400 rows perhaps? Or even less...? No 100-rows if-else beasts anymore, just lists, dictionaries, pipelines, and so on, and so on...

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/4deDwkEOpGiOJ8hScjdW.2","pinned":false}

Like everything, this sequence of re-incarnations changed my view: now I'm **searching** for the available tools instead of **re-inventing** them. Coding now is like playing with Lego bricks, *find the right one, go to the next step*. If everything goes well, I'm facing the last and final incarnation: phoenixes must go back to myth...

