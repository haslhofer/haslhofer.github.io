---
layout: post
title:  "Deep learning - course take-aways"
author: gerald
categories: [ learning ]
image: assets/images/face.jpg
---

Notes from PyTorch bootcamp 
---

[Source](https://learning.oreilly.com/videos/pytorch-bootcamp-for/9781839218897/9781839218897-video2_4)

Numpy
- import numpy as np
- x = np.array([1,1])

Simple arithmetic
``` 
x = np.array([4,4,6])
y = np.array([5,3.4,6])
z = x +  y
print (z)
``` 

Dot product: np.dot(x,y)

``` 
Matrix: np.matrix
x = np.matrix([[4,5], [6,7])
``` 

Matrix multiplication: np.multiply(a,b) - elementwise; otherwise a*b

Inverse matrix:

``` 
from numpy.linalg import inv
print (inv(x))
``` 