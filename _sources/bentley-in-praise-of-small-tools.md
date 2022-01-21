---
title: In Praise of Small Tools, or a short Ode to the CommandLine
description: How breadth and flexiblity of command line tools can be adapted to
  the huge scope of geological problems
date: 2021-01-27T15:18:52.464Z
author:
  - "@mtb_za"
name: bentley-in-praise-of-small-tools
oxa: oxa:5w7N97WoctdHdShYPn5p/r2TaTDL1NN5bB83XlhU3
---

# In Praise of Small Tools, or a short Ode to the CommandLine

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/bZYul9P0AbNFLSjk1xKA.2","pinned":false}

Given the huge scope of geological problems, it is not reasonable to assume that all of these can be solved using large, monolithic solutions. The requirements of a geochemist will be different to the requirements of a structural geologist. As such, they will work with different computational approaches. However, even within a given field, different problems need to be solved, so your monolithic tool that can handle gravity models does not work with magnetic fields, or you have a weird edge­case that needs an additional pre­processing step that can not be accommodated easily. Frequently, this additional capability can be included in a monolithic tools using some plugin system or other. This may or may not require an additional payment for each plugin. There must be a more sensible way, surely?

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/0aoK1GkXYkZUNclscZF5.3","pinned":false}

For those not familiar with the Unix/Linux environment, there is a design philosophy that favours small, single­-use tools. An important part of this is that the various tools need to be able to feed the data that they generate into the next tool, to create an entire workflow. An example of this would be:

```null
cat data.csv | grep ­i ‘sio2’ > silica.csv
```

This will print the entirety of `data.csv`, but then will search for any lines with ‘sio2’ in them. This is then put into a new file, named `silica.csv`.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/YMIB8JUiPwLhZi8FdWg6.2","pinned":false}

My perfect geocomputing world would be arranged similarly. Imagine starting with your datafile, and running it through a series of small programs. Each of these programs would deal with one part of the problem: removing poor data, selecting the datapoints, running the analyses, and creating your data visualisation. If you need to change one aspect of this, the rest of your workflow can be left intact. This can certainly be done with various graphical interfaces, but is easier with small tools once you have done it once, if you have a way to record or script what you have done. You can go back and look at what you have done, and tweak things, if you need to. So maybe your selection of data points needs to be expanded, or reduced. In a toolchain environment this is done by simply altering the parameters to the small program that selects the data.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/tsdqlgmlqR72vvXmgHUZ.3","pinned":false}

This also allows people to focus on solving particular sub-­problems. Like how you will select the data points so that they can be changed, and improved or even how their types can be changed. You can also drop a new step into the toolchain with relative ease. Maybe you need to add a fudge­ factor to all your readings as a pre­processing step, but after you have selected your data points. All this can be done without making anything else work differently.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/kwLwLwc6hOM0o9p50A6j.2","pinned":false}

An obvious requirement for all this to work is that all your tools need to read and write to standard formats. These do exist, for various data­types: image formats such as `.png` or `.svg`, and various non-­binary things such as `.csv` or `.xml` files. If these are done with sensible, well ­understood headers, there is no reason that we can not start to work on small, self­ contained useful tools which we can start to chain together.

