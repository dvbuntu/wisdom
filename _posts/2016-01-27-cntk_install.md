---
layout: post
title: Microsoft CNTK Installation
cover: none.png
date: 2016-01-27 20:48:49 
categories: posts, stream, cntk, neural net
---

Fortuitously, Microsoft released their own machine learning library this week, [CNTK](https://github.com/Microsoft/CNTK).  Unlike TensorFlow, Theano, and other popular frameworks, CNTK doesn't yet support Python or C++ bindings.  So far, it looks like it only has configuration files and an `ndl` file format for specifying nets.  I streamed trying to install it and do the simplest computation

<iframe width="560" height="315" src="https://www.youtube.com/embed/jAyalvQTTyQ" frameborder="0"> </iframe>

Since I tried to do this the day it was released, you shouldn't be suprised that there were issues.  I was little irked that although they supported Linux, they didn't have a binary already compiled.  And trying to compiling it myself quickly led to dependency hell.  Thankfully, I found an old binary on their [codeplex page](https://cntk.codeplex.com/releases).  While it was a CPU-only version, it allowed me to start playing with the language.
