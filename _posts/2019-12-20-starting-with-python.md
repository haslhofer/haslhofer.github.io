---
layout: post
title:  "Starting data science with Python and Visual Studio Code to work with BERT"
author: gerald
categories: [ ml, python]
tags: 
image: assets/images/landscape3.jpg
---

Reproducing BERT training for text classification
---

Step 1: Setup
---

**Tutorial**
[Introduction](https://code.visualstudio.com/docs/languages/python) to Visual Studio Code and Python

**Downloads**

* Visual Studio Code [download](https://code.visualstudio.com/Download)
* Python [installer](https://www.python.org/ftp/python/3.8.1/python-3.8.1.exe) for Python 3.8.1. Make sure that environment variables are set
* Also tried Anaconda distribution https://www.anaconda.com/distribution/#windows
* Create directory, start Visual Studio Code (```cd dir; code .```)
* Select environment: CTRL+SHIFT+P,  "Python: Select Interpreter"
* Create a terminal window: CTRL+SHIFT+P, "Terminal: Create New Integrated Terminal"
* Install tensorflow GPU (with Conda). New Command Window. ```conda install tensorflow-gpu```  (Conda is preinstalled)

Step 2: Follow tutorial
---

* Tutorial 1: https://towardsml.com/2019/09/17/bert-explained-a-complete-guide-with-theory-and-tutorial/
* Tutorial 2: Intent classification https://towardsdatascience.com/bert-for-dummies-step-by-step-tutorial-fb90890ffe03. Our choice.

Make sure the GPU works for tensorflow

```
# verify GPU availability
import tensorflow as tf

device_name = tf.test.gpu_device_name()
if device_name != '/device:GPU:0':
  raise SystemError('GPU device not found')
print('Found GPU at: {}'.format(device_name))
```