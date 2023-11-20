---
layout: post
title:  "Named entity extraction (NER)"
author: gerald
categories: [ ml, deep learning ]
image: assets/images/turks.jpg
---


The task in Named Entity Recognition (NER) is to find the entity-type of words. Entities can be locations, times or names. 

### Intros
* Introduction for named entities using Python at [depends-on-the-definition.com](https://www.depends-on-the-definition.com/introduction-named-entity-recognition-python)
* A Review of Named Entity Recognition (NER) in [towardsdatascience](https://towardsdatascience.com/a-review-of-named-entity-recognition-ner-using-automatic-summarization-of-resumes-5248a75de175)
* [Named entity extraction Github - sample code for 3 different methods](https://github.com/guillaumegenthial/tf_ner)
* [Papers with Code](https://www.paperswithcode.com/task/named-entity-recognition-ner) on Named Entity Recognition 

### Methods (from simple to advanced)
- Conditional random field (CRF) 
- LSTM
- [Bidirectional LSTM-CRF Models for Sequence Tagging](https://arxiv.org/abs/1508.01991) paper on arxiv and article [here](https://www.depends-on-the-definition.com/sequence-tagging-lstm-crf/) 
- LSTMs With Character Embeddings 
- Residual LSTM network together with ELMo embeddings (paper [here](https://arxiv.org/pdf/1802.05365.pdf))
    - ELMo word representations are functions of the *entire* input sentence
- [NER with BERT](https://www.depends-on-the-definition.com/named-entity-recognition-with-bert/) - highest score


### Service offerings 

* [Azure Entity identification and entity linking](https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/how-tos/text-analytics-how-to-entity-linking) 
* [Google Cloud Api Demo](https://cloud.google.com/natural-language/#natural-language-api-demo) which also figures out phone # etc. You can also train custom models.

### Client libraries

Good introduction [O'Reilly Deep Learning for Natural Language Processing](https://learning.oreilly.com/library/view/deep-learning-for/9781838550295/)

- Libraries:
    - [Open source - NLTK](https://www.nltk.org/). Introductory exercise here in O'Reilly book [here](https://learning.oreilly.com/library/view/deep-learning-for/9781838550295/C13783_02_Epub_Final_SZ.xhtml#_idParaDest-67)
    - [spaCy Industrial Strength NLP](https://spacy.io/)
        - Article that shows [custom NER](https://towardsdatascience.com/custom-named-entity-recognition-using-spacy-7140ebbb3718) on top of spaCy
    - [CoreNLP / Stanford Python library](https://stanfordnlp.github.io/stanfordnlp/)
    - [Gensim](https://radimrehurek.com/gensim/)
    - [Textblob](https://textblob.readthedocs.io/en/dev/api_reference.html#module-textblob.en.np_extractors)
    - [Flair](https://github.com/flairNLP/flair) A very simple framework for state-of-the-art NLP


### Data sets
- Training data set [entity annotated corpus](https://www.kaggle.com/abhinavwalia95/entity-annotated-corpus) 
- [Conll 2003](https://www.paperswithcode.com/sota/named-entity-recognition-ner-on-conll-2003)

### My own prototype
- Implementing spacy together with Flask / python, and deploying to Azure. [Live website](http://aka.ms/todosmart)

# Continuation 11/19/2023 with LLMs

- [Spacy LLM](https://github.com/explosion/spacy-llm/tree/main/usage_examples/ner_dolly)




