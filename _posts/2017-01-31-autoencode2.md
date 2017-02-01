---
layout: post
title: Convolutional Autoencoders
cover: none.png
date: 2017-01-31 22:15:06 
categories: posts, stream, machine learning, python, autoencoder, keras
---

Ah, Autoencoders, previously [my nemesis]({{ site.baseurl }}/2016/12/13/autoencode.md), but now just another tool in the toolbox.  This time, I wanted to sort out how to handle convolutional autoencoders when handling strange sizes.  `UpSampling2D` is the opposite of `MaxPooling2D` except for odd dimensions.  Upsampling can't know that you removed an odd-numbered row in the encoding step.  To handle this, you need to add an empty row of zeros back with `ZeroPadding2D`.  This seems incongrous at first, but the more I thought about it, adding fake zeros is pretty much the antithesis of removing a row of pixels.

<iframe width="560" height="315" src="https://www.youtube.com/embed/pIrKP4DyH-Q" frameborder="0"> </iframe>

The model itself, however, takes about 5 minutes per epoch, so I didn't wait around to see how it would train.  One alternative might be to train on the first 16 columns, and use that for each slice.  Maybe another time.
