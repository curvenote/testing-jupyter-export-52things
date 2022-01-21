---
title: The grammar of graphics
description: ""
date: 2021-01-27T15:21:10.267Z
author:
  - Dewey Dunnington
name: dunnington-grammar-of-graphics
oxa: oxa:5w7N97WoctdHdShYPn5p/wJBpVFCz6rSkwBcxn2px
---

# The grammar of graphics

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Auzn04kwkdTXnlFE67es.1","pinned":false}

> Dewey Dunnington

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/6rYgxjTkfG3nUms01tvF.1","pinned":false}

Leland Wilkinson's 2005 book *The Grammar of Graphics* (GoG) is a must-read for any geoscientist who communicates data using graphics on a regular basis. Rather than thinking about graphics using pre-conceived templates (e.g., the "scatterplot", the "bar graph", or the "boxplot"), Wilkinson decomposes graphics into several orthogonal components: data, scales, statistics, geometries, and facets. In most implementations of the GoG, data consists of a table with one row for each object (e.g., a sediment sample), and one column for each variable (e.g., from which lake the sample was collected, or the concentration of an element in the sample) (Wickham 2014). One or more of these variables can then be mapped to a scale, which can represent a position on the plot (e.g., x-axis or y-axis) or an aesthetic (e.g., colour or shape). Before being passed to a geometry (e.g., a point, line, or polygon), the data can optionally be transformed using a statistic (e.g., a linear regression). Finally, data can be split into multiple panels using facets (e.g., one panel for each surficial unit). Using these elements, Wilkinson argues, almost any graphic can be constructed.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/bie1KTRasPqmcxTf7US7.1","pinned":false}

Creating a graphic using a template-based plotting library is like filling in a form, and creating a graphic using a GoG-based plotting library is like writing a paragraph on a blank page: writing a paragraph takes more work, but there is a limit to what one can communicate using a pre-conceived template. The flexibility of GoG-based plotting libraries is a similar trade off: creating any particular graphic may take more work, but there are few limits to the type of graphic one can create. If R is your language of choice, the `ggplot2` package provides what is perhaps the most widely used implementation of the GoG; in Python, the `plotnine` package implements the GoG using `matplotlib` as a plotting backend; and in JavaScript, the `G2` library implements the GoG using `D3.js`.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/iJTMociUr6xGTHBG7132.1","pinned":false}

When graphics become more complex there are no pre-conceived templates, in which case it becomes much faster to use a GoG-based library. For example, the graphic shown below in most plotting libraries would require creating two separate plots with manually-scaled axes (to ensure they were the same as each other) and suppressed y-axis labels (on the second plot), drawing three series on each plot, and calculating/drawing two linear regressions. Finally, one would have to create a custom legend to incorporate the series for both plots. In a GoG-based framework, creating this plot requires specifying that the variable `K` should be mapped to the x-axis, the variable `Ti` should be mapped to the y-axis, the variable `Lake` should be mapped to the shape aesthetic, and that one panel should be drawn for each unique value in the `surface_formation` variable. Finally, one needs to specify that the first layer should be drawn using a point geometry (no transformation), and the second layer should be drawn using a line geometry (after calculating a linear regression).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/0zwbn5QuMj9s99kh4mIw.1","pinned":false}

Whether or not you use a GoG-based library, knowing the GoG makes it possible to decompose a graphic into its components and improve it, piece by piece. What makes effectively organized data? What makes an effective colour or shape scale? Could this graphic be more effective if the data were split into multiple panels? A quick read of *The Grammar of Graphics*, and you are likely to find the answer.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/4cGCBpsWfuaWl2Xe0RXW.1","pinned":false}

```{figure} images/5w7N97WoctdHdShYPn5p-DwAvkyu1iiIkxAJ8XIQq-v1.png
  :name: fc4fb661
```

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/T7NizJhpUwihxdzu416T.1","pinned":false}

## References

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/iG1vPvfeEfBGCzPv8i0Q.1","pinned":false}

Dunnington, DW, IS Spooner, WH Krkošek, GA Gagnon, RJ Cornett, CE White, B Misiuk, and D Tymstra (2018). Anthropogenic activity in the Halifax region, Nova Scotia, Canada, as recorded by bulk geochemistry of lake sediments. *Lake and Reservoir Management* **34**. [DOI: 10.1080/10402381.2018.1461715](https://doi.org/10.1080/10402381.2018.1461715)

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/LDSowbV878aYwaI26UVE.1","pinned":false}

Wickham, H (2014). Tidy Data. *Journal of Statistical Software* **59**. \[DOI: 10.18637/jss.v059.i10\](https://doi.org/10.18637/jss.v059.i10}

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/iHCAJfuBe2TFKLJV4jNO.1","pinned":false}

Wilkinson, L (2005). *The Grammar of Graphics*. Springer-Verlag, New York. [DOI:10.1007/0-387-28695-0](https://doi.org/10.1007/0-387-28695-0)

