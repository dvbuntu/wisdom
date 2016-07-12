---
layout: post
title: CNN/RNN Combo model
cover: none.png
date: 2016-07-12 13:04:24 
categories: posts, stream, keras, data, machine learning, fwtk
---

This is it, a combined Convolutional/Recurrent model.  The plain RNN was ok, but I really want to feed interesting subfeatures to the recurrence, not raw pixel values.  This way, the RNN only has to worry about important features, not computing the features and remembering the past both.

<iframe width="560" height="315" src="https://www.youtube.com/embed/wSpPJtenw_c" frameborder="0"> </iframe>

This turned out to be more difficult to implement than I bargained.  Essentially, we want to run the same convolutional weights against every block (in time) of the input image.  But Keras doesn't inherently support this.

What it does support is graph-based models.  Much like pure Theano or TensorFlow, you can specify general computation graphs and still benefit from the automatic differentiation to do your optimization.  So I had to read in the 8 "blocks" of each image as separate inputs, apply the same convolution to each, then merge the results.  Finally, to get the shape LSTM expects (a time x number of features array), I `Reshape`'d the merged intermediate output and dumped into the same LSTM from last week.

After some fighting with the exact input `model.fit` expects (a list of the inputs, meaning swapping axes between the data points and the blocks), I finally got the model to run.  It cranked through about 2/3 of the training data (~300000 examples), getting about 60% accuracy.  I was impressed that this was in the first epoch of the stupidest, yet most complex, model I could design in an hour.

Unfortunately, I ran into a problem with my GPU.  A memory error came up and corrupted the model.  This not only killed the model fitting, but it also kept me from being able to access the weights.  It's possible that my GPU ran out of memory, but I think that's unlikely.  Even with 64-bit floats, there's only 20k parameters to the model, which would be 160 kB of memory, way less than my card supports.  So it's still a mystery.

While there may be an encore presentation, I think this wraps up "For Well Thou Know'st".  We started with a simple font classification model of logistic regression, got even simpler, and then ramped up complexity of a challenging data set.  If I can get some serious results, I'll publish them in a journal somewhere.
