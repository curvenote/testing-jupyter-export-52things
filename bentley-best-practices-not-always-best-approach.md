---
title: Best Practices are not (always) the best approach
description: Reflections on how being a coder in a diverse group of scientists
  or specialists calls for flexbility and maleable practices
date: 2021-01-27T15:19:01.974Z
author:
  - "@mtb_za"
name: bentley-best-practices-not-always-best-approach
oxa: oxa:5w7N97WoctdHdShYPn5p/bmwnIJQQ4e7fhiXYOMvk
---

# Best Practices are not (always) the best approach

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/oBYhnmQ2tHrHZA93T9Vd.6","pinned":false}

I am one of the only people in my research group with much of a programming background. Accordingly, I have spent quite a lot of time helping other people with relatively simple scripts for data analysis. This leads to some interesting observations from time to time. A good example of this are some processing scripts that I wrote for a piece of equipment that reads various chemical abundances in gas (in parts per million). Unfortunately, it has no spatial awareness, which means that doing 'drive-around' surveys and sampling as we travel is not something that can be done out of the box. Fortunately, one can obtain a GPS-based location logger that can be easily put into a vehicle and pull out the location at a specific time. These locations can be exported as a KML file, which is Google Earth’s spatial format. Since KML is a derived from XML, we can process this file using anything that can handle text data.

Even more fortunately, the analyser records about once a second (sometimes two readings per second, sometimes it misses a second), while the GPS logger records more precisely, with one reading per second. This means that we can match a given timestamp from the analyser to the time and place from the GPS tracker.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/CrkG8oSuooMwaVEaHgfP.1","pinned":false}

Since that was the first priority, I hacked together a fairly ugly bit of code, using python and pandas to do just that. It goes against all the usual rules: the location of the file is hard-coded as a string, as are the locations to save a couple of plots and the combined data file. So you have stuff like the following:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/mNFVe78J4EUcahAkzUG0.2","pinned":false}

```null
root = 'C:/Users/mtb/Documents/GitHub/gas_processor/'
data_root = root + '20170313/data/'
analyser_file = data_root + '20170313_readings.csv'
gps_file = data_root + '20170313_gps.csv'
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/onQ9jHfy2d0thQvpQnVC.1","pinned":false}

Clearly this is bad design. But my colleague was perfectly happy with this (partly because it means that he does not have to manually match a reading to a location).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/nenBlNxp3RNud2T4wadZ.4","pinned":false}

```{margin}
The GPS tracker exports the positions in a KML file. [KML is Keyhole Markup Language](https://developers.google.com/kml), and is the variant of XML that Google Earth understands. The goal here was to take those positions and link them (via time) to a reading from the chemistry machine.
```

I then wrote a second script, to simplify the extraction of the locations from the KML file, and combine sequential data files (since the equipment creates a new log every hour or so). These would then be used as input to the first script, and save a bit of mucking about in Excel and copy-pasting data. I decided to push the boat out a little and made it much better, with a series of command line arguments that could stitch an arbitrary number of arbitrarily located files:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/6CX70Yl2cyBqEAr9ZcuA.2","pinned":false}

```null
usage: process_data.py \[--kml\] \[-o O\] \[-t TIME_ADJUST\] files \[files ...\]
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/iTCpGd36Q5U0jtcBDGeY.2","pinned":false}

`--kml` is a boolean indicating that we need to extract the positions of the points from a kml file (defaults to false), `-o` is the location to save the combined file to, `-t` is to account for a delay in gas getting to the sensor as one drives, and `files` are the files to be combined.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/lx3XI7ky4NKIWje2tLTI.1","pinned":false}

Despite being "better", my colleague preferred the approach of the other script, because passing things on a command line is something completely foreign to them. They preferred to just go and edit the source file to point at their data, because it was more obvious what was being changed. They also did not need to think about relative locations of data files and the script.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/2omI76DbLfqYUcJgkPDe.1","pinned":false}

Partly this is something that can be addressed by education, and after a bit of a lesson in how the command line works, they can now use the script. But it might still be better for their use-case to just edit it to something less sophisticated and hard-code the locations of things in again.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/5WvB7sLGBcMaiNBXAqi6.1","pinned":false}

If you are writing stuff for non-technical users, their approach and way of thinking about a given piece of software might be markedly different to your own. Something that is emphasised in proper software development courses is usability testing. Even, possibly especially, when writing software that will be used by non-programming colleagues that is intended to solve a specific problem that is unlikely to have broader outside use (taking two datafiles from two specific pieces of equipment and mashing them together to enable further analysis, for example), we need to make sure that they are comfortable with using it. And if that means that you need to let some best practices slide, I think that that is an acceptable compromise in places.

