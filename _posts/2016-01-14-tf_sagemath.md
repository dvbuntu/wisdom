---
layout: post
title: TensorFlow in SageMathCloud
cover: none.png
date:  2016-01-14 21:23:00
categories: posts, python, sagemathcloud, tensorflow
---

# Installing TensorFlow in SageMathCloud
TensorFlow isn't always the most friendly library to install, but within [SageMathCloud](cloud.sagemath.com) for a CPU-only version and Python3.4, it's not too bad.  Most of the pain comes from SageMathCloud cutting off our network access.

First, download the TensorFlow wheel file.  Do this on your local computer, not SageMathCloud.

```bash
# Use wget from the command line, or search the tensorflow website under "Get Started"
wget https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.6.0-cp34-none-linux_x86_64.whl
``` 

Next, open a terminal in your SageMathCloud.  We'll use `pip3` to install TensorFlow like you might a normal Python package, but we'll pass in some options so that `pip3` doesn't try to download unneeded dependencies.

```bash
pip3 install --user --no-index --no-deps tensorflow-0.6.0-cp34-none-linux_x86_64.whl
```

That's it!  TensorFlow is now ready to use in a Python3 kernel under a Jupyter Notebook.
