---
layout: post
title: Hark! A Model
cover: none.png
date: 2016-05-31 12:51:59 
categories: posts, stream, keras, data, machine learning, fwtk
---

"For well thou know'st" now has a model.  Not a very deep nor complex model, but a model.  I created a simple logistic regression on the entire 128 by 16 pixels, which gave alternately 60% or 40% accuracy.  I think it was stuck in some local maxima where only a couple glasses were really having their weights adjusted.  Still, it was a start.

<iframe width="560" height="315" src="https://www.youtube.com/embed/REyDGG9uVbk" frameborder="0"> </iframe>

Just for giggles, I decided to upgrade the logistic regression to a simple single hidden layer neural network with 16 neurons.  And I trained for all of 2 epochs.  The result: 97% accuracy on the validation set!  I think the difference is that the optimization space could update all the neuron weights (or enough of time) to capture features of all the font classes.  Not too shabby for a few extra seconds of effort.

Looking more closely at the neuron weights and some example images, I suspect it's just finding how tall and wide some of the text renderings are.  Narrow fonts are centered and rarely reach into the edges, so those pixels have negative weight.  Likewise, tall fonts reach above others, so those pixels should have positive weight for some neurons.  Ultimately, I believe that logistic regression should have been able to do something similar, but kept getting stuck.  Maybe if I prime it with sane starting weights, it will do a decent job.

Because this simple model did so well, I may have to reevaluate the research problem.  Right now, the model is really only keying in on a couple size features, but I really want to learn what features are particular to different types of fonts.  This may mean remaking the dataset to fill up the available image space (so a variable number of characters, even with a constant size image).  Or, I might step away from neural nets and try to build a model with as simple of features as possible.  That is, can I classify these fonts knowing just the overall size of the text area?  Two features, five classes?  Maybe.

