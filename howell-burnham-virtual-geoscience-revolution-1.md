---
title: "The Virtual Geoscience Revolution: From William Smith to Lidar"
description: A historical perspective on the development of technologies with
  initial application to Virtual Outcrops - Part I.
date: 2021-01-27T15:22:49.102Z
author:
  - John Howell
  - "@bsburnham"
name: howell-burnham-virtual-geoscience-revolution-1
oxa: oxa:5w7N97WoctdHdShYPn5p/tV9ana9lvD1kgFdNY9K9
---

# The Virtual Geoscience Revolution: From William Smith to Lidar

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/jUha6q9y9F8uUmxGg9Mk.8","pinned":false}

In 1799 a surveyor called William Smith published the World’s first geological map and fundamentally changed the way in which geologists envisaged the subsurface {cite:p}`winchester_map_2001`. For the next 200 years, field geologists did as Smith had done, tracing geological boundaries on the ground and used ink pens and coloured pencils to record the surface expression of the geology onto paper and maps ({numref}`Figure %s <66139bc1>`A). Even today, the largest single component of any undergraduate degree in the UK is the “mapping project”, where students make detailed maps of a selected area. There can be very few sciences where there have been no significant changes in the basic data collection methods for over 200 years. However, since the turn of the 21st Century we have seen a quiet revolution in the way in which field data are collected, analysed, and displayed. We call this the Virtual Geoscience Revolution and it has come about in a number of discrete phases, each of which have resulted from the development of a number of distinct but parallel technologies.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/C2QYk2kZE05YHPJ2vknE.2","pinned":false}

### Stage 1 – Satellites and GPS.

It’s not easy to remember a world without GPS, but in the mid 1990’s to locate yourself on a map, orienteering with a compass and landmarks was standard practice. Early GPS units were cumbersome and inaccurate, but towards the end of the 90’s small handheld units became affordable and usable in the field. The application still relied on transposing coordinates onto a paper map and had errors that meant they were not good enough for detailed mapping, but this was the first stage of digital data collection. At the same time, more expensive differential GPS systems started to appear that relied on stationary base stations to correct satellite drift (post-processed or in real time) from a rover unit position. For the first time it was possible for a geologist to trace a field boundary and record it digitally.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/U0jKykEtZ0tIVuESIxRv.5","pinned":false}

### Stage 2 – Early Virtual Outcrops

Whilst walking out geological boundaries was the start of digital mapping, it was time consuming. Shortly afterwards, a whole new school of digital geology was born. With a virtual outcrop, the entire outcrop is captured in a 3D picture where the exact location of every pixel is recorded. The earliest attempts (that we are aware of) came when researchers at Statoil tried to use photogrammetry (more about that later) to capture cliffs in Utah and Spain as part of the original SAFARI Project {cite:p}`flint_sedimentary_1993`. These attempts failed because, while the concept was good, computer hardware and storage space had yet to catch up.

The first practical virtual outcrops came in the early 2000’s with the work of [Carlos Aiken](https://profiles.utdallas.edu/carlos.aiken) and others at UT Dallas {cite:p}`Xu2000Creating`. A robotic Total Station was used to record the location of a few tens of points on a cliff face. This provided a framework onto which photogrammetry was used to produce a photorealistic model of the outcrop. Whilst this work was pioneering, it did not receive the attention that it deserved at the time.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/m99Y8WAubkIN3fpYTgSk.11","pinned":false}

### Stage 3 – LIDAR

Soon after Aiken et al. were building their models, terrestrial lidar appeared on the scene. Designed for architectural scanning, the first application in Geology was by Jerry Bellian and Dave Jeanette at the Bureau of Economic Geology {cite:p}`Bellian2005Digital`. A lidar system records the time of flight of a rapidly pulsed laser beam shot at cliff faces (several tens of thousands points per second – up to a million today) and calculates a spot position. This produces a point cloud of millions of georeferenced points that accurately recorded the shape of the outcrop. The subsequent addition of a digital camera meant the point cloud could be coloured to produce a highly accurate but lowish resolution 3D image. The 3D image is significantly improved when the point cloud is triangulated and meshed to create a solid surface onto which the photographs could be draped. The virtual outcrop, as we know it today was born ({numref}`Figure %s <66139bc1>`B).

```{figure} images/5w7N97WoctdHdShYPn5p-ohEazLG1tf8Ld9DbnEl3-v1.png
  :name: 66139bc1

  Lulworth Cove, UK. A. Typical sketch with annotations that a geologist would create rom field observations B. 3D view of a virtual outcrop of the same outcrop in the field sketch.
```

### References

```{bibliography}
:filter: docname in docnames
```

