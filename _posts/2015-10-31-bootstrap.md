---
layout: post
title: Pulling Yourself Down by the Bootstraps
cover: none.png
date: 2015-10-31 05:40:54 
categories: posts, critique, econometric, bootstrap
---

"Bootstrapping" is an attempt to get more out of less data.  In a serious statistical model, you split your data into training and validation sets.  Essentially, you build a model with the training set, then you "check your work" with the validation set.  If your model performs equally well on the validation set as the training set, then you have some confidence that the model didn't "overtrain" (memorize) the data.  Bootstrapping cranks this process up to 11.

In an ideal world, you have plenty of data to afford setting some aside for validation, but back in the real world, you take what you can get.  Bootstrapping says, "Not enough data?  No problem.  Train on a random subset of the data.  In fact, train on a bunch of different random subsets.  Rinse and repeat."  By picking many different subsets and averaging, you hope to avoid overtraining on any one particular set.

The paper we're exploring today tried to use bootstrapping but never quite justified it.  [Here's](https://drive.google.com/file/d/0B0zbVEese408UFZhdG9OZk04LVE/view?usp=sharing) a pre-print of the article ([raw tex file]({{ site.baseurl }}/resources/bootstrap/vanboxel2008ese_trb.tex)).  Briefly, this study models crash counts on sections of roadway by building a "Negative Binomial" (a fancy Least Squares for predicting counts rather than rational numbers) model using roadway features as independent variables.  The crux of the study, however, is the "Mean Absolute Error" (MAE) of a given model, basically how wrong it is.  The authors claim that by bootstrapping their model building, they get lower MAEs than simply simply building one big model (Figure 3).  This preprint leaves out some details, but this point comes out strongly.

This study fails, however, because it doesn't address the problems bootstrapping may introduce.  The whole point of holding data back in a validation set is to avoid overtraining.  But in bootstrapping, you repeatedly use data points multiple times to build one model.  Now, it may be that this violation of independence between bootstrap iterations is insignificant.  But that needs to be stated and supported in the article.

Confession time: This is one of my earliest scholarly works.  Back in summer 2008, we didn't have the time to understand and qualify bootstrapping's limitations.  So we scrapped the paper.  Thankfully, we were able to reuse the Negative Binomial model in [another paper](http://trrjournalonline.trb.org/doi/abs/10.3141/2096-06).  But in a more sleep-deprived or results desperate environment, someone might have ignored the omission and published anyway.

