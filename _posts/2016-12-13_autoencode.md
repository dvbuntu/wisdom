---
layout: post
title: Crashing and Burning with Autoencoders
cover: none.png
date: 2016-12-13 19:35:34 
categories: posts, stream, machine learning, python, autoencoder, keras
---

Sometimes, you crash and burn.  I wanted to take a look at [autoencoders](https://blog.keras.io/building-autoencoders-in-keras.html) this week since that's an area I haven't worked with much.  Things were going fine as I created a simple model with 32 encoded features.  The results were crummy, sure, but it ran alright.

<iframe width="560" height="315" src="https://www.youtube.com/embed/pIrKP4DyH-Q" frameborder="0"> </iframe>

But I wasn't careful about my memory management.  For data, I was using the text images from my [font classification project](https://www.youtube.com/playlist?list=PLFxrZqbLojdIUIAoWuquwlDMkVkJefL0e).  I store the pixels as unsigned bytes, or `np.uint8`'s.  Each image is 16 * 64 = 1024 pixel and so takes up that many bytes.  There are about 500000 images total, so that's more than 500,000,000 bytes, or about half a GB.  No big deal.  Ah, but then I divided by 255 to convert these to floats, no big deal, right?  Wrong, when I did the conversion in NumPy, I didn't specify a datatype, I got `np.float64`, which uses 8 bytes per element.  So now my data is 4 GB.  Still not too bad, until I made two copies of it, one flattened and one with the image dimensions.  My machine nominally has 8 GB of memory, but between this indulgence, streaming, and various programs, everything froze.

Important lesson: be careful about your memory.  Python will hide things from you, but that can make it that much easier to hurt yourself.
