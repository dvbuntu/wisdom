---
layout: post
title: Autonomous Car Model
cover: none.png
date: 2016-07-25 12:58:51 
categories: posts, stream, keras, data, machine learning, autonomous car
---

As a one-time civil engineer, self-driving cars hold a place in my heart.  As a commuter, I also hunger for the freedom that they will create.  Not only the freedom to nap on my way to and from work, but the freedom to stop owning a car, the freedom for the elderly and disabled to get wherever they want to go, and the freedom from reptilian side of my brain when it comes to parking.  So I'm excited to be working on a [Powerwheels Racing](http://www.powerracingseries.org/) autonomous car with [FUBAR Labs](fubarlabs.org).  

<iframe width="560" height="315" src="https://www.youtube.com/embed/meU1fXXIAOQ" frameborder="0"> </iframe>

This video just plans out the model inputs/outputs and slaps together some skeleton code.  I think we have the basics of a decent model with the following inputs at time `t-1`:

* Acceleration/Braking
* Speed
* Distance to object in front
* Steering wheel angle
* Webcam front view

We can combine all these inputs into a neural net (or just a linear model) using a graph model.  The webcam images we will probably put through a few convolutional layers first, and then dump everything into some densely connected layers.  Once we get down to some true core features, we extract our desired outputs at time `t`, namely:

* Gas pedal/braking
* Steering wheel angle

The hard part will be getting a good data set for this.  Most data I've seen aimed at self-driving cars is trying really hard to do object detection with LIDAR and other fancy methods.  I'm just looking for something with these simple parameters.  And this isn't even worrying about the specific scenario of Powerwheels racing, which is more like go-karts than real cars.  As with all models, it's never what you initially imagine, but you always have something.

