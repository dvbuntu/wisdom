---
layout: post
title: Keras Introduction
cover: none.png
date: 2016-03-24 20:16:27 
categories: posts, stream, tensorflow, machine learning, keras, theano
---

It's time for a whole new library, [Keras](keras.io)!  This is actually another high level wrapping langauge, similar to skflow.  It was originally built on top of Theano, but now it works with *both* Theano and TensorFlow.  The interface isn't as simple as skflow's one line deep neural network, but it still makes common things easy.  Oh!  And it has beautiful progress bars while going through training.  So soothing.

<iframe width="560" height="315" src="https://www.youtube.com/embed/L0IVu_sKOOY" frameborder="0"> </iframe>

The basic construction in Keras is the `model` built of *layers*.  After creating an empty model, you can add densely connected layers (and then their activation functions, like sigmoids), convolutional layers, or whatever.  Then you tie it up with your output layer, typically `softmax` for classification.  To actually train the model, you pick one of the many optimizers, set a couple parameters, and crank through your data.

The one downside is that it's not clear how to add custom components.  skflow included examples with custom convolutional layers, and eventually I figured out how to access its weights.  But Keras is still opaque; I think I can hack in some custom activation functions, but it won't be trivial.

