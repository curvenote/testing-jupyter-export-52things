---
title: Is Geology Cartesian?
description: This chapter reviews some reasons, tools and techniques to describe
  the subsurface and simulate its behavior using unstructured meshes.
date: 2021-01-27T15:20:04.779Z
author:
  - "@geologuic"
  - Bruno Levy
name: caumon-levy-is-geology-cartesian
oxa: oxa:5w7N97WoctdHdShYPn5p/lR5IyeHfJwNVM0Nu5lDk
---

# Is Geology Cartesian?

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/A53PBHJ5LQiOT8UAyXmW.3","pinned":false}

Geocomputing is about processing and interpreting geo-data, realizing physical simulations and solving inverse problems. All these tasks somehow call for approximating time and space by discrete points, some associated values, and the neighborhood relationships used to connect these points.

Grids typically implement these principles, but which grids should be used in geocomputing {numref}`Figure %s <c3b34628>`? Cartesian grids have many qualities, owing to their structure and regularity. Neighborhoods are trivially defined. Many great image processing algorithms, geophysical methods, geostatistical algorithms, and other useful numerical techniques directly apply to Cartesian grids. A computer screen is a grid. Most computations in reflection geophysics use Cartesian grids, and produce excellent images of the subsurface.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/uf4H3WQb0uqf4z5TjHSE.5","pinned":false}

Yet, a vast community of geoscientists and physicists, not only in the academic world, has spent much effort to develop codes on **irregular** and **unstructured grids**. For example, reservoir engineers and hydrogeologists use deformed Cartesian grids (also called corner-point or geocellular grids, see for instance [DUMux](https://dumux.org/)). The bravest use fully unstructured grids (made of tetrahedra, prisms or even arbitrary polyhedra). From a programming standpoint, these grids are scary. Many of the efficient algorithms designed for Cartesian grids fall apart when considering irregular geometry and arbitrary connectivity. Parallelization remains possible, but is more difficult to implement. Still, in addition to commercial software, several open-source packages exist nowadays to work effectively with unstructured grids, for example:

* Generic meshing and geometric libraries: [TetGen](http://wias-berlin.de/software/index.jsp?id=TetGen), [GMSH](https://gmsh.info), [Geogram](http://alice.loria.fr/index.php/software/4-library/75-geogram.html), [MMG](https://www.mmgtools.org), [CGAL](https://www.cgal.org).
* Numerical simulation packages for generic computations such as [Moose](https://mooseframework.inl.gov/), [FreeFEM](https://freefem.org), [MFEM](https://mfem.org), or specialized such as [OpenFOAM](https://www.openfoam.com) in fluid dynamics or [SeisSol ](http://www.seissol.org)in seismology.
* Integrated geocomputing platforms: [OpenGeoSys](https://www.opengeosys.org) , [RINGMesh](http://ringmesh.org), [OpenGeode](https://geode-solutions.com/opengeode).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/cXuL3nGwqajhCZmMUynL.3","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-hUid2ST5QE0eIdPPLz8F-v1.png
  :name: c3b34628

  Four possible meshes representing the same geological structure (a thrust fold in Corbieres). Courtesy of Arnaud Botella.
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/B8gpzh4t9dxD1WbJ7tjQ.2","pinned":false}

Why did unstructured grids come up? This may be explained by some fascination for pretty pictures and a form of mathematical beauty of these meshes. But there has to be something else to justify investment in the business and engineering world.

We suggest that a stronger reason holds in the classical quote attributed to Albert Einstein: "Everything should be made as simple as possible, but not simpler".

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/MShTD3tNJL2AIclhELnv.7","pinned":false}

## Geometry / discontinuities

Geological processes are a tremendous engine to create geometrically complex changes of physical parameter fields; these changes can be quite abrupt, as two rock samples 1cm away one from another may have been formed million years apart {cite:p}`Wellmann20183`.

Such sharp geological features may have arbitrary geometries, which is generally approximated in Cartesian grids as stair-steps. This may (or may not) be a problem, depending on the application at hand. Explicit representation of geological objects can be essential to focus on geological details deemed important for a particular purpose. This is exemplified for instance in the area of fracture modelling.

Studying fracture growth, quantifying fault reactivation and displacement needs an accurate geometric representation. The connectivity of fractures is also a very important point when it comes to understand subsurface flow. As fractures seldom align on orthogonal directions and generally span multiple scales, their explicit representation is very useful at some point (e.g., {cite:t}`nick_comparison_2011`; {cite:t}`Bonneau2016JGRSE`).

More generally, an accurate geometric representation of subsurface geologic features is important to create benchmarks such as the [SEAM ](https://seg.org/SEAM/home)benchmark models; homogenized parameter field on Cartesian grids can then eventually become handy {cite:p}`Cupillard2018Non`.

## Adaptivity

With Cartesian grids, the grid block size corresponds **everywhere** to the size of the smallest feature that you want to represent. This is generally fine in two dimensions (digital pictures have the same limitations and are still very good "digital eyes"), but raises significant computational challenges in three-dimensional domains. Moreover, the Earth remains mostly inaccessible to observations an hidden “details” may matter.

Practitioners, therefore, make compromises by averaging some (expensive) borehole measurements at flow simulation block scale; conversely, values away from observations are poorly constrained and are sampled using geostatistical methods, even in the areas where heterogeneity has little or no impact. With unstructured grids, the element size can vary according to the dimension of the features that matter (See for instance {cite:p}`Sambridge2005Seismic` for further discussions in seismology).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/UEsRbi3u4qA1rgnGnJWt.1","pinned":false}

All in all, unstructured meshing technology, once restricted to CAD/CAM applications, has matured to handle realistic geometries of geological features. We believe this is now the right time to use these technologies to address longstanding geocomputing challenges.

### References

```{bibliography}
:filter: docname in docnames
```

