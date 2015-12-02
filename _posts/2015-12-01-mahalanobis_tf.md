---
layout: post
title: Mahalanobis Distance in Tensor Flow
cover: none.png
date: 2015-12-02 18:17:40 
categories: posts, stream, tensor flow, mahalanobis
---

Last night I decided to stray from tutorials and implement [mahalanobis distance](http://en.wikipedia.org/wiki/Mahalanobis_distance) in TensorFlow.  This metric is like standard Euclidean distance, except you account for known correlations among variables in your data set.  My friend over at [Math Misery](http://mathmisery.com/wp) is really into it, so I thought, why not?

tl;dr I did manage to program Mahalanobis Distance (albeit using numpy to invert the covariance matrix) and get the same result as the scipy and pure numpy versions.  I think next week I'll try to do it more purely in TensorFlow and work on optimizing it a bit.

<iframe width="560" height="315" src="https://www.youtube.com/embed/osr6VX1j4kM" frameborder="0"> </iframe>
