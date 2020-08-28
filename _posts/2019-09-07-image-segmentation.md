---
layout: post
title:  "Image segmentation: resources"
author: gerald
categories: [ ml, rpa ]
image: assets/images/landscape7.jpg
---

Segment the screen / disambiguate areas of interest
---

**Intros**

* [Segmantic segementation](http://blog.qure.ai/notes/semantic-segmentation-deep-learning-review)
    - Difference between object detection (bounding box) and semantic segmentation (each pixel is classified)
    - One general thing most of the architectures have in common is an encoder network followed by a decoder network
* [Deeplearning intro on TowardsDataScience](https://towardsdatascience.com/semantic-segmentation-with-deep-learning-a-guide-and-code-e52fc8958823)
* [Deeplearning intro on Medium ](https://medium.com/nanonets/how-to-do-image-segmentation-using-deep-learning-c673cc5862ef) 
* [Mobile Real-time Video Segmentation](https://ai.googleblog.com/2018/03/mobile-real-time-video-segmentation.html) 
* [State of the art for semantic segmentation 2019](https://www.novatec-gmbh.de/blog/semantic-segmentation-part-4-state-of-the-art/)

**Specific algorithms**


**Deeplab**

Particularly usable for high performance and real-time applications. Suitable for feasibility checks - easy to implement and works well for real-time applications.

* [Deeplab-V3 paper](https://arxiv.org/abs/1802.02611)
* [Code for Deeplab](https://github.com/tensorflow/models/tree/master/research/deeplab) and [Papers with Code](https://www.paperswithcode.com/method/deeplabv3)
* [Tensorflow-deeplab-v3-plus](https://github.com/rishizek/tensorflow-deeplab-v3-plus)
* [Google TPU tutorial on deeplab](https://cloud.google.com/tpu/docs/tutorials/deeplab)
* [Tensorflow deeplab readme](https://github.com/tensorflow/tpu/blob/master/models/experimental/deeplab/README.md)
* [Towardsdatascience.com The evolution of deeplab for semantic segmentation](https://towardsdatascience.com/the-evolution-of-deeplab-for-semantic-segmentation-95082b025571)
* [How to use deeplab in tensorflow for object segmentation](https://www.freecodecamp.org/news/how-to-use-deeplab-in-tensorflow-for-object-segmentation-using-deep-learning-a5777290ab6b/)
* [Semantic image segmentation with DeepLab in Tensorflow](https://ai.googleblog.com/2018/03/semantic-image-segmentation-with.html)


**Convolutional networks** 
* [Fully convolutional networks for semantic segmentation](https://people.eecs.berkeley.edu/~jonlong/long_shelhamer_fcn.pdf)
    - FCN is not so powerful as other discussed models and serves as basic information
* [CNNs with skip connections](https://github.com/jiny2001/dcscn-super-resolution) 
* [Fully Convolutional Networks for Semantic Segmentation](https://arxiv.org/abs/1411.4038) 
* [U-Net for satellite images](https://deepsense.ai/deep-learning-for-satellite-imagery-via-image-segmentation/) 

Mask R-CNN takes a different approach as the encoder-decoder structure. It is an extension of Faster R-CNN, which is used for object detection. Besides the *class label* and *bounding box* coordinates, it returns the *mask for each object*. 
* [Mask R-CNN, extends Faster R-CNN](https://arxiv.org/pdf/1703.06870.pdf)
* [Facebookresearch maskrcnn benchmark](https://github.com/facebookresearch/maskrcnn-benchmark?utm_source=mybridge&amp;utm_medium=blog&amp;utm_campaign=read_more), superseded by [Detectron2 by Facebook](https://github.com/facebookresearch/detectron2) 
* [Mask R-CNN implementation](https://hackernoon.com/instance-segmentation-in-google-colab-with-custom-dataset-b3099ac23f35)
* [Transfer learning with Mask R-CNN](https://www.novatec-gmbh.de/blog/semantic-segmentation-part-3-transfer-learning/)
* [EfficientPS](http://panoptic.cs.uni-freiburg.de/): New State-of-the-art Model in Panoptic Segmentation. No code available.
* [Seamless Scene Segmentation](https://github.com/mapillary/seamseg)


**GAN**
* [GAN: Pix2Pix](https://phillipi.github.io/pix2pix/)
* [Pix2Pix turorial](https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/r2/tutorials/generative/pix2pix.ipynb#scrollTo=YfIk2es3hJEd)
* [Original Pix2Pix paper](https://arxiv.org/pdf/1611.07004.pdf)  

**YoloV3**
* [YoloV3](https://pjreddie.com/darknet/yolo/)
* [Review yolov3 you-only-look-once-object-detection](https://towardsdatascience.com/review-yolov3-you-only-look-once-object-detection-eab75d7a1ba6)
* [YoloV3 paper on arxiv](https://arxiv.org/abs/1804.02767)  


**Document structure. Figure out which input elements belong to which text elements**  
[Semantics of words - Word2Vec](https://papers.nips.cc/paper/5021-distributed-representations-of-words-and-phrases-and-their-compositionality.pdf) 


**Useful links for implementation:**
* Semantic segmentation [suite](https://github.com/GeorgeSeif/Semantic-Segmentation-Suite)
* [Dataset Pascal VOC2012](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/)



![useful image]({{ site.url }}/assets/ml.png)