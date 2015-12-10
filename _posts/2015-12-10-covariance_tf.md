---
layout: post
title: Mahalanobis Distance in Tensor Flow Part 2
cover: none.png
date: 2015-12-10 02:16:47 
categories: posts, stream, tensor flow, mahalanobis, covariance
---

This week, I improved my implementation of Mahalanobis distance a bit.  Where previously I was still using Numpy to compute the inverse of the covariance matrix, I thought it would be fun to do that in TensorFlow itself.  Conveniently, TF has a function for inverting a matrix.

What TF lacks, or I didn't find, is a function to compute the covariance between variables on a data set.  So I also sought to implement that.  After quickly whipping up a version in NumPy, I started translating to TF.  You'll have to watch to see how far I got.

<iframe width="560" height="315" src="https://www.youtube.com/embed/wjsA72oUpEg" frameborder="0"> </iframe>

Next week I'll continue looking at the Mahalanobis distance implementation, as well as given some general thoughts on TensorFlow.  While I'm still new to the library, I can now say that I've worked through a few tutorials and a small project of my own.  I was initially kind of turned off by the style of TF, but I think I'm warming up to it.

Starting next year, I will stream similar sessions for [Theano](http://deeplearning.net/software/theano/), another "deep learning" framework for Python.  This one doesn't have the backing of Google, but it is open source and has a strong community.  While I've fiddled with it once or twice, I'll be starting from scratch with the installation, so everyone can see me screw up right away.
