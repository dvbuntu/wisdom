---
layout: post
title: Crop Disease Mode
cover: none.png
date: 2017-01-17 20:13:30 
categories: posts, stream, python, crop disease, keras
---

This special episode of DanDoesData takes a look at a [Crop Disease Identification Problem](https://www.crowdai.org/challenges/plantvillage-disease-classification-challenge).  It's special because it's sponsored by [GrowMobile,LLC](https://www.facebook.com/growmobilellc/)/[NerdFarmer](http://nerdfarmer.com/).  This is only a quick stream, not a formal report, so thanks to these folks for donating to [FUBAR Labs](fubarlabs.org).

<iframe width="560" height="315" src="https://www.youtube.com/embed/HZdCeptyl5I" frameborder="0"> </iframe>

Anyway, this data is about 20k images of leaves.  There are 38 different classes showcasing different diseases.  The goal is to train a classifier to recognize the disease based on a single image.  Sounds easy, right?  There's a few complications.  The images are all different sizes.  One dimension is always 256 pixels, but the other varies from 256 up to about 516.  To handle this, I decided to cut the center out of the long dimension to square things up.  This may cut out interesting data, but for a first pass, hopefully it's ok.  An alternative would be to inflate the smaller dimension with empty data.  You can then resize them all to standard dimensions, here 224x224.  Once you deal with that, you'll also notice that the photos are all taken at different angles and rotations.  Oh well; hopefully that doesn't impact too much of the disease markings, but it also means that generating more data by rotating images might be particularly useful.  Always little issues coming up.

The model itsef I whipped up pretty quick. 5 layers of convolutions with max pooling followed by a few dense layers and the final softmax to predict 38 probabilities.  After training for 1 epoch (15 minutes), the final accuracy was about 15%.  Pretty crummy but better than random.  And this was just a first pass model to get the process down.  For production use, one should study what others have done, fine tune a model with more (or fewer!) layers, and train for a while.  It's not so different from a certain [Font Recognition problem](https://www.youtube.com/playlist?list=PLFxrZqbLojdIUIAoWuquwlDMkVkJefL0e).

