---
layout: post
title: DeepDrive Data
cover: none.png
date: 2016-07-31 13:56:12 
categories: posts, stream, keras, data, machine learning, autonomous car
---

Tipped off a good friend from FUBAR, I found a reasonable data set to train a self-driving car.  [DeepDrive](deepdrive.io) is full video and information of a vehicle taken from the video game, Grand Theft Auto V.  This includes the speed, delta speed, accelerator, and other key data points in addition to the frame of the graphics at that time.  This is everything I wanted except for the rangefinder, and that wasn't required anyway.

<iframe width="560" height="315" src="https://www.youtube.com/embed/6bSAXvN4uos" frameborder="0"> </iframe>

As DeepDrive is run by a single awesome guy, it's not as fully described as it could be.  Most of the data is self-explanatory, but I spent a good portion of this video figuring out the image format.  I'm most used to Red, Green, Blue formats, but that never quite gave me the expected results.  I could get close by inverting the color, but it still looked off.

Thankfully, Craig from DeepDrive heard my plight.  He told me that Caffe, the ML library he was using, expect images in Blue, Green, Red format!  Fixing this gives realistic-looking images when plotted normally.

This episode didn't really feature much machine learning, but that's ok.  This is "Dan Does Data" because understanding one's data is key to any modeling problem.  Often, sifting through the data itself takes more time than coding a model, especially given modern libraries.  But it's still important to *look at the data*.
