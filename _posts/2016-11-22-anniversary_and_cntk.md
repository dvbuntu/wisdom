---
layout: post
title: TensorFlow and CNTK Revisited
cover: none.png
date: 2016-11-22 20:25:57 
categories: posts, stream, CNTK, tensorflow
---

It's been two weeks since I wrote as I decided to combine that past two streams into one post.  They're both 2nd looks at post libraries to see how far they've come in about a year: [Google TensorFlow](http://www.tensorflow.org) and [MicroSoft CNTK](http://cntk.ai).

The TensorFlow episode was also the 1-year anniversary of Dan Does Data!  Since I had gotten a new hard-drive since then, I actually needed to reinstall TensorFlow anyway, so I took the opportunity to do it live.  Being much more familiar with the process these days (and already have CUDA and other things installed), it was a pretty simple process involving `pip`.

<iframe width="560" height="315" src="https://www.youtube.com/embed/s-5Bk-dQdQw" frameborder="0"> </iframe>

I also took suggestions from the audience on what future videos you'd like to see.  There's more libraries out there to explore, more machine learning techniques to learn about, and of course, a world of applied problems to investigate.  The winner by far was applied problems.  While I've covered font recognition and a self-driving car (and have more to come in that area), which problem to tackle next is still open.  If you have an opinion (or an active problem, with data) drop me a line!

CNTK was due for another look because they updated the library with Python bindings, something I asked for [in the original episode](https://www.youtube.com/watch?v=jAyalvQTTyQ).  Microsoft delivered, so I gave it a whirl.  I was hoping for a painless install and, already having a bunch of other libraries, tried to install it directly by grabbing their archived `whl` file.  That claimed to install correctly but wouldn't import.  After fighting with it for a bit, I gave up and followed their "scripted" install instructions.  These basically download and setup an entire [Anaconda](https://www.continuum.io/downloads) distribution in a special environment.  Especially for just learning a library, this feels like massive overkill.  But I appreciate that they have the option, else I wouldn't have gotten CNTK running at all.

The framework itself feel very similar to [Theano](http://deeplearning.net/software/theano/) or [TensorFlow](http://www.tensorflow.org).  You specify a computation graph of nodes, along with a loss function and input nodes.  Then you set it to train given an optimizer of some kind.  I personally prefer the syntax of TensorFlow to CNTK, but the differences were mainly aesthetic.  Their claim that they're much faster than other libraries is not something I could verify, so take that as you will.

<iframe width="560" height="315" src="https://www.youtube.com/embed/FWZFH9-ainQ" frameborder="0"> </iframe>

If you're just getting started with machine learning, I'd suggest sticking with Theano or TensorFlow at this point.  They seem to have simpler installs (though still not trivial) and more community support.  Better yet, use [Keras](http://keras.io) on top of one of those so you can focus on the fun data science part, and not on coding minutiae!
