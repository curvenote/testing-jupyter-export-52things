---
title: "Am=d: A linear algebra approach to seismic modelling"
description: ""
date: 2021-01-27T15:19:39.549Z
author:
  - Ben Bougher
  - "@kwinkunks"
name: bougher-a-linear-algebra-approach-seismic-model
oxa: oxa:5w7N97WoctdHdShYPn5p/O1vu2bfVLapqPziyPY9U
---

# Am=d: A linear algebra approach to seismic modelling

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/pvQx9IUV5TWlLXWV3b4H.1","pinned":false}

> This manuscript is not ready for review. — MH

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/tlyBSDXloqtuM6lm8rqc.1","pinned":false}

In 52 things about geophysics, Bryan Russel wrote an excellent article on Am = d, the simple matrix-vector product at the core of seismic modelling and processing. In this article, we demonstrate the relationship by forward modelling a seismic experiment using the linear model Am = d.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/JZyqc5uZT9kJhMit4IDR.1","pinned":false}

First and foremost, let’s put clear definitions on what these algebraic symbols represent. The “vector” m is the model of the earth, which acts as the input parameters of the experiment. If it seems counter-intuitive to represent the earth as a 1-dimensional vector instead of a slice or volume, think of the earth model as a list of inputs into our experiment, not as a geospatial representation.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/3lYrxQyMUca1NF9utJVE.1","pinned":false}

The matrix A describes the mechanics of our forward model; it transforms our vector of earth parameters m into a vector of observed data d. Generally, m is the physical properties of the earth and A is the physics that models seismic data.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/PDZ4FIDPn7BTPbHqMCtC.1","pinned":false}

This article demonstrates a simple forward model of an angle gather typically used in AVO analysis. In this case m is the elastic properties of the earth, which for simplicity we will define in the time domain. Using the Aki-Richards equation, the angle-dependent p-wave reflectivity can be modelled by the linear equation:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/qEezeAWXV1CLuelGHD1E.1","pinned":false}

> Matt to insert equation

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/y0doIc5XWnY0Aijmq8Bn.1","pinned":false}

where θ is the angle of incidence, α 0 , β 0 , ρ 0 are the average elastic properties (p-wave velocity, s-wave velocity, and bulk modulus), and ∆α, ∆β, and ∆ρ are the differences in the elastic properties across the reflection interface.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/3OYzmUg9KagD9fgeFMjX.1","pinned":false}

Defining a difference operator matrix

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Z6EIkn3T0dOrURhZodTm.1","pinned":false}

> Matt to insert equation

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/9xKwqvg1Gfw2yrhRWubA.1","pinned":false}

and lumping the constant terms, the Aki-Richards equation can be written as a matrix vector product:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/mAE0FBeG9MKtpo8BqwSE.1","pinned":false}

> Matt to insert equation

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/LY3M6XOqQ7BmYP0twLUz.1","pinned":false}

We now model the physics of seismic reflection data as a convolution of a wavelet with a reflectivity series. Convolution is a linear operation, so by definition it can also be expressed in matrix form. This operator is a special type of matrix, called a Toeplitz matrix, where each row is a shifted copy of the previous row.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/bXBar3UMvNWhUUDDBvEl.1","pinned":false}

> Matt to insert equation

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/HuKTOMOOi5djZdrrXJBQ.1","pinned":false}

For seismic modelling each row would be shifted version of the source wavelet. Applying this matrix to 3 we create a vector of synthetic data d. Defining ρ the model vector m =  α  and the operator A as the product of the convolution β and Aki-Richards matrices we arrive at the relationship Am = d.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/miGzCpBaHCAKOPKJdfvn.1","pinned":false}

```null
\# helper functions available on github
include("helper.jl")

\# build a 1D 2-layer earth model
n = 250
vp, vs, rho = zeros(n+1), zeros(n+1), zeros(n+1)
vp\[1:n/2\] = 2750; vs\[1:n/2\] = 1600; rho\[1:n/2\] = 2150.0;
vp\[n/2:end\] = 3000; vs\[n/2:end\] = 2200; rho\[n/2:end\] = 2500.0;

\# stack the parameters into a flat vector
m = \[rho, vp, vs\]

\# make the Aki Richards reflectivity operator for angles \[0-40 deg\]
theta = \[0:2:40\]
R = \[opAkiRichards(n, angle, mean(vp), mean(vs), mean(rho))
for angle in theta\]
R = cat(1, R...)

\# make a 40 Hz Ricker wavelet
dt, f = .001, 40.0
duration = dt \* (n-1) \* 2
w = Ricker(duration, dt, f)

\# make a single Toeplitz convolution matrix
C0 = opToeplitz(w)

\# expand the convolution matrix to match the offset dimensions
\# using a kronecker matrix product.
C = kron(speye(size(theta,1)), C0)

\# make the forward modelling operator A
A = C\*R

\# forward model the data
d = A\*m

\# reshape the data vector into the proper dimensions
d = reshape(d, n, size(theta,1))

\# plot the gather
plot(d)
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/EeNCXoktEIuoOS4OaeY4.2","pinned":false}


> figure tbd

*Figure 1. Synthetic angle gather.*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/fGh1BV9zme7Be5uZmGER.2","pinned":false}

## References

* [Modelling of linearized Zoeppritz approximations, Arnim B. Haase](http://www.crewes.org/ForOurSponsors/ResearchReports/2004/2004-61.pdf)
* [GitHub repository https://github.com/ben-bougher/geoComputing](GitHub repository https://github.com/ben-bougher/geoComputing)

