---
layout: post
title: Autonomous Car Model Review
cover: none.png
date: 2016-10-11 20:53:57 
categories: posts, stream, keras, data, machine learning, autonomous car
---

I didn't have have much specifically planned for this week, so I ended up reviewing some work I did over the weekend.  This was a mixup of transfer learning, rebuilding other models in Keras, and processing more data.

<iframe width="560" height="315" src="https://www.youtube.com/embed/vHSbSqYVH3E" frameborder="0"> </iframe>

As mentioned before, the SqueezeNet transfer learning wasn't paying off, so I moved on to replicating the results of DeepDrive in Keras.  Craig from DeepDrive was kind enough to share his model weights in a [binary format](https://drive.google.com/drive/folders/0B2UgaM91sqeAUkExb0FLR05sT1E).  I worked out how to map them to a Keras AlexNet-based model with a little reshaping.  But, the model seems to list to the left.  It might be that Caffe has some features we don't know about in how it implements AlexNet, or that I've got the color channels screwed up.  Either way, I wasn't having great luck with this on the first 100 samples of the DeepDrive data.  But it does work in Caffe, so there must be something here.

Getting frustrated, I turned back to my own models.  The 0.03 MSE left a lot of room for improvement, so I looked around for inspiration.  Nvidia recently released a TensorFlow [implementation](https://github.com/SullyChen/Nvidia-Autopilot-TensorFlow) of one of their models, and it had a relatively reasonable number of parameters.  I didn't want to just copy it, but I did try 5 convolutional layers with an increasing number of kernels in each layer.  With a modest amount of training, this started to perform decently, with about 0.01 MSE.  Finally, a win.

This comes with a caveat, however, that I also processed some more DeepDrive data, about doubling the amount available.  I strongly suspect this new data is a little more well-behaved generally, so that might color the effectiveness of this model.

What's worse, during stream I discovered a typo in this "good model".  Turns out I was using 1 less convolutional layer than I thought!  Fixing that and rerunning, I get a new model that's a little more effective still.  It pays to double check for easy to make and fix mistakes.
