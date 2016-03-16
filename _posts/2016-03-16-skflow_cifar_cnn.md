---
layout: post
title: CIFAR10 in skflow with a Convolutional Net
cover: none.png
date: 2016-03-16 10:37:27 
categories: posts, stream, tensorflow, machine learning, skflow, cifar10
---

After spending most of last video figuring out how to properly import the data for CIFAR10 image recognition, this time I blitzed through the modeling and visualization.  You can download the binary data yourself from [Alex Krizhevsky](https://www.cs.toronto.edu/~kriz/cifar-10-binary.tar.gz).  Once you do that and read it in with `np.fromfile('/path/to/extracted/data/bin')`, it's pretty easy to manipulate and use with `skflow`.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UGldPm4RRww" frameborder="0"> </iframe>

This video also made good use of pulling out the weights from skflow as discovered previously.  In fact, it was nice to look at the first layer weights by properly coloring them red, green, or blue according to the channel.

In this case, I was only using 1/5 of the data anyway (forgot to read all the globs), but it still demonstrates how to setup and run the model with skflow.  I really appreciate how easy skflow makes setting up a typical neural net.  If only extracting the weights were a little more natural.  Maybe that's a future pull request.

