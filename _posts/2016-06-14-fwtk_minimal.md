---
layout: post
title: Rewriting the Script
cover: none.png
date: 2016-06-14 11:28:34 
categories: posts, stream, keras, data, machine learning, fwtk
---

Further investigation into the data set of "For well thou know'st" revealed that using just the overall width and height of space taken up by the font accounted for most of the predictive power.

<iframe width="560" height="315" src="https://www.youtube.com/embed/g5oGFGCPrtU" frameborder="0"> </iframe>

This is really an artifact of how I created the data, so I don't think it's fair to model that way.  To solve this, I remade the data set using a variable number of characters for each font.  Instead of always using 16 characters, now I use as many as necessary to fill up 64 pixels wide (which is half the size of the previous data), up to 32 characters.  Because I had been careful about creating and reading in my data in the first place, this didn't take long at all.

<iframe width="560" height="315" src="https://www.youtube.com/embed/sT-2sj1fYlU" frameborder="0"> </iframe>

