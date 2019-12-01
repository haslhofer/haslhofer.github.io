---
layout: post
title:  "Natural language processing - Introduction"
author: gerald
categories: [ ml, nlp ]
image: assets/images/landscape7.jpg
---

Natural language processing - introduction  and state-of-the-art
---

**NLP - Basics**
* Overview / [ImageNet moment in NLP](https://ruder.io/nlp-imagenet/)

* *Embeddings*: 
First step often is turning input words into vectors using embeddings (see. e.g. [here](https://machinelearningmastery.com/what-are-word-embeddings/) for an explanation of word embeddings). These vectos capture some semantics (king-man+woman=queen). These vectors are somewhere in the 200-300 dimensions range. Embedding explanation with Word2Vec focus on [medium](https://medium.com/deeper-learning/glossary-of-deep-learning-word-embedding-f90c3cec34ca)
* Video about using sentence embedding [for fact checking](https://www.youtube.com/watch?v=ddf0lgPCoSo)

* *Attention* [overview](https://jalammar.github.io/visualizing-neural-machine-translation-mechanics-of-seq2seq-models-with-attention/) and original paper ["Attention is all you need"](https://arxiv.org/pdf/1706.03762.pdf). Basic premise is that enabling the neural network to pay attention to a specific subset of hidden states leads to better results.

* Basics - *Transformer* Great high level [overview](http://jalammar.github.io/illustrated-transformer/). Originally intorduced in ["Attention is all you need"](https://arxiv.org/pdf/1706.03762.pdf).  
Fully annotated code to the paper from Harvard NLP group is [here](http://nlp.seas.harvard.edu/2018/04/03/attention.html).  
And [Tensorflow library tensor2tensor](https://github.com/tensorflow/tensor2tensor). Interactive tensor2tensor on [Google Colab](https://colab.research.google.com/github/tensorflow/tensor2tensor/blob/master/tensor2tensor/notebooks/hello_t2t.ipynb).   
Hugging Face Transformer [quick tutorial](https://github.com/huggingface/transformers)  
Transformer [introduction](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html) from Google
* Introductory article for [Hugging Face](https://blog.tensorflow.org/2019/11/hugging-face-state-of-art-natural.html?m=1) NLP library 

**BERT et.al.**  
Basic premise: semi-supervised training on large amounts of text to build model. Then supervised training with specific labeled data set. Key concepts applied: semi-supervised sequence learning; Transformers; ELMo (tbd), ULMFiT (tbd)   
Simplest model: train a binary classifier with (1) BERT --> (2) Feed-forward neural network + softmax. 
BERT model is modified only slightly during the training phase.  
* [BERT original paper](https://arxiv.org/pdf/1810.04805.pdf)
* Illustrated BERT, [great explanation](https://jalammar.github.io/illustrated-bert/) 

**Implementation**
* Getting a big model into [production](https://medium.com/huggingface/scaling-a-massive-state-of-the-art-deep-learning-model-in-production-8277c5652d5f)

**Self improvement / learning**
* Learning course for [GAN](https://developers.google.com/machine-learning/gan/) from Google

**Data-sets**
* Stanford [sentiment data set](https://nlp.stanford.edu/sentiment/) 