---
title: Domain-Driven Design in Geocomputing
description: ""
date: 2021-01-27T15:19:15.375Z
author:
  - Austin Bingham
name: bingham-domain-driven-design
oxa: oxa:5w7N97WoctdHdShYPn5p/6YoLi4VF5JsdX5vI1AJR
---

# Domain-Driven Design in Geocomputing

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/36hPlt3nCGh2b3TDPjzA.2","pinned":false}

In his seminal 2003 book, Eric Evans popularized an approach to software design called Domain-Driven Design (DDD). At its core, DDD centers around building high-fidelity software models of the problem domain and using these models as the basis for system design.

These domain models capture the *essential complexity* of the domain (constraints, terminology, relationships between domain elements, etc.) while avoiding most commitments to *accidental complexity* (databases, storage formats, communication protocols, UI technologies, etc.) DDD can be a powerful technique, and especially so for software where the problem domain is complex, relatively stable, and depended upon by a large portion of the system's components. These, of course, are qualities of many geocomputing systems, so it's interesting to consider how DDD can be (and has been) used to design software in that domain.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/P36hMLTVZzisbuqelhhr.2","pinned":false}

## DDD as a design philosophy

On the one hand, DDD is a design philosophy. It picks a single aspect of software design, the problem domain, and makes it the foundation for everything else. Most other components depend in some way on the domain model, but the model doesn't have outward dependencies. This means, among other things, that the domain model implementation is insulated from changes in most parts of the system. It only needs to be changed to reflect changes in the domain itself (or, more likely, changes to our understanding or interpretation of the domain.) The domain model is often a very valuable piece of software, and minimizing unnecessary changes to it reduces the defect injection rate. Since the domain model is the foundation of DDD, this systematically improves the quality of entire systems.

This philosophy is a great match for many geocomputing applications where correctly modeling a complex domain is pivotal to developing coherent, accurate software. The value basis for this kind of software generally has little or nothing to do with specific computing technologies. Rather, it's a product of how well the software captures some relevant approximation of reality - that is, the problem domain.

More concretely, it would be odd to ask "How well does this software calculate reservoir volumes using C#, PostgreSQL, and an enterprise service bus?" The value of the software comes almost entirely from answering the first part of the question, and the technology choices should be incidental. Yet many pieces of software (and certainly not just in geocomputing) conflate all of these issues, forcing developers to modify the domain model implementation when, for example, they switch databases.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/FCINI8M7Y9UrjRX5v7Y4.2","pinned":false}

## DDD as a set of techniques

At the same time, DDD provides a toolkit of specific techniques, structures, and terminology for applying this philosophy. Many of these elements are simply the results of finding the common aspects in successful DDD deployments and distilling them into reusable patterns. These elements go by names like *repository*, *bounded context*, and *anti-corruption layer*, and, while we don't have space here to discuss them (there are several books that do a fine job of that), there is one element - *ubiquitous language* - that is particularly apropos to geocomputing.

A ubiquitous language (UL) is simply an agreed-upon set of terms and their definitions that is used ubiquitously throughout all artifacts in a software system, including requirements, code, design documents, email, and so forth. Crucially, the terms comprising the language should be drawn whenever possible from the antecedent culture, be that petrophysics, geomorphology, seismology, or whatever. By strictly and universally defining terms, everyone from geologists (users!) to programmers to salespeople can know when they are talking about the same thing, and they can avoid miscommunication.

Consider the term "well". Does it include a platform? Does it include sidetracks? If so, how do I refer to a single path from the wellhead through the sidetrack tree to a completion? There are dozens of ways to define a well, so unless you're using an agreed UL definition you have to assess each particular instance of the term.

With a UL definition, however, you remove that friction from your organization. A defect report from the field can go from a drilling engineer to front-line support to a developer or domain expert - and back! - with little or no translation. So a UL is not just a development tool, it's an operational tool. With the plethora of domain- and discipline-specific terms in geocomputing, and considering that these terms are often overloaded with multiple meanings, a ubiquitous language can provide a huge boost in productivity and quality.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/bVSm4OSf9fMTDXWy9ghX.2","pinned":false}

## Summary

Domain-driven design is an important and actively evolving area in software development. While this article just touches on a few high points of the approach, hopefully, it's clear that DDD can significantly aid the development of geocomputing systems. We're starting to get reports of successful DDD-based architectures in large geocomputing systems, and surely there are many more that we haven't heard about, so the benefits of DDD are not just theoretical. Geocomputing as a whole stands to benefit greatly from improved development techniques, and DDD will likely play an important role in its future.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/wXWj0DwnmGCQcOHhCiXI.2","pinned":false}

## Suggested Reading

* Evans, Eric (2003). [Domain-Driven Design: Tackling Complexity in the Heart of Software](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)
* Vernon, Vaughn (2013). [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)
* InfoQ.com (2006). [Domain-Driven Design Quickly](https://www.infoq.com/minibooks/domain-driven-design-quickly)

This work is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of this license, visit <http://creativecommons.org/licenses/by/4.0/> or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

