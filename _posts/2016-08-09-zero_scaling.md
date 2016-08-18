---
layout: post
title: Zero Scaling
cover: none.png
date: 2016-08-09 19:35:56 
categories: posts, stream, keras, data, machine learning, autonomous car
---

While my transition from ArchLinux to Ubuntu went smoothly, I can't say the same for the self-driving car model.  I discovered that it was always predicting the same values no matter the inputs!  In this video, I suspected that the problem was unscaled inputs, but fixing that didn't resolve the problem.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PeoFPAr084s" frameborder="0"> </iframe>

Now I'm thinking that it may be the activations.  I was using Rectified Linear for the convolutional layers.  It could be that negative values are driving all my gradients to zero.  In the [DeepDrive](http://deepdrive.io) model, Craig uses ReLU as well, but the [CommaAI](https://github.com/commaai/research/blob/master/train_steering_model.py) model uses "ELU" or exponential linear unit.  Basically ELU is like ReLU but "leaks" a little when the input is below zero, and it does so in a nonlinear fashion.  This might solve my gradient problem.
