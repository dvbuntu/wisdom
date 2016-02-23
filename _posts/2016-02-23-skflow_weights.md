---
layout: post
title: TensorFlow and skflow weight recovery
cover: none.png
date: 2016-02-23 13:15:34 
categories: posts, stream, tensorflow, machine learning, skflow
---

In addition to supporting a handful of built-in models, [skflow](github.com/tensorflow/skflow) allows you to supply a custom graph, typically capped off with one of the common models (like a fully connected layer).  The [example](https://github.com/tensorflow/skflow/blob/master/examples/mnist.py) shows how this actually works with a convolutional neural net.  There's just one problem: weights are no longer accessible.  I struggled through this in the first video last week.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ACSyNjZyD1U" frameborder="0"> </iframe>

But perseverance paid off!  This week I studied the log file normally used for TensorBoard.  Running strings on that file, I extracted the necessary incantation to access all of the weights.  And I submitted a [Pull Request](https://github.com/tensorflow/skflow/pull/111) to show other users how this is done.

```python
classifier.get_tensor_value('conv_layer1/convolution/filters:0')
```

Here's the triumph in action:

<iframe width="560" height="315" src="https://www.youtube.com/embed/TCsPeXL8g0w" frameborder="0"> </iframe>
