---
title: Quality Checking your Spatial Data
description: ""
date: 2021-01-27T15:28:13.379Z
author:
  - Hassan Sabirin
name: sabirin-quality-checking-spatial-data
oxa: oxa:5w7N97WoctdHdShYPn5p/HfMn8Xm2AHVhr0f3LGmx
---

# Quality Checking your Spatial Data

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/E4HLhSZ6NaQ7FmnbBdRf.1","pinned":false}

I have made many dangerous statements throughout my career; for example raising the overpressure zone alarm during a drilling operation when no such risks were predicted during planning stage. It is a difficult thing to stand your ground when the majority of opinion is against you. Having a solid list of proofs and evidences is always a good thing to keep in your arsenal. My best record in this field is when I announced in a meeting that an unbelievably large quantity of well coordinates in the corporate database are in error, thus deeming most of the associated data to be unusable. In this text I will try to elaborate on what method and tools I used to get to that conclusion.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/4UePQcdsy3J6tvmdXdVm.1","pinned":false}

There are two basic components in positioning: a coordinate and a coordinate system. A correct position must have these two fields populated and verified and the coordinate system identifiable to a valid one. The familiar Cartesian system is easy to understand and relate to, but not everybody knows what is a WGS 1972.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/vu1us2uQ1c2nS5rNk4ZH.1","pinned":false}

Modern positioning systems today give coordinates in the WGS 1984 system and that is what the recent geospatial data are usually stored in. However, legacy data are still very much regarded in value and they are still kept in various arcane coordinate systems. When positioning data is stored in two different systems, the situation provides for a great opportunity to test the potential error in either of the coordinates. Here is an example of such data:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/ev6G8lKYTYXDC8EU3zYf.1","pinned":false}

> Matt to format table

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/mVP7n9pz3gKA1CUhp1M7.1","pinned":false}

*Table 1: Example of Well Header Spatial Data*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/I5Jbi94iLBIOMMP3vra4.2","pinned":false}

To proceed with this method, there are the development tools I normally use `pyproj` (<https://pypi.python.org/pypi/pyproj> or pip install pyproj )

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/KEQtnghywZSMR9UdSHdz.1","pinned":false}

pyproj comes pre-installed with EPSG definitions of coordinate systems. However, I have seen certain definitions from pyproj which deviates from the official registry at www.epsg-registry.org.This may be caused by pyproj CRS definition being early-binding in nature, and you can’t select an alternative datum-to-datum transformation without altering the definition by hand. My usual work process assumes that most of the definitions are correct and will only start exploring the root cause when I see suspicious results. The logic is that most of the time there is only one way for a coordinate to be correct and plentiful others for it to go wrong.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/vABiY05LMiEAMxDCbzzN.1","pinned":false}

So if you have the tools installed, this is how you use pyproj:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/8sky5MSHMdkoCpNGtkIl.1","pinned":false}

```null
import pyproj

\#init srs
w84UTM50N_srs = pyproj.Proj( "+init=EPSG:32650" ) 

\#Without preserve_units=True, all results will be returned in meter
TimbBRSO_ft_srs = pyproj.Proj( "+init=EPSG:29872", preserve_units=True )

\# these are original/stored coordinates in Timbalai BRSO(ft)
long = 114.0
lat = 5.0
x = 1900000.0
y = 2050000.0

\# and this is WGS84 UTM 50N coordinate
W84_x = 278000.0
W84_y = 626000.0

\# Section A – projection and unprojection
\# ‘c_’ indicates calculated values
(c_x, c_y) = TimbBRSO_ft_srs (long, lat)		# Timbalai BRSO geographic to projected coordinate
(c_long, c_lat) = TimbBRSO_ft_srs (x,y, inverse=True)	# Timbalai BRSO projected to geographic coordinate

\#Section B - transformation between different datums/projection - here from WGS84 50N to Timbalai BRSO(ft) 
(c_29872_x, c_29872 _y) = pyproj.transform(w84UTM50N _srs, TimbBRSO_ft _srs,  W84_x, W84_y)
\# and the other way around
(c_32650_x, c_32650 _y) = pyproj.transform(TimbBRSO_ft _srs , w84UTM50N _srs ,  x, y)
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/9gFHEy8pyHkHYlAs5FcQ.1","pinned":false}

Thus, given a position data set in Table 1, one can use the above examples to re-attempt the projection and datum-to-datum transformation between two coordinate systems in both directions. The value or magnitude of absolute difference between the calculated and the stored coordinate should alert you to potentially erroneous coordinates:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/9fKqhnH9ecNKpDFbgU5U.1","pinned":false}

```null
\#Here we calculate the abs difference between stored and calculated values.
\#Refer to variables defined in Section A
abs_diff_x = abs( c_x – x )  # calculate absolute difference
abs_diff_y = abs( c_y  – y)

\# You can also calculate offset: use Pythagoras method sqrt(dX\*dX + dY\*dY) and then magnitude: log10(offset)
\# Insert your own code here to do something when the difference in values exceed a certain value or magnitude
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/ok0BQmoF8q4TnJj2D0yg.1","pinned":false}

The next thing to do is to adapt this measurement method in a while or for loop and run it across all rows in your well header database (perhaps by using ODBC/SQL calls).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/FlKPaDnTbO2Q6dFlLFvh.1","pinned":false}

Through my own experience with this process, I have picked up silly one digit typo that introduced five to six thousands in meter of error, coordinates stored in different systems than actually claimed, angular lonlats populated in place of XY coordinates. However before you go out to meet the world with the excitement of your discovery, remember to double and triple check that, 1) you have tested that the pyproj CRS you are using is exactly similar in behaviour to the EPSG definition, 2) your measurement units are correct, 3) your code is comparing positions of the same object (not jumping between database rows), 4) you have made an attempt to double-check your work with a geodesist. A disputable premature statement could hurt your reputation like the boy who cried wolf, and we don’t want anything like that now do we ?

