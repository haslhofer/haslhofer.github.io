---
layout: post
title:  "ML on the edge survey"
author: gerald
categories: [ ml ]
image: assets/images/landscape7.jpg
---

Survey of ML on the edge
---

### Case studies

NLP

- Smart reply [Google Blog](https://ai.googleblog.com/2017/02/on-device-machine-intelligence.html) and [research paper](https://arxiv.org/pdf/1708.00630.pdf)
- [On-Device Conversational Modeling with TensorFlow Lite](https://ai.googleblog.com/2017/11/on-device-conversational-modeling-with.html) 
- [Reddit thread](https://www.reddit.com/r/MachineLearning/comments/e7c8bo/run_bert_on_mobile_phones_single_cup_core_a76_in/
) Run BERT on mobile device using [TinyBERT](https://github.com/huawei-noah/Pretrained-Language-Model/tree/master/TinyBERT)

Vision
- Vision: MobileNet Open Sourced: https://ai.googleblog.com/2017/06/mobilenets-open-source-models-for.html



### Frameworks

- [BOLT](https://github.com/huawei-noah/bolt)

- ML Kit with Tensorflow Lite
    - Smart-reply 
        > [Sample] to try out (https://www.tensorflow.org/lite/models/smart_reply/overview)


- ONNX Runtime from Microsoft. V1 of runtime [launched 10/2019](https://cloudblogs.microsoft.com/opensource/2019/10/30/announcing-onnx-runtime-1-0/). Works together with [NN API for Android](https://github.com/microsoft/onnxruntime/blob/master/docs/execution_providers/NNAPI-ExecutionProvider.md)
    - NNAPI:  Android [developer documentation](https://developer.android.com/ndk/guides/neuralnetworks)
        > [Sample] for NNAPI (https://github.com/android/ndk-samples/tree/master/nn_sample)
        - [DNNLibrary](https://github.com/JDAI-CV/DNNLibrary) is a wrapper of NNAPI. It lets you easily make the use of the new NNAPI introduced in Android 8.1. You can convert your onnx model into daq and run the model directly.
        > Sample https://github.com/daquexian/dnnlibrary-example



- Caffe2 / PyTorch

    > AI camera [Sample](https://github.com/caffe2/AICamera)
    - Unclear if Caffe2 uses NNAPI (see [thread](https://github.com/pytorch/pytorch/issues/18101))
    - [PyTorch Mobile](https://pytorch.org/mobile/home/), also [mentioned in](https://github.com/cedrickchee/pytorch-android)

### Generating smaller networks
- Neural projection networks. https://arxiv.org/pdf/1708.00630.pdf A joint learning framework based on neural projections to learn lightweight neural network models for performing efficient inference on device.
- Learn2Compress models: https://ai.googleblog.com/2018/05/custom-on-device-ml-models.html
