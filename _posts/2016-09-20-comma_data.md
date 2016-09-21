---
layout: post
title: Comma.ai data
cover: none.png
date: 2016-09-20 20:33:50 
categories: posts, stream, keras, data, machine learning, autonomous car
---

The race over the weekend went...ok, based on what I heard.  I was unable to attend myself, but I believe Otto got on the track and promptly listed right.  The track was more or less a large right turn, so that's something, right?

This week, I wanted to take a look at a different data set that came out recently, [comma.ai](https://github.com/commaai/research).  This is 7.25 hours of highway driving put out by a startup that wants to add after-market self-driving capabilities to regular cars.  I think that's an ambitious idea, but the way to bring autonomous vehicles to the masses, so why not have a look.

<iframe width="560" height="315" src="https://www.youtube.com/embed/GAYzflie_Vw" frameborder="0"> </iframe>

The [dataset](https://archive.org/download/comma-dataset/) is a full 45 GB, but I only wanted to work with a small subset.  So I picked one of the small image files (3 GB or so) and went with that.  When I have a compressed minimal dataset ready, I'll post that.

The data itself is RGB 160x320 images, and a whole mess of logging information, including the precious speed, acceleration, and steering angle.  The minimal data in question is about 20000 data points, although the first 1000 or so are the vehicle backing out of a garage.

This episode was spent just poking through the data and trying to reformat it.  One catch is that there are 20 images per second, but the logging records 100 times per second.  What's worse is that it's not exactly those numbers, so you can't just take very 5th logging point to tie to the image.  The logging does provide a pointer to the appropriate image for each log point, but it took some mangling to get that in the form I wanted.  Once that was done, it was mostly smooth sailing resizing the image data.  From 3 GB down to about 256 MB.  Not bad.

There still needs to be rescaling of the other parameters.  This should be pretty straightforward, but I know an issue is that most of the driving is straight ahead, with only slight adjustments.  This is reflective of real driving on a highway of course, but Otto will be doing a lot of turning.  

