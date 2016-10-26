---
layout: post
title: Autonomous Car Data Collection Platform
cover: none.png
date: 2016-10-26 18:19:52 
categories: posts, stream, keras, data, machine learning, autonomous car, data collection
---

Previously, I've used data from [existing](http://deepdrive.io) [sources](https://github.com/commaai/research) to train our autonomous tractor.  This was convenient since it allowed me to get familiar with what variables would be important to me and to get something going just as our vehicle was physically coming together.

But the differences in physics and simulated nature of some of the data never exactly fit right for Otto.  The difference in top speed and turning radius alone would muck things up.  While machine learning is powerful and can often fill in gaps in human understanding, this is a case where it makes more sense to collect our own data.  Proper experimental design can drastically reduce the need for intensive computation.  This is one step in that direction.

<iframe width="560" height="315" src="https://www.youtube.com/embed/dHu5koYZe2U" frameborder="0"> </iframe>

The overall design of this data collection is pretty simple.  Every iteration, the webcam on Otto will snap a picture, then we receive the current information (speed, acceleration, steering angle, gas, etc) from the FUBARino board, followed by a little processing.  Every N steps, we save it off to a file and start a new chunk.

During the stream itself, `obs` had control of my webcam (to stream my face to viewers), so I couldn't test that part of the problem.  And perhaps more concerning, we haven't nailed down what information will actually be sent from the FUBARino in what format.  So this code remains a skeleton for now.  But it's better to have [this skeleton](https://github.com/dvbuntu/autonomous/blob/master/collect.py) than nothing at all.


I believe I have a simple RNN working with just a single frame of lookback.  At least, based on the number of parameters, I think that's what must be happening.  It's always a little hard to tell if I'm loading the data correctly for these kinds of models.

I also learned about [TimeDistributed](https://keras.io/layers/core/#timedistributeddense) layers, which can ease some of the burden of implementing more complex RNNs by handling the multiple inputs to each time.  This would have been useful when doing [Font Recognition](https://www.youtube.com/watch?v=wSpPJtenw_c), but at least doing it "manually", I understood exactly what was happening.  Tradeoffs of using libraries.

