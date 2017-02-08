---
layout: post
title: Crop Disease Model Simplified
cover: none.png
date: 2017-02-08 11:20:42 
categories: posts, stream, python, crop disease, keras
---

With a special thanks to [NerdFarmer](http://nerdfarmer.com/), we have another sponsored episode on classifying leaf diseases.  This time, we focused on trying to simplify the data and the model to make it a little more approachable.  Previously, I squared up images by cutting to the smaller dimension and rescaling to 224x224 (thinking maybe transfer learning would happen later).  This time, I decided not to throw away any part of images.  So I padded the smaller dimension to equal the larger.  To get them all on the same size, I still rescaled, now to 64x64.  So rather than holding 2GB of data in memory, it was only about 256 MB; much faster to work with.  During the stream itself, we even reached 66% accuracy.

<iframe width="560" height="315" src="https://www.youtube.com/embed/OPi4wT7Ecb8" frameborder="0"> </iframe>

After the stream, a fan commented that he used the same model to get about 100% accuracy!  While this is great to hear, we may be overfitting the model.  At this point, we should select a *random* subset of the training data to use for validation.  I fear the accuracy may not be so stellar.


