---
layout: post
title: Comma.ai Model
cover: none.png
date: 2016-09-27 19:08:22 
categories: posts, stream, keras, data, machine learning, autonomous car
---

I must apologize for the short stream this week.  As I was processing the data, I read it in a 2nd time and used up all available memory.  This ground the computer (and the stream) to a halt.

But, in the 30 minutes of DanDoesData, I created a simple model based on the [comma.ai](https://github.com/commaai/research) data.  Over the weekend, I had fixed up the data shrinking and scaling, but I suspect that I'll have more of that yet to do.  The steering is dominated by a few large turns in the data, with small lane changes at other times.  Or maybe it's just the visualization that I need to change.

<iframe width="560" height="315" src="https://www.youtube.com/embed/axWmemh6Zx0" frameborder="0"> </iframe>

The dataset I compressed will be posted [here](https://drive.google.com/drive/folders/0B0zbVEese408WjYtWGdJWTF0Rjg), hopefully by the time you read this post.  I may cut it down further, or at least remove some of the outlier shots (like the car backing out of a driveway), but it's usable right now.
