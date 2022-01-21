---
title: "GemPy: 3D Structural Geomodeling in Python"
description: This chapter introduces GemPy - an open source, 3D geomodelling
  system written in python
date: 2021-01-27T15:28:03.199Z
author:
  - "@leguark"
name: delavarga-gempy-3d-structural-geomodelling
oxa: oxa:5w7N97WoctdHdShYPn5p/QrlE1GpR3NofZr8mBxYm
---

# GemPy: 3D Structural Geomodeling in Python

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/4LzRmByM4O0W01VXErjC.2","pinned":false}

Making 3D geological models is hard. Classical explicit models rely on the expertise of the modeller and their manufactured nature makes them extremely tedious to update as more information is obtained. Implicit modelling based on global interpolations can solve many of these problems, but so far they have been implemented in commercial software only, making them often prohibitively expensive for scientists. Also, proprietary geomodeling software tends to only provide limited functionality through their interfaces or APIs, limiting modern reproducible geocomputing workflows.

Making a 3D geomodel is hard, but making 50 different models for testing different hypotheses or 50000 models to get a complete description of the inherent model uncertainty is much harder. And it was in this climate of frustration and limitation—as is the case with many other open-source projects—when `GemPy` was conceived.

`GemPy` is an open-source Python library based on the potential field method developed by {cite:t}`lajaunie_foliation_1997` and expanded during the following years by many others. The method interpolates interface points and surface poles—i.e perpendicular vectors to the surface dip—to create a potential field from which the domains (e.g. layers) can be extracted {numref}`Figure %s <b69ec23d>`. And by conditioning this potential field and combining multiple of them, it is possible to model faults and unconformities.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/64uXvi1nSLJGedr0v1aS.2","pinned":false}

## Example

To create a `GemPy` model, we have to define its extent, the grid resolution to be used for discretization, as well as the input surface points and orientations, as well as the geological relations of the data.
```
import gempy as gp
geomodel = gp.create_model("Geomodel Name")
gp.init_data(geomodel, extent, resolution, surfacepoints, orientations)
geological_information = {
    "Fault Series": 'Main Fault', 
    "Stratigraphy Series": ('Sandstone 2', 'Siltstone', 'Shale', 'Sandstone 1')
  } gp.map_stack_to_surfaces(geomodel, geological_information) gp.set_interpolator(geomodel)
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/2aKSMfe44ba2bpGAMLx4.2","pinned":false}

Then, we can compute the geomodel using:

```python
gp.map_stack_to_surfaces(geomodel, geological_information) gp.set_interpolator(geomodel)
```

and visualize the geomodel using `GemPy`'s 2D and 3D visualization functionality:

```python
gp.plot.plot_2d(geomodel)
gp.plot.plot_3d(geomodel)
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/qA9t0DMOan5lYrSJBfi9.2","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-NXOOFPqUcPnEg5YW10x0-v1.png
  :name: b69ec23d

  Figure caption needed
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/hnxHHhUq7p1cGpuS90FF.2","pinned":false}

As most other open-source projects, `GemPy` rests on the shoulders of powerful open-source libraries: `pandas` {cite:p}`mckinney_data_2010` for data management, `pyvista` {cite:p}`Sullivan2019PyVista` for 3-D visualization and `scikit-image` {cite:p}`Walt2014scikit` for extracting 3D surfaces from the interpolated potential fields, to just name a few. Thus `GemPy` is another example of how much can be accomplished by integrating the latest developments of the scientific community in the open-source software scene.

One of the main motivations for the development of `GemPy` was to enable the seamless interoperability with other open-source software to enable uncertainty quantification of geomodels. Every object of `GemPy` is accessible and easy to modify, thus making stochastic simulations of any aspect of a geomodel straight-forward.
```
stochasticmodel = StochasticModel(geomodel)

for i in range(1000):
    sample_data = stochasticmodel.sample()
    stochasticmodel.modify(*sample_data)
    gp.compute_model(geomodel)
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/F12hxbeyWqZKAGZI85wQ.2","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-2qok2NdnromBvqvpnSfC-v1.png
  :name: 1e65a5d5

  Figure Caption needed
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/dOIWefVm5S3vSBpKR6LC.2","pinned":false}

For stochastic simulations, computational performance is key. For this, `GemPy` was built using `theano` {cite:p}`Theano2016Theano`, and will soon be ported to `tensorflow`. Both libraries allow us to compute the geomodels on the GPU, significantly decreasing computational time. Our initial research purpose for `GemPy` was to learn uncertain geological models on additional information (e.g. gravity data, knowledge of the regional geology) using probabilistic machine learning (Bayesian networks). This is greatly helped by its seamless integration into `pymc3` {cite:p}`salvatier_probabilistic_2016`, a probabilistic programming framework, allowing us to use gradient-based sampling methods to explore the Bayesian posterior model space efficiently.

But this is only the beginning. Making geological modelling open-source is another step towards an ecosystem were geological modelling, geophysical inversions and process simulations coexist, moving from deterministic unique models to an automatic stochastic system of validation of hypothesis - and where the reproducibility of structural geomodelling is not locked behind prohibitive paywalls.

### References

```{bibliography}
:filter: docname in docnames
```

