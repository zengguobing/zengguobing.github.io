---
layout: archive
title: "SAR Geodesy"
excerpt: "Develop SAR and InSAR related algorithm and tools, including geolocation, coregistration, time series analysis, noise reduction, and uncertainty quantification.
  <br/>
  <br/>
  <img width='600' src='/images/phase_correction.jpg'>"
collection: research
author_profile: true
---

## Small Baseline InSAR Time Series Analysis with MintPy

We present a review of small baseline interferometric synthetic aperture radar (InSAR) time series analysis with a new processing workflow and software implemented in Python, named MintPy. The basic idea is to apply the phase corrections in the time series domain (as shown below), instead of the traditional interferogram domain, to leverage the small orbital tubes and regular sampling of modern SAR satellites, for more efficient computing, in addition to a few more features. Check more details in [Yunjun et al. (2019)](https://yunjunz.github.io/files/Yunjun_etal-2019-mintpy.pdf). 

<img width='800' src='/images/phase_correction.jpg'>

+ The code is open-sourced and freely available on GitHub at [https://github.com/insarlab/MintPy](https://github.com/insarlab/MintPy) with documentation, tutorials in Jupyter Notebooks and test data. The software has been widely used in the science community, including the [UNAVCO InSAR short course](https://www.unavco.org/event/2021-short-course-insar-processing-analysis-isce/) since 2019.


## Phase Unwrapping Error Correction

The estimated InSAR time-series can be potentially biased by wrong integer numbers of cycles (2π rad) added to the interferometric phase during the two-dimensional phase unwrapping, to which we refer simply as unwrapping errors. We develop the following two methods to automatically correct unwrapping errors using constraints from the space and time domain, respectively. Check more details at [Yunjun et al. (2019)](https://yunjunz.github.io/files/Yunjun_etal-2019-mintpy.pdf) and [Oliver-Cabrera et al. (2021)](https://yunjunz.github.io/files/Oliver_etal-2021-PUError.pdf).

+ The bridging method connecting reliable regions with minimum spanning tree bridges (particularly suitable for islands).

<img width='800' src='/images/unw_error_bridging.jpg'>

+ The phase closure method exploiting the conservativeness of the integer ambiguity of interferogram triplets (well suited for highly redundant networks).

<img width='600' src='/images/unw_error_closure.jpg'>


## SAR Geolocation and Coregistration

SAR and InSAR time series analysis generally starts with the stack coregistration. In this paper, we explore the approach of geometrical coregistration using precise orbits and DEM, refined by estimates from external models and products to correct for the atmospheric propagation delays and known surface motions, for operational stack coregistration. We call this the model-adjusted geometrical image coregistration (MAGIC) approach. To verify this approach, we evaluate the impact of different sources of geolocation errors on stacks of C-band Sentinel-1 and L-band ALOS-2 data, with a focus on the impact of the ionosphere.

+ Yunjun, Z., Fattahi, H., Pi, X., Rosen, P., Simons, M., Agram, P., & Aoki, Y. (2021). Range Geolocation Accuracy of C/L-band SAR and its Implications for Operational Stack Coregistration. _IEEE Transactions on Geoscience and Remote Sensing_ [in reivew].
