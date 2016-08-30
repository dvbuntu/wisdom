---
layout: post
title: Smaller Models and Regularization
cover: none.png
date: 2016-08-30 19:42:17 
categories: posts, stream, keras, data, machine learning, autonomous car
---

Over the weekend, I made the crucial error of messing with my data.  I had grown tired of having to preprocess it every time I wanted to model something.  And it was irritating that it was split across several files when the raw data size I really wanted could fit in memory.  So I compressed it.

Really, I shrank the data by preprocessing the images down to 64x64 pixels (saving a factor of about 16) and saving only the speed/target information needed, not doubling up.  While I initially had some scaling errors (note to self: only add 1 once :p), it came out great and the model is now much easier to use.  The resulting files are up on Google Drive, [take a look](https://drive.google.com/open?id=0B0zbVEese408WjYtWGdJWTF0Rjg).

Speaking of the model, this week I wanted to tackle the steering model a bit.  Deciding that the previous neural network design was arbitrary, I arbitrarily removed some layers, added regularization, and changed the optimizer.  Fiddling with so many things at once was a mistake.  The model started suffering from insanely bad losses, I have to assume because it was predicting wildly off-base steering results.  We're talking total mean-squared-error in the millions.  Comically bad.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xWuc7w9kco0" frameborder="0"> </iframe>

Watching an animation of the model, I saw that one section of frames was particularly bad.  Bad in that it was an image of the car stuck on another car, trying to turn the wrong way to get out.  I think the in-game AI had trouble in that scene, leading my model to learn garbage.  So I ripped out 250 frames of inputs from the data set.

That wasn't enough though.  It would take dialing down the regularization and moving back to the Adam optimizer to start seeing a "reasonable" steering model.  I didn't have time to fully train on stream, but I suspect it will climb to something ok.

Frustrated with the steering, I turned back to the gas/brake/reverse model.  After a few false starts, I got this running with minimal regularization and was surprised to see that just a few epochs of training produced a halfway decent model.  By this, I mean the training accuracy was 80% and the validation accuracy was 60%.  Not great by any stretch, but this was a big improvement over the "always predict gas" model from before.  With a little more training, this model might be there.

The timeline is coming due, however, for a model to see live action.  Next week we'll have to tackle either training these models simultaneously in a single network, or training 2 models.  The single has the advantage of being less computation overall, but it might not be as accurate for individual features.  Oh well.
