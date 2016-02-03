---
layout: post
title: Dreaming of a Convolutional Neural Network
cover: none.png
date: 2016-02-03 13:13:15 
categories: posts, stream, theano, python, neural net, cnn, visualization
---

After spending forever yakking about Convolutional Neural Nets last week, I thought it would be best to complete the "show" part of "show and tell".  So this week I built a simple CNN to predict digit classification, modifying an example at [this excellent tutorial](https://github.com/Newmu/Theano-Tutorials/blob/master/5_convolutional_net.py).  In addition to actually building the dang net, I also made some quick plots of the weights and activations of various layers.

In for a penny, in for a pound.  After whipping up the weight image, I tried to mimic Google's [Deep Dreams](http://googleresearch.blogspot.ch/2015/06/inceptionism-going-deeper-into-neural.html) and let my network imagine what it thinks a '2' looks like.  The results were entertaining if not helpful.

<iframe width="560" height="315" src="https://www.youtube.com/embed/f8KfvpCF70Q" frameborder="0"> </iframe>
