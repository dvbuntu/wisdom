---
layout: post
title: Keras RNN Success
cover: none.png
date: 2016-04-24 03:12:53 
categories: posts, stream, tensorflow, machine learning, keras, theano, rnn, weather
---

It's taken several weeks, but I finally got a simple RNN model working in Keras.  The key was understanding that Keras wanted to work on one sequence at a time, not batch them all up.  So I had to change up my training to iterate through all the sentence, doing one epoch at a time.  Maybe there's a better way, but this finally worked and gave a model that did vaguely the correct thing.

<iframe width="560" height="315" src="https://www.youtube.com/embed/sYXEdXuIEcI" frameborder="0"> </iframe>

After producing a working model for this word embedding problem, I wanted to have something simpler just to get a better grip on RNNs.  So, I generated some fake sinusoidal temperature data and quickly grabbed some rainfall information off the web.  I was able to use this to build a model to predict the season based on daily values of these (and history via the RNN).  Doing this hacky thing doesn't work too well, but keep your eye out to if I revisit this type of data again.
