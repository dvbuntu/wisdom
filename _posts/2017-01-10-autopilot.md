---
layout: post
title: Nvidia Autopilot Model
cover: none.png
date: 2017-01-10 19:27:47 
categories: posts, stream, python, self-driving car, keras, nvidia
---

Happy New Year!  We're back with a brand new model, same old data.  Nvidia posted a model of their [End to End Learning for Self-driving Cars](https://arxiv.org/pdf/1604.07316.pdf) last year, and I sought to recreate it in Keras.  The paper is a pretty easy read and the model isn't too complicated.  The biggest trip ups for me were that their convolutional layers, rather than having a stride of 1 and doing max-pooling with stride 2 (so computing 4 things and then taking the "strongest"), they just have a convolution with a stride of 2 (so always taking the top left box in a 2x2 grid, basically).  But this was pretty easy to do in Keras.  The output function, as I noted based on [SullyChen's Tensorflow implementation](https://github.com/SullyChen/Autopilot-TensorFlow/blob/master/model.py) was an arctangentfunction.  Graphically, this is similar to hyperbolic tangent, so I just used that (`tanh` is part of vanilla Keras while `atan` isn't).  Doing custom activations isn't hard, but that wasn't the purpose of this stream.

<iframe width="560" height="315" src="https://www.youtube.com/embed/1nuu5P3voB8" frameborder="0"> </iframe>

The results came out pretty well.  At very least, it matched similar "large" models I had created earlier.  One thing to note is that I used my compressed dataset from [DeepDrive](deepdrive.io), so my images are smaller and I have fewer interior values to flatten and pass to the first dense layer.  Ultimately, this model suffers from the same issue as my previous models: it doesn't stray much from driving straight.  Not that this behavior is inherenty wrong; it does go left and right, just not as much as I might have expected.  But hey, 90% of driving is going straight, ya?

