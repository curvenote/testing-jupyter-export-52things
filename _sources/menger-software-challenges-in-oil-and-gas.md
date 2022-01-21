---
title: Software Challenges in Oil and Gas
description: ""
date: 2021-01-27T15:24:10.418Z
author:
  - Bill Menger
name: menger-software-challenges-in-oil-and-gas
oxa: oxa:5w7N97WoctdHdShYPn5p/OkKss4uBzzOmDSuOysTO
---

# Software Challenges in Oil and Gas

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Js590M3mx7WjOLGWNGjy.1","pinned":false}

## The Need

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/mgxkjEQarYniFAzP38aO.1","pinned":false}

Geoscientists demand specialized “best of breed” software applications.  This has resulted in a proliferation of commercial software usage in oil and gas companies. While effective, the use of commercial software holds inherent strategic challenges.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/G255iy7kKglAyGum2n1T.1","pinned":false}

## Software Challenges

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/TbRADamZ1aQKIZNRpnnt.1","pinned":false}

Software is an expensive but vital component of a successful oil and gas company’s E&P strategy. Due to the high cost of development and maintenance, organizations usually find it more cost-effective to purchase software than to develop it in-house. When buying commercial software, each company must address the following challenges:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Qd5A48ZeXYKTZp2Qbv7h.1","pinned":false}

* How to sustain a competitive advantage if you use the same software as your competitors
* How to incorporate a needed new feature that the commercial applications do not support
* How to ensure that different data formats can be read by multiple applications.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/HX4xJc8rUcKLY0fcolZp.1","pinned":false}

Even when commercial software comprises the bulk of applications used in a company, researchers still need to create new programs.  If the expertise to produce and deploy proprietary software is missing, how does technology transfer from the research and development function to the operating units?

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/j8vYxKwDYq7WHtIlo7be.1","pinned":false}

## Extending Commercial Software

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/YhXKVNrwNiesOgbyDpvL.1","pinned":false}

Extending commercial software with a Software Development Kit (SDK) offers one approach to resolving the challenges.  Many commercial applications have carved out a niche in a particular geoscience specialty such as seismic processing or petrophysics. However, SDKs do have some drawbacks.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Pdb8dSs7wyth8nRZ1K6B.1","pinned":false}

* Applications are often built using different software languages.
* Applications run on different operating systems.
* Licensing an application just to leverage its SDK can be expensive.
* Some SDKs are designed for use by professional developers and not by geoscientists.
* Adding new functionality into an existing application can be difficult.
* Software reuse among different SDKs is often impossible.
* Data exchange can be a problem.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/SPqDONq5ghKO6zPdojuY.1","pinned":false}

Using a commercial SDK makes sense for some types of problems. For instance, in the case of a seismic processing system, the problem can be expressed generically as the task of applying a sequence of operations to a collection of seismic traces on a cluster of machines. If you are building a seismic processing module, then the odds are excellent that you can leverage a lot of the functionality in an SDK.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/XoQGqi8osXYZGZaIHjRi.1","pinned":false}

Many SDKs support plug-in extensions to a limited degree, but this does not mean that the application will be sufficiently extensible to support all needs. For example, multi-component seismic data is not supported in most of the current SDKs. One would have to add input/output functionality, visualization code and new data structures to handle multi-component data before effectively adding such new functionality to the software.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/z17i3M7HexV8VnCatqIS.1","pinned":false}

Data exchange issues are exacerbated by each SDK’s use of a different database.  Middleware technology (e.g. OpenSpirit, GeoShare) and workarounds involving file transfers can be employed in many cases, but sometimes developers must extend several applications with custom input and output code in order to complete a workflow for production use.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RbLo3I9Mp969LnBhy6Jd.1","pinned":false}

## Developing Software Internally

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/lY76VhnUl08HW5YOnS2L.1","pinned":false}

In an era where the same software is used by most companies, it is tempting to try to gain a competitive advantage by developing more software in-house. However, the requirements for in-house software are just as demanding as those for commercial software, and development is handicapped by fewer resources and a relatively small user base that provides limited feedback.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/yUHcolPRx5U50YzDQUtg.1","pinned":false}

Based on historical project data, internally developed software has a lifetime cost of approximately $100 for each line of code that is written.  This shows a clear need to avoid writing code whenever possible.  The easiest way to do this is to employ a “buy-versus-build” strategy and to focus on building only the most valuable new functionality.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/dhloR7OPEkLqRfXQx5an.1","pinned":false}

