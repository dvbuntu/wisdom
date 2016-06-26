---
layout: post
title: Jittered Model
cover: none.png
date: 2016-06-26 04:20:58 
categories: posts, stream, keras, data, machine learning, fwtk
---

What I didn't mention last week was that I tried some simple models with the rebuilt data...and they still were way too accurate to be believable.  Even filling up the horizontal space left the vertical space for models to cheat with.  To get around this, I remembered a common technique when dealing with image data: jitter it.  That is, for any given image, shift it around a few pixels and use that image as well.

Doing this yields a much more reasonable model with a typical multilayer perceptron type model.  The accuracy was still well above random guessing, but it wasn't perfect either.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Mj5tL45b_0s" frameborder="0"> </iframe>

I also tried a convolutional neural net model on this data.  As expected, this performed very well, getting nearly 100% accuracy.  Fonts have lots of clues that give away their identity at the small scale.

One thing I still want to try is looking at a small slice of the image, say 8 pixels wide.  Then I'll run a small net on this to develop some confidence about the overall nature of the class.  Moving onto the next slice, we'll remember some state and do it over again.  This should be faster to train (fewer weights) and works on variable length data.
