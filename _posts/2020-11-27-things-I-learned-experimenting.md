---
layout: post
title:  "Things I learned experimenting during Thanksgiving week"
author: gerald
categories: [ experiments]
image: assets/images/landscape7.jpg
---

- Taking a screenshot from Windows in the right resolution and scale factor
- Using Tesseract OCR engine
- spaCy NLP python library. [Demo with spacy](https://www.geeksforgeeks.org/python-named-entity-recognition-ner-using-spacy/)
- Powershell scripts and how to launch them (to access Windows.Media.OCR capabilities)
- Using Google cloud for [text classification](https://github.com/GoogleCloudPlatform/dotnet-docs-samples/tree/master/language/api/Analyze)
- Creating a Flask webserver hosting python code to expose capabilities to a local c# app (instead of always launching the python exe given that's too slow)
- Authenticating using MSAL to access resources in MS Graph
- Adding pages to OneNote (including inline base64 encoded images embedded in HTML to avoid having to use multi-part messages which never worked)
- Creating c# structure based on Json payload. [source](https://json2csharp.com/)

Future:

Extract summaries:
- https://pypi.org/project/bert-extractive-summarizer/

Layout analysis:
- https://github.com/Layout-Parser/layout-parser/blob/master/examples/Deep%20Layout%20Parsing.ipynb 
    - based on Facebook's Detectron framework
    - needs MS c++ 14+

- https://dhsegment.readthedocs.io/en/latest/start/annotating.html
- https://huggingface.co/transformers/model_doc/layoutlm.html based on https://arxiv.org/pdf/1912.13318v5.pdf 


Other sources and relative importance:
- annotated screens: https://github.com/ibm-aur-nlp/PubLayNet
- projects about document layout analysis : https://github.com/topics/document-layout-analysis 
