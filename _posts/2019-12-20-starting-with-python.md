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

Step 0: Understand what BERT is
---

See https://haslhofer.github.io/nlp-introduction/, section "Transformers".


Step 1: Setup on Surface Book (which has GPU)
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

Conda and Pip coexistence: 
https://www.anaconda.com/using-pip-in-a-conda-environment/

* Create new environment with Conda so you control the right version of e.g. Tensorflow (Bert-as-a-service does not work with Tensorflow 2.0)

``` 
conda create environname
conda activate environname

```

Make sure the GPU works for tensorflow

```
# verify GPU availability
import tensorflow as tf

device_name = tf.test.gpu_device_name()
if device_name != '/device:GPU:0':
  raise SystemError('GPU device not found')
print('Found GPU at: {}'.format(device_name))
```


Step 2: Choose tutorial to get started
---

Potential tutorials, ultimately chose Bert-as-a-service as it allowed the most straightforward experiments
* Tutorial 1: https://towardsml.com/2019/09/17/bert-explained-a-complete-guide-with-theory-and-tutorial/
* Tutorial 2: Intent classification https://towardsdatascience.com/bert-for-dummies-step-by-step-tutorial-fb90890ffe03
* Tutorial 3: https://github.com/huggingface/transformers
* Tutorial 4: https://towardsml.com/2019/09/17/bert-explained-a-complete-guide-with-theory-and-tutorial/
* Tutorial 5: http://mccormickml.com/2019/05/14/BERT-word-embeddings-tutorial/
* Tutorial 6: https://github.com/hanxiao/bert-as-service Our choice.

Step 3: set up Bert-as-a-service
---

https://github.com/hanxiao/bert-as-service

``` 
pip install bert-serving-server  # server
pip install bert-serving-client  # client, independent of `bert-serving-server`
``` 

Download BERT model from Google. 

https://storage.googleapis.com/bert_models/2018_10_18/uncased_L-12_H-768_A-12.zip

 and extracted it to 
 ```
 C:\Users\gerhas\code\python\uncased_L-12_H-768_A-12
```

Start the BERT server component
```
bert-serving-start -model_dir c:\users\gerhas\code\python\uncased_L-12_H-768_A-12 -num_worker=4
```


Other notes
---

Bert-as-service exploration
---

