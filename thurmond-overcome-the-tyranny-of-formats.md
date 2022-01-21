---
title: Overcoming the tyranny of formats
description: ""
date: 2021-01-27T15:27:33.094Z
author:
  - "@grajohnt"
name: thurmond-overcome-the-tyranny-of-formats
oxa: oxa:5w7N97WoctdHdShYPn5p/YvOXdnMLzGKdrIZgDdzQ
---

# Overcoming the tyranny of formats

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/99EbfaGXicCElRbL3aUq.1","pinned":false}

Format conversion is a great way to get started in programming, because the challenges are usually very simple, and it opens up an enormous toolbox that becomes useful for almost everything else you will ever have to do, even if you never go any further with programming. Without this skill, you can only work with formats that your software can read and write, which can quickly stymie good ideas.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/gmMSkJLWn6vkYbjksjO8.1","pinned":false}

When I first started working with 3D data, I was lucky enough to have learned some simple programming and was comfortable reading and manipulating data. At the time, 3D polygonal mesh construction and editing was an esoteric art. Software vendors mostly used their own formats, and format exchange programs were either non-existent or prohibitively expensive. To do the work I knew I wanted to do, I had to figure out how to convert between different formats. What I didn’t know at the time was that this was a remarkably simple problem.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RhLp78k3NbfJCWJRsiJQ.1","pinned":false}

Like most data files, 3D polygonal mesh formats are made up of very simple structures. The main information is a sequence of points or *vertices* with (*x*, *y*, *z*) positions, and set of *faces* that describe how to connect these points. Additionally, the files were typically just plain text!

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/iutXYAu8crPFhQ8WiTN8.1","pinned":false}

For example, here's how to encode a simple triangle in Wavefront OBJ format:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/b6bf53hvCcOIJwQRmn5C.1","pinned":false}

```null
v 0.0 0.0 0.0
v 0.0 10.0 0.0
v 10.0 0.0 0.0
f 1 2 3
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/iB0qkdJRWxDXuuklmm7o.1","pinned":false}

And here's the same triangle in 3D Systems STL format:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RVqE3fCe1YZcgS6Umg6X.1","pinned":false}

```null
facet
outerloop
 vertex 0.0 0.0 0.0
 vertex 0.0 10.0 0.0
 vertex 10.0 0.0 0.0
endloop
endfacet
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/5bMqO6DXIxVMudBY4PBx.1","pinned":false}

If you can program just enough to read in an array of vertices and faces, converting between these two formats is nothing more than a little book-keeping and outputting the right text.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/tNanp188wFi6qIT2Vqsy.1","pinned":false}

Once I understood this basic building block, I put together a set of very simple scripts that allowed me to convert between formats and connect the capabilities of various software tools. To others, this seemed like a magic wand that allowed me to do things that they could not, but in reality it was only a few hundred lines of code. I carried this very useful toolbox around with me for years, but turned to it less and less as time went on and software limitations slowly vanished.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RNjLeCBXjHTK7LDxgdDj.2","pinned":false}

Recently, I started working with 3D printing as a hobby. As it turns out, the STL format I had dealt with before is the de facto standard for the interchange of models for printing. I put some of those old skills to work and built models that others hadn’t seen before, like a dual-color topographic model of the Gulf of Mexico (have a look at [thingiverse.com/thing:617729](thingiverse.com/thing:617729)). Being unafraid of working with 3D models and programming meant that it was easy to pick up OpenSCAD (openscad.org), and to use it to allow others to make their own customized geology block models for teaching (for example, [thingiverse.com/thing:2222945](thingiverse.com/thing:2222945)), or more frivolous things ([thingiverse.com/thing:1985430](thingiverse.com/thing:1985430)).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/SnjR7IhnJCrxUq5Zm13f.2","pinned":false}

These days, there’s much more open sharing of code, and it’s easier than ever to find a format reader or converter already written for you, but I still see people thwarted by format conversion on a regular basis — for example, have a look at <https://ageo.co/q2e3Wt>. Having even a rudimentary knowledge of programming and format conversion can be a skeleton key that opens up an incredible number of doors — sometimes even to unexpected places.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/HpHaXSiKTVlooXIRdHsB.1","pinned":false}

*Could add figure if room*

