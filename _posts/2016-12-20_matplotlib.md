---
layout: post
title: Bare Minimum of Matplotlib
cover: none.png
date: 2016-12-20 19:24:46 
categories: posts, stream, python, matplotlib, bare minimum
---

[Matplotlib](http://matplotlib.org) is a great data plotting package you can use interactively via Python.  While I've been using on this stream since day 0 (and long before then professionally), I had never taken the time to walk through the "bare minimum" needed to make it useful.  Thinking there might be other tools and methods needing a small amount of explanation to be really powerful, I started this as a new series.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZthnIfAbKAU" frameborder="0"> </iframe>

In this case, there are two key features of `matplotlib` that every data scientist should know.  The first is how to plot a simple scatter plot.  With a single list, you can plot vs index by doing `plt.plot(foo_list)`.  That covers a surprising number of use cases when you just need to get a quick visual on some data.  For 2-dimensional data, you probably want `plt.plot(x,y,'o')` unless you really care about the order of data points.  The 2nd salient feature is handling heat map, which is a fancy way to say "color a grid based on the value in each box".  So if you've got a pixelated image, that's basically a heat map with 3 color channels.  `matplotlib` makes this easy with `plt.pcolormesh(foo_array)`.  You can change the color settings, show actual images, and do other cool stuff, but I find this handles nearly all situations.  These functions don't cover everything, but they're something that everyone should cover.