Software developed internally needs to have a high perceived business value. This is achieved by building new functionality that cannot be purchased commercially, which occurs when the functionality is innovative or when it is a niche application with a small user base.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/K8PxuHSJnWBKw5TlGUJI.1","pinned":false}

Oil companies frequently generate software requirements that are specific to business processes and the geological provinces being explored.  Commercial vendors cannot expect a reasonable return on investment if they tailor software to fit such specific business needs and so it is left to the oil and gas company to build its own software… or is it?

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/eRcegClJBqGWCGlnXyvT.1","pinned":false}

## Open Source Strategy

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/dyVG4A1jwqz9E7ytyRvU.1","pinned":false}

The following quote is from the authors of Innovation Happens Elsewhere, Open Source as Business Strategy by Ron Goldman and Richard P. Gabriel (Morgan Kaufmann Publishers, San Francisco).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/DR4sEG4Z6LcXLr1evmWc.1","pinned":false}

> …companies need to find ways to use outside innovations and to become part of a distributed fabric of innovation through a combination of licensing and well chosen gifts. Although the concept of a gift may not at first seem to fit well with free-market capitalism, it might when thought of in the context of collaborating with others to build common commodity-like infrastructure.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/4pjuv087BcnA6U5vOwKB.1","pinned":false}

If the oil and gas company could make effective use of open source software, and give back to the open source project from time to time, then it could find itself with lower total cost of ownership, higher usability in its internal codes, and research software that finds solid usefulness in its operating units.  The goal of using an open source project is to avoid spending time writing code that others have already written – code that does the basic I/O, visualization, menu-ing, graphical user interface design, etc. and to concentrate on the software that gets the geophysics done.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/aGpoq4PG7THVrhAdXyLu.1","pinned":false}

## Sustainable Open Source Development

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/xngnNo8yCEFU2NKnuc84.1","pinned":false}

Sustainable open source development requires a stable entity that can house the software, maintain the web presence, advertise and solicit for collaboration, and to own the intellectual property. The ideal entity is a non profit organization whose purpose is to foster collaboration and elevate the common good. It should have as one goal the education of the next generation of geoscientists.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/kVmEyc1VxxdyZBLXrJ3b.1","pinned":false}

Sustainable open source development also requires proper licensing that allows:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/b8lKzWaMpKpSLE8zLFxl.1","pinned":false}

* businesses to use the product to make money,
* universities to use the product to house research projects and to train students,
* oil and gas companies to use the product to house proprietary programs.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/z8cIu7cRyvfVXcOJLqzH.1","pinned":false}

In order for this kind of product development to be successful in the geophysical realm, it will need to:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/YyaCcK5qUWCLi3bMsldD.1","pinned":false}

* support multiple data formats,
* contain a standardized domain model,
* simplify development of new data visualization tools,
* encourage code reuse,
* have a user-friendly design,
* have the potential to evolve as a geoscience development platform,
* be built upon a solid foundation and framework.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/RrWJxZ3Q3Ds7nVzImrcF.1","pinned":false}

## Managing Open Source Software

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/9InWPK4ZqV9IRpmdeC7g.1","pinned":false}

Software is available.  For seismic processing, there are Madagascar, SU, CPSeis, and FreeUSP.  For quantitative interpretation there is QI and for general purpose interpretation utilities there is GeoCraft.  What we lack on some of these projects is the proper open-source license. We also lack the non-profit organization that can bring geophysical open-source projects into an umbrella legal structure and merge the frameworks where appropriate.  We need the organization that can relicense with business-friendly licensing that helps the developers to justifiably reap some rewards for their efforts but that still allows the hobbyist and student to use the software.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/WmkolItWvsErUnSsBmth.1","pinned":false}

## Parting Thoughts

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/p3p1uumCjfNTv1cKoxGl.1","pinned":false}

As a founding member of the GeoCraft team, I was able to think through many of these ideas, but the missing link then – and now – is the non-profit organization.  It is time to create that organization and to change the way the industry writes its software.  We should not want to damage the commercial software industry, but we do want to:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/8VmbZA8dlxHkemKRZbGH.1","pinned":false}

1. stop inefficient software development in the oil and gas companies,
2. create platforms for grad students to build their research upon, and
3. raise the bar for commercial offerings.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/NSmjeoTa2LP654nHTUSN.1","pinned":false}

Pasted from <http://hpcinoilandgas.blogspot.com/2009/05/software-challenges-in-oil-and-gas.html>

