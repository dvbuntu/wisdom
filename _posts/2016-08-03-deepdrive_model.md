---
layout: post
title: DeepDrive Model
cover: none.png
date: 2016-07-31 13:56:12 
categories: posts, stream, keras, data, machine learning, autonomous car
---

With the (Blue, Green, Red) issue clarified regarding the DeepDrive data, I was able to start reading in the dataset proper and do some training.  Nothing fancy yet; I just wanted to modify the model enough to accept this type of data.

<iframe width="560" height="315" src="https://www.youtube.com/embed/CdlHNMPFKt4" frameborder="0"> </iframe>

So, the model did something sane, which was good to see.  I only had 1000 samples in this slice of the data, and I didn't bother to train a model that was supposed to be good.  I'm just glad to see that it didn't blow up in my face.

Also, just today I saw a new autonomous car dataset came out from [comma.ai](https://github.com/commaai/research).  This data includes pretty much the same kind of thing as in DeepDrive, but it's 7 hours of actual highway driving in various conditions.  The authors were also kind enough to publish the code and everything for their model.  High fives to them!  I'll definitely be taking a look at their model and this data in a future livestream.
