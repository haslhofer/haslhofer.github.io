---
layout: post
title:  "Natural language processing - Introduction"
author: gerald
categories: [ ml, nlp ]
image: assets/images/landscape7.jpg
---

Natural language processing - introduction  and state-of-the-art
---

This post provides a summary of introductory articles I found useful to better understand what's possible in NLP, specifically what the current state of the art is and what areas should be prioritized for future explorations.

**NLP - Basics**
* Overview / [ImageNet moment in NLP](https://ruder.io/nlp-imagenet/)

**Embeddings**

First step often is turning input words into vectors using embeddings (see. e.g. [here](https://machinelearningmastery.com/what-are-word-embeddings/) for an explanation of word embeddings). These vectors capture some semantics (king-man+woman=queen). These vectors are somewhere in the 200-300 dimensions range.   

  *Non-contextual embeddings*

  Embedding explanation with Word2Vec focus on [medium](https://medium.com/deeper-learning/glossary-of-deep-learning-word-embedding-f90c3cec34ca). Key constraint of Word2Vec is that it doesn't capture multiple interpretations of a single word ("stick").
  * Word2Vec - generate your own - [Google project](https://code.google.com/archive/p/word2vec/)
  * GloVe. 
   
  *Contextualized embeddings*

  Contextualized word embeddings factor in multiple interpretations of words. ELMo uses bi-directional LSTM to create embeddings based on the context of words. 
* Video about using sentence embedding [for fact checking](https://www.youtube.com/watch?v=ddf0lgPCoSo)

**Attention** 

[Overview](https://jalammar.github.io/visualizing-neural-machine-translation-mechanics-of-seq2seq-models-with-attention/) and original paper ["Attention is all you need"](https://arxiv.org/pdf/1706.03762.pdf). Basic premise is that enabling the neural network to pay attention to a specific subset of hidden states leads to better results.

**Transformers**

* Basics - *Transformer* Great high level [overview](http://jalammar.github.io/illustrated-transformer/). Originally introduced in ["Attention is all you need"](https://arxiv.org/pdf/1706.03762.pdf).  
Fully annotated code to the paper from Harvard NLP group is [here](http://nlp.seas.harvard.edu/2018/04/03/attention.html).  
And [Tensorflow library tensor2tensor](https://github.com/tensorflow/tensor2tensor). Interactive tensor2tensor on [Google Colab](https://colab.research.google.com/github/tensorflow/tensor2tensor/blob/master/tensor2tensor/notebooks/hello_t2t.ipynb).   
Hugging Face Transformer [quick tutorial](https://github.com/huggingface/transformers)  
Transformer [introduction](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html) from Google
* Introductory article for [Hugging Face](https://blog.tensorflow.org/2019/11/hugging-face-state-of-art-natural.html?m=1) NLP library 

**OpenAI transformer**  

Language modelling using 12 stacked *de*coder layers for language tasks such as classification, similarity, multiple choice questions - [source](https://openai.com/blog/language-unsupervised/). Note: this transformer is unidirectional (so a step back from LSTM based embeddings such as ELMo)

**BERT**   

* [BERT original paper](https://arxiv.org/pdf/1810.04805.pdf)
* Illustrated BERT, [great explanation](https://jalammar.github.io/illustrated-bert/) 


Basic premise: semi-supervised training on large amounts of text to build model. Uses *en*coder stack (as opposed to OpenAI which uses decoder stack)

 Key concepts applied: semi-supervised sequence learning; Transformers; ELMo (evolution of), ULMFiT (evolution of)

Bert is pre-trained with two tasks: (1) predict missing word (2) figure out if sentence A follows sentence B

Predict missing words: masked language input (replace 15% of input with [Mask] keyword).

Two-sentence task: predict if sentence A follows sentence B. 
Other notes: BERT doesn't use words, but WordPieces which are smaller chunks.

**Using BERT**


Once BERT is pre-trained, it can be combined with supervised training with specific labeled data set.

Simplest model: train a binary classifier with (1) BERT --> (2) Feed-forward neural network + softmax. 
BERT model is modified only slightly during the training phase (details in the great article [here](https://jalammar.github.io/illustrated-bert/) )
* Interactive BERT in [Google Colab](https://colab.research.google.com/github/tensorflow/tpu/blob/master/tools/colab/bert_finetuning_with_cloud_tpus.ipynb) with specific language tasks 

* BERT and [Binary classification](https://towardsdatascience.com/how-to-do-text-binary-classification-with-bert-f1348a25d905)

* BERT and [Semantic Similarity in Sentences](https://medium.com/analytics-vidhya/semantic-similarity-in-sentences-and-bert-e8d34f5a4677) on Medium  


**Implementation**
* Getting a big model into [production](https://medium.com/huggingface/scaling-a-massive-state-of-the-art-deep-learning-model-in-production-8277c5652d5f)

**Self improvement / learning**
* Learning course for [GAN](https://developers.google.com/machine-learning/gan/) from Google

**Data-sets**
* Stanford [sentiment data set](https://nlp.stanford.edu/sentiment/) 