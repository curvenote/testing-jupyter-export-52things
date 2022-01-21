---
title: General purpose GPU programming
description: A time capsule view from 2015 of the emergence of GPU programming
  and its potential in geoscience.
date: 2021-01-27T15:20:51.970Z
author:
  - "@jesperdramsch"
name: dramsch-general-purpose-gpu-programming
oxa: oxa:5w7N97WoctdHdShYPn5p/lGGs2qgaoIjocW1UH7cM
---

# General purpose GPU programming

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/EJLQ3ArolmXpm3738FXW.2","pinned":false}

The seismic industry has profited significantly from rapid hardware development in other industries. One example is the application of Surface Related Multiple Elimination ([SRME](http://sepwww.stanford.edu/public/docs/sep130/intro/paper_html/node7.html)), when it was first introduced it was doomed as too computationally expensive. Today it is the industry standard for multiple attenuation in 2D and 3D.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/QuhZyzhO1shBHkwDkgDj.2","pinned":false}

Already as an intern, with Fugro FSI, I had several nodes running 16 cores and 96 GB ram at my expense for testing purposes. Yearly, investments of $5 to $7 billion are made for new clusters industry wide. We have quite some computing power in our hands, but there's a limit. The limit is in the design of CPUs.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Y56u8sz5Tfjjd9TXE5AS.2","pinned":false}

CPUs are designed to do a variety of tasks. There are so many things we do with our PCs. We finish our PowerPoint presentations, while Skyping across the world. This is what computers are good at; Mostly single sequential tasks.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/idq6KBWHZkU15VBteftU.3","pinned":false}

But there's something new coming up. Walking the show at the EAGE (2015), I was a bit puzzled to see Nvidia and other companies selling hardware that one might know from computer gaming: Graphics cards. Talking to the sales rep, I learned that these are powered by GPUs instead of CPUs and we might be able to utilize this power in the seismic industry.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/MsyYDt7AtPbC9MVu8rwz.2","pinned":false}

However, later I learned, there's a big problem with GPUs. GPUs are slower than CPUs. They're not as smart, although they evolved alongside the CPU. In the end, GPUs just always had a different purpose than CPUs. But they're amazing at one thing; easy calculations, like addition and multiplication. In fact they can do a lot of them quickly and in parallel. Essentially, they function like a big class of 3rd graders.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/P8If4CxCAmYggg4HSCHj.2","pinned":false}

Working in parallel on different cores, means we have to be smart about dividing our resources. Parallel code rises and falls from good planning. Assigning parallel calculations means, we do not want several of these to have to wait for a single other calculation. High Performance computing (HPC) has really improved on this issue, but GPUs take this to an entirely new level.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/DTsgZo8lg5vWDM0Xr7Qn.2","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-nyfXHXhzAHfnVij1Gs8W-v1.svg
  :name: a37c82bf
```

The image shows how CPUs have a lot of space for units for control and cache functionality. Whereas, the GPU uses most of the architecture for the processing functionality. | CC-BY NVidia

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/dN7zI97YR5tKZvPiygL7.1","pinned":false}

Picking up on the analogy of 3rd graders, GPUs are a tad special to work with. When you tell your class to add three sequentially for three times, if you're lucky you'll get the right result of 9. This is a task badly suited for parallel computing, but sometimes it's necessary. Taking this into account, we have to think about memory management. That one slow kid in the class may be still working on the first part of the calculation, but communicate their result the loudest.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/dZqski4YJyFOt1A6dXhH.1","pinned":false}

GPUs work in quite a similar way, they only have very special kinds of cache (most are even read-only). So when we want our parallelized tasks to work with intermediate results, we have to force the GPUs to do so. Of course this synchronization should only be done when absolutely necessary. Additionally, the GPU programming languages have built-in operations that block the memory of a variable until it is modified. These so-called atomic operations save a lot of hassle.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/ggCRklMG58HzFYBPciFM.1","pinned":false}

Memory management is important, when we go into GPU programming. It helps a lot to be fully aware of the hardware we deal with. GPUs work fundamentally different from CPUs and their caching and memory abilities. Learning about the structure of GPUs will enable us to write amazingly fast code.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/i46ee28Gdc7ESBEVIZrZ.1","pinned":false}

What we're talking about here is called General Purpose GPU (GPGPU) programming. There are dedicated languages from Nvidia (CUDA) and the other GPU hardware supplicants, as well as, an open alternative that hooks into these, called OpenCL. Utilizing those, there are possibilities opening up to build highly parallel versions of the most computationally expensive applications we have in seismic processing.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/GwVi8wKUt1CoK1j77wwc.1","pinned":false}

Dedicated GPU cards and even clusters are being sold, opening up new opportunities to get beautiful images out of artifact-ridden seismic data, but it does take work to get there.

