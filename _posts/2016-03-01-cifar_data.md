---
layout: post
title: Reading CIFAR10 in TensorFlow and skflow
cover: none.png
date: 2016-03-02 11:38:40 
categories: posts, stream, tensorflow, machine learning, skflow, CIFAR10
---

This week we started looking at a new dataset (no more MNIST, rejoice!), the CIFAR10 image recognition dataset.  Well, "looking" might be a strong verb.  I wanted to build a simple CNN to try this in skflow.  There's a TensorFlow tutorial on this benchmark, but they develop a custom method of actually reading in the data.  So it took me a while to decipher what they were doing before I could just read the images into my own simple numpy array.  But I got it eventually and built a basic logistic regression classifier (not very good, but shows that the setup works).  Next time (March 15 as I'm off next week), we'll be at it in full force.

<iframe width="560" height="315" src="https://www.youtube.com/embed/FM5czI9iWvA" frameborder="0"> </iframe>

