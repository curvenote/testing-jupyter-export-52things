---
title: 5 Minute Intro to HPC
description: ""
date: 2021-04-26T20:29:06.845Z
author:
  - "@gbisbas"
name: 5-minute-intro-to-hpc
oxa: oxa:5w7N97WoctdHdShYPn5p/vld2S24p887JqtjfeWPb
---

# 5 Minute Intro to HPC

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/fOoTJukj03ctsDyJb28L.2","pinned":false}

## Introduction

The need to execute complex and demanding problems at scale is more imminent than ever! The rise of big data and the requirements for just in time solutions made HPC a dominant research area of our era. Typical examples that may be encountered in real-life can be the following: Scientists of various fields need to cross-validate their model. One thousand runs are required, but every one of them takes an hour. Running on their local desktop may take over a month! A biologist has been using small datasets of DNA sequence data, but a new model is ten times as large. Opening the data in his PC is already challenging. Processing the larger dataset will probably crash it.

Large-scale computing systems – shared computing resources with many computers – are available at many universities, labs, or national networks. These resources usually have more processors that operate at higher speeds, more memory, more storage, and faster connections with other computer systems. They are often interchangeably called “clusters”, “supercomputers”, or resources for “high-performance computing” or HPC. In these cases and a lot more ones, what is needed is computer power that can be used in sync.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/kdABULKjHTaAvucTtg0W.2","pinned":false}

## Some Terminology

* What is High-Performance Computing (HPC)? Computing resources that allow people to solve their problems faster or treat larger ones than they would be able to use standard computing resources (e.g. a laptop, desktop, or workstation). It usually implies some parallel computing.
* What is Parallel Computing? Using computing resources in parallel to speed up computation or treat significant computational problems.
* What is a Supercomputer? Typically used to describe an extensive HPC resource such as those found on the Top500 list. Often uses the same technology as compute clusters but at a larger scale.
* What is a Compute Cluster? Typically describes a smaller HPC resource than those referred to as supercomputers. Usually, they use the same technology as supercomputers but on a smaller scale.
* What is High Throughput Computing (HTC)? A subset of parallel computing where computing resources are used in parallel on many independent sub-tasks to increase the rate at which computations can be performed. For example, they vary an input parameter (or input data) to computation and run many copies simultaneously.
* What is Cloud Computing? Using remote computing resources on demand. It is often associated with public cloud computing resources provided by large internet corporations.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/3T3Mx0qhQhfyQpwPxRwO.2","pinned":false}

## Advantages of HPC

Although HPC systems often have slightly more powerful processors, more memory and more storage, the real additional power comes from using the resources in parallel rather than in serial. Using an HPC system often has the following advantages for researchers:

* Speed. With many more processing cores, often with higher performance specs, than a typical laptop or desktop, HPC systems can offer significant speed up.
* Volume. Many HPC systems have both the processing memory (RAM) and disk storage to handle vast amounts of data. Terabytes of RAM and petabytes of storage are available for research projects.
* Efficiency. Many HPC systems operate a pool of resources drawn on by many users. In most cases, when the pool is large and diverse enough, the resources on the system are used almost constantly.
* Cost. Bulk purchasing and government funding mean that the cost to the research community for using these systems is significantly less than it would be otherwise.
* Convenience. Maybe your calculations take a long time to run or are otherwise inconvenient to run on your personal computer. There’s no need to tie up your computer for hours when you can use someone else’s instead.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/W6fKf2dKW15N7zyiHI4u.3","pinned":false}

## Getting started in the world of HPC

Getting familiar with HPC is not easy and is not meant to be achieved through a 5-minute intro! In order to get the first taste of HPC we suggest following these tutorials:

* Open MP tutorial: <https://computing.llnl.gov/tutorials/openMP/>
* MPI tutorial: <https://mpitutorial.com/tutorials/>
* CUDA tutorial: <https://www.tutorialspoint.com/cuda/index.htm>

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/TXp40umYa5kbRJFDvepe.1","pinned":false}

## References

* \[Online\]<https://hpc-carpentry.github.io/hpc-shell/00-hpc-intro/index.html>, CC BY 4.0 license.
* \[Online\]<https://rse.shef.ac.uk/hpc-shell-tuos-training-cluster/aio.html>, CC BY 4.0 license.

