---
layout: post
title: Keras Line by Line Scikit-learn GridSearch
cover: none.png
date: 2017-05-04 19:34:55 
categories: posts, stream, python, keras, linebyline, 
---

I felt like the Project Euler videos weren't as interesting as I hope (and they were topics well covered by others already), so by request I'm doing another [Line by Line](http://goo.gl/d3wzh2) series.  This time, we're looking at various [Keras examples](https://github.com/fchollet/keras/tree/master/examples).  Specifically, I decided to check out [`sklearn` GridSearch Example](https://github.com/fchollet/keras/tree/master/examples/mnist_sklearn_wrapper.py).  GridSearch is really just an exhaustion over possible hyperparameters you declare in a dictionary.  This is neat if you have a limited number of varied models to try and don't mind waiting:

<iframe width="560" height="315" src="https://www.youtube.com/embed/6RdflAr66-e" frameborder="0"> </iframe>

While I didn't have a prior familiarity with `sklearn`'s GridSearch, the Keras example was a gentle introduction to the process.  While I probably won't be using this specific SciKit-Learn tool, it's great that the ability is built-in to Keras.  Finding the right specific model is a frustration of mine, so I'm looking forward to deploying some of these tools for Keras models.
