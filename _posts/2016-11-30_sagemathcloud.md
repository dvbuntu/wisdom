---
layout: post
title: Jupyter and SageMathCloud
cover: none.png
date: 2016-11-30 17:29:46 
categories: posts, stream, sage, sagemathcloud, jupyter, python
---

Long ago, I mentioned how to [install TensorFlow on SageMathCloud]({{ site.baseurl }}/2016/01/14/tf_sagemath/).  Today, I decided to give [SageMathCloud](cloud.sagemath.com) a proper stream.  It's a good thing I did, because it's gotten a lot better in the past year.

<iframe width="560" height="315" src="https://www.youtube.com/embed/tZ5DRWTk7ak" frameborder="0"> </iframe>

SageMathCloud has been a convenient way to use IPython Notebooks with a lot of prebuilt computing tools for awhile now.  But recently, they've upped their game on machine learning libraries that come pre-installed.  You no longer need a hacky workaround to install TensorFlow, it comes free!  Prefer Theano?  No problemo; it's got that too.  It even has a version of Keras so you can get going quickly.  This is all in addition to the solid NumPy/SciPy/Matplotlib support.  It's a great platform.

I have only a couple complaints.  First, it doesn't play nice with Firefox anymore (maybe it never did?).  So you'll have to install Chrom[ium] or IE or something to use it.  Not a big deal.  Also, whiel it does have several machine learning libraries, the versions are a bit dated.  This might be based on the Anaconda version they're running, but it was a bummer to see Keras at version 1.1.2 on [PyPi](https://pypi.python.org/pypi/Keras) but only find version 0.3.2 on SageMathCloud.  Not a big deal, but a number of things have changed since then.  Chasing versions, however, I know would be a Sissyphean task given the pace of these libraries.  Maybe I'll just have to live with it.
