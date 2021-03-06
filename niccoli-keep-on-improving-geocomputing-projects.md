---
title: Keep on improving your geocomputing projects
description: ""
date: 2021-01-27T15:24:39.706Z
author:
  - "@mycarta"
name: niccoli-keep-on-improving-geocomputing-projects
oxa: oxa:5w7N97WoctdHdShYPn5p/e7USdziNO6xUhoSUtAK5
---

# Keep on improving your geocomputing projects

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Sf7CCQZGh5dXYIyEG3ZP.1","pinned":false}

Revisiting old projects is an essential part of how I approach scientific computing. It is a practical way to cement new coding practices or take advantage of insights acquired, for example, after completing courses or through independent study. Additionally, changes in the focus of the work encourages me to revisit a project.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Dca1jJIk5Iew4OoIOIjo.1","pinned":false}

In this chapter, I will go over my favorite example. This project is an anomaly for me as it is the one I worked on for the longest time, but never published or shared anything about it. Below is a detailed account of how it evolved:

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/sk8yNwyHVgcQ9woseBex.1","pinned":false}

Pre-2010. In this very early stage, my goal was to apply concepts from mathematical morphology to the design of frequency filters for periodic noise such as seismic acquisition footprint. I also wanted to learn how to use the MATLAB signal and image processing toolboxes inside out. I used a few images with moiré patterns, and natural images to which I added noise. I had to figure out how to create 2D periodic noise with sine waves, combine it with an image, either in the spatial or the frequency domain, and learn the ins and outs of 2D FFT. Moreover, I had to come up with a robust method for filtering out the noise frequencies that could also work in a semi-automatic to fully automatic way under the best conditions.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/4kbI2TjW9o7TOZJNgF0h.2","pinned":false}

2010 to 2011. After the initial efforts, my primary goal became the definition and quantification of filtering success. I started using a CT scan of King Tut’s skull ([source](http://guardians.net/hawass/press_release_tutankhamun_ct_scan_results.htm)). I chose a CT scan because the advantage of working with medical images, contrary to images of the subsurface, is that the noise-free ground truth is always known. Therefore, it is possible to characterize how well a filter has performed without using the noise-free input as baseline. As a qualitative and subjective success measure, I used the continuity and interpretability of Canny and Sobel edge detection on the filtered image vs the original with periodic noise. This process is similar to looking at continuity of automatically picked faults on a discontinuity time slice. As a quantitative, but still somewhat subjective measure (dependent on the user experience), I considered whether any signal (bone-looking or geology-looking features) appeared in the difference between noisy input and filtered image. Finally, as a quantitative and objective (and much harder) measure, I thought one could use (not implemented yet) a comparison between the autocorrelation of the noise (which would have to be modelled) and the autocorrelation of the difference (there is a discussion about this in the comment section of Cris Luengo’s blog post: [Evaluating noise filters](https://www.crisluengo.net/archives/490).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/b4IirIhWM3uHCs7iUOTS.1","pinned":false}

2011 to 2012. By early 2012, I had been invited to Stavanger, Norway, as part of a job application with DONG Energy, requiring me to make a project presentation to show during the interview. The work described in the previous section was the key reason for choosing this project, and I turned the presentation into a simulation of my approach to evaluating a new technology. Even without prior offshore experience, I aced the interview and ultimately landed the job. It is difficult to say how much the project presentation contributed to my success but it definitely played a key role. I think this is an excellent example of how iterative improvement and continuous learning can be a great strategy for staying relevant and employable.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/HA5EnGdTWqVDkyXqJ3sY.2","pinned":false}

2014 to 2018. The minute I started moving away from MATLAB to embrace Python, I knew this was going to be a good practice playground. I started right away porting all code to Python (using numpy, scipy, scikit-image, and astropy). After a deeper dive into forensics and computer vision, I was also keen on developing a more mature image processing workflow. Along the way, I occasionally posted updates ([2014](https://mycarta.wordpress.com/2014/11/07/moire-patterns/) and [2017](https://mycarta.wordpress.com/2017/08/13/what-is-acquisition-footprint-noise-in-seismic-data/)) and I was often side-tracked (e.g.: wrote two tutorials for The Leading Edge, did CV work for a colormap talk with Matt Hall, participated in the SEG ML contest, wrote a tutorial on SVM for the CESG Recorder) but never uploaded code to GitHub. However, I would always go back to the project and, eventually, I succeeded (continue reading).

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/sw3oAaQ9uyDod6VTHwQr.3","pinned":false}

2018 to 2020. I continued the work though more examples and I finally managed to get a good amount of coherent material together, which I am now happy to share as a tutorial \[https://github.com/mycarta/2D_FFT_filter_tutorial/blob/master/52-things_tutorial.ipynb\]. I also invited Elwyn Galloway to collaborate, with the idea of putting together a production workflow: faster computations \[[scipy_gaussian_kernel.ipynb](https://curvenote.com/@swung/52-things-geocomputing/scipy-gaussian-kernel-ipynb) and [speed_up_convoluton.ipynb](https://curvenote.com/@swung/52-things-geocomputing/speed-up-convolution-ipynb)\], working with noisier, more challenging data and 3D seismic , interactivity with Jupyter widgets1, stacking of time slices1.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/ES6oj5dFGx30spmOyIoc.3","pinned":false}

2021 and beyond. This was one of the projects at the TRANSFORM 2021 Hackathon project ([discussion here](https://github.com/softwareunderground/transform-2021-hackathon/discussions/9)); \*\*MORE DETAILS COMING SOON\*\*.

