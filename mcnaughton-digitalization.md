---
title: "'Digitalization,' from Harry Nyquist to the 'edge' of the internet"
description: ""
date: 2021-01-27T15:23:38.881Z
author:
  - Neil McNaughton
name: mcnaughton-digitalization
oxa: oxa:5w7N97WoctdHdShYPn5p/pPjThnlYd1IfcEy4tR3I
---

# 'Digitalization,' from Harry Nyquist to the 'edge' of the internet

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/cfGXXPXnMuRh3gj8EbtZ.1","pinned":false}

You might be forgiven for thinking that today, just about every measurement is ‘digital.’ A watch shows time in digits. Music streams across the internet in digital MP3 files and so on. Although if you are a music buff, you will know a bit about err.. bit rates … and the difference between a scratchy sounding MP3 file and a CD. At the root of time and sound, indeed just about any measurement, there is the continuous ‘analog’ variation of a parameter that needs to be sampled and turned into a string of numbers. This is not quite as easy as it appears. The manner in which analog is turned into digital determines how the real world is perceived by those using the digital version. It is a good idea to understand how the conversion has been achieved before blindly treating the ‘digital twin’ as the unadulterated truth.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/DdZflNw2T0rueDZAoIxQ.1","pinned":false}

It is usual to speak of the digital to analog conversion process as ‘sampling.’ While this is not wrong, it only tells half the story. The process of digitizing is a process of modeling. How it is done affects how well the digital version will represent reality and how useful it will be for a particular purpose.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/2AMbwqufcdmUrkOWLH0K.1","pinned":false}

Analog-to-digital conversion was invented by electronic engineers and assumes that the parameter of interest, the signal, varies in such a way that the sampling campaign can be designed to capture all significant changes in the signal. There is a big ‘gotcha’ in this approach as follows.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/IVyEnVgvIYOh93SVsNgR.1","pinned":false}

Suppose that the ‘signal’ to be digitized is the length of the day as judged from observations of the position of the sun. Imagine that our observer was a bit lazy and just checked the position once a day, at 12 noon. He or she might conclude that the sun never changed its position, its ‘frequency’ would be zero and its period infinite. Suppose now that the observer took a reading just a little bit more frequently, say, for the sake of argument, once every 23 hours 56 minutes. He or she would then conclude that the sun was moving slowly backwards, returning to the same position after a year! To capture the sun’s true frequency, you need to take at least two observations per day, spaced 12 hours apart. Anything below two samples per cycle gives the wrong frequency, a phenomenon known as ‘folding’ or ‘aliasing.’ For more on this you need to visit Harry Nyquist (https://en.wikipedia.org/wiki/Harry_Nyquist) who first described the problem.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RvVvWQnhgxcqoYhuglx2.1","pinned":false}

To avoid having embarrassing ‘folded’ frequencies polluting the digitized data, seismologists and engineers apply an ‘anti alias’ analog filter before sampling to remove all frequencies that would otherwise ‘fold.’ National Instruments has a good page explaining this (http://digital.ni.com/public.nsf/allkb/68F14E8E26B3D101862569350069E0B9). Incidentally, a search on NI.com for ‘Nyquist’ returns some 2,000 references! For a geophysicist, an engineer sampling the electrical output from a device on the ‘internet of things,’ frequencies higher than the fold either do not exist or are not important. High frequencies are often thought of as ‘noise.’

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/HN5QsdbCIu4ew8DwI4RA.1","pinned":false}

The Nyquist/folding phenomenon is not limited to the time domain. Folks who make maps from discrete point measures of topography, gravity measurement or radar altimetry should filter out the higher spatial frequencies although I’m not sure that this is always done. It’s perhaps more usual to ‘filter’ by contouring the data into a smooth representation afterwards. While this is probably not best practice, it does implicitly acknowledge that high spatial frequencies don’t exist. If, from a 100km x 100km per data point survey across the alpine chain, you contrive to contour in Mont Blanc, the Matterhorn and the Monte Rosa then you are either making things up or interjecting what is called ‘prior information.’ We will come back to ‘prior’ and ‘making things up’ in part II of this tutorial/editorial series\*.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/SOs7yXI8UBM8WxtxyLo6.1","pinned":false}

Now what happens if frequencies above the fold are important. Consider the popular meme of equipment monitoring. Sensors on rotating equipment likely will return the same value of say oil temperature, RPM or whatever for very long time periods. Such slow variations can be captured and transmitted accurately with a low bandwidth network. But what if the analytics tells us that a malfunction is preceded by a very high frequency event, the noise made by an oil pump blowing a gasket, or the clicking of a worn bearing as happened to me on my bike recently. To record all the data at a frequency high enough to detect such rare events would require much higher data rates than needed for normal operation. If you need millisecond sampling for the extraordinary and the ordinary is happy with one sample per day you have just multiplied your bandwidth, processing and storage requirements by a zillion!

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/82kY9iEoNHvetyWRlght.1","pinned":false}

What to do in such circumstances is part of ‘edge computing,’ the subject of this month’s lead. Transient events can be recorded locally at a suitably high frequency in a local loop. If a value goes above some threshold, the loop containing the data can be sent over the wire. This implies of course more local ‘smarts’ at the edge and likely across the network too. Much more sophisticated scenarios can be envisaged, with machine learnings (about bearing failure noise patterns and such) deployed ‘at the edge’ so that all that comes over the wire is a succinct ‘crank bearing fault’ message (we are assuming the connected bike here).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/ty26szWd1dc27oDNJ8ae.1","pinned":false}

Note however that the more smarts in your edge processing, the less access you have to real ‘internet of things’ data. Combine this with kit (sensors and smarts) from multiple vendors each with their own ‘land grab’ smarts and you see why the Linux Foundation’s idea is a necessary but probably not sufficient condition for interoperability. The problem is not just about aligning data protocols, it is also, and more profoundly, about aligning models of reality. A harder, if not impossible task!

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/cp3vF7Mw6uQhOeocVytB.1","pinned":false}

1007 words

