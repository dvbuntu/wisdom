---
layout: post
title: Keras Custom Activations and RNNs
cover: none.png
date: 2016-04-05 12:27:54 
categories: posts, stream, tensorflow, machine learning, keras, theano, rnn
---

I missed posting about last week's successful video defining custom Keras activations!  This wasn't nearly as painful as figuring out how to access the weights in an `skflow` model, but it's about as much work after the fact.  Like everything in life, no tool is perfect.

<iframe width="560" height="315" src="https://www.youtube.com/embed/56EuHj2V8K8" frameborder="0"> </iframe>

And just tonight I started looking at Recurrent Neural Networks.  These are cool ways to introduce the element of time in your dataset.  Essentially, you're adding extra features from the previous data point into your current time step's neural net.  It gets more complicated than that with things like LSTM (use those features to decide when to "forget" old information and the like), but we're sticking to the basics.

Unfortunately, I didn't see a tutorial on using RNNs with Keras, so we're winging it off of a [Theano tutorial](http://deeplearning.net/tutorial/rnnslu.html).  But it's a little light on the explanations and details.  Hopefully my video starts to clear the waters.

<iframe width="560" height="315" src="https://www.youtube.com/embed/zW6wXmsInU0" frameborder="0"> </iframe>

In the end, I couldn't get the model working by the 1 hour mark.  That's ok, this just gives us another topic to cover next week: Keras RNN 2, Electric Boogaloo.
