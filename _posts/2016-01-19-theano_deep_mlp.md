---
layout: post
title: Theano Deep MLP for MNIST
cover: none.png
date: 2016-01-21 21:52:47 
categories: posts, stream, theano, python, neural net
---

Finally, some neural net action!  The Theano [tutorial](deeplearning.net/tutorial/mlp.html) guided me in building the basic machinery for neural nets.  I verified their model on MNIST and then generalized it to an arbitrary number of hidden layers.  Does this actually work better?  Who knows, but it's generally useful and now we can bang neural nets against all kinds of problems.  Wee!

<iframe width="560" height="315" src="https://www.youtube.com/embed/e0ziEYlBrJw" frameborder="0"> </iframe>

As a bonus, I got Theano working with my GPU.  Granted, I'm running on a card that was obsolete 4 years ago, but it's an improvement.  If I could get it working with TensorFlow, I might switch back.
