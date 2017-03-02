---
layout: post
title: Bardic Lore Data Prep
cover: none.png
date: 2017-03-01 18:54:37 
categories: posts, stream, python, keras, bardiclore
---

This video kicks off a new series, "Bardic Lore".  You may have heard of the power of Recurrent Neural Networks to [generate human-like text](https://us-amazon.icims.com/jobs/432808/machine-learning-scientist---machine-translation/login).  While this takes quite a bit of training, I wanted to implement a modest version of this to learn and demonstrate the details.  There's various existing implementations emulating different authors, but I grok it best when I build it myself.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xQlhFj2NcEM" frameborder="0"> </iframe>

So far, we got the data preparation started and worked through the simplest possible example.  The data I'm using is the same Shakespeare corpus I used to [model fonts](https://www.youtube.com/playlist?list=PLFxrZqbLojdIUIAoWuquwlDMkVkJefL0e), only now instead of turning it into pictures, we're actually using the text itself.  To simplify the data, I lowercased everything and removed a handful of exraneous punctuation; I assure you the Bard is kept intact using just 34 unique characters.  The template I followed to get started is conveniently enough [in the Keras documentation](https://github.com/fchollet/keras/blob/master/examples/lstm_text_generation.py).  This is only a starter, but it shows how to do the simple thing: convert all your data to 1-hot format and shove it into a model.  Adding more layers or tweaking the type shouldn't alter our framework too much.

I have trained the model briefing; it's about 30 min/epoch, so it takes awhile.  But it's still stuck on outputting spaces for the moment. Once I have something vaguely respectable (not great but not total junk), I'll post a github repo.
