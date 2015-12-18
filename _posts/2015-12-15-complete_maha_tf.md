---
layout: post
title: Mahalanobis Distance in Tensor Flow Part 3
cover: none.png
date: 2015-12-17 19:48:59 
categories: posts, stream, tensor flow, mahalanobis
---

Finally, after numerous screwups, I completed my full TensorFlow implementation of the Mahalanobis distance.  This video also reveals the first instance of my portable markerboard; hopefully my handwriting isn't too much of a scrawl.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9NfkvrMT_il" frameborder="0"> </iframe>

The function I implemented takes in a given data set and spits out the mahalanobis distance of every point to the mean.  This is an interesting proof-of-concept as this kind of operation occurs in k-means clustering (with whatever distance metric).  There, however, you would probably use the global covariance matrix, but the mean for the given cluster.  I might take a stab at his next week

The implementation makes full use of matrix computations, avoiding clunky `for` loops whenever possible.  If you know a better way to extract the diagonal of a matrix in TensorFlow than this `tf.pack` method, I'd love to hear it.  A series of matrix multiplies and adds should bev doable, but it might not be any better.  Still, it'd be good to see an alternate design.
