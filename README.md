# Car Make and Model classification example with YOLOv3 object detector

[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE)

## Introduction

A C++ example of using [Spectrico's car make and model classifier](http://spectrico.com/car-make-model-recognition.html). It consists of an object detector for finding the cars, and a classifier to recognize the makes and models of the detected cars. The object detector is an implementation of YOLOv3 (OpenCV DNN backend). It doesn't use GPU and one frame takes 1s to process on Intel Core i5-7600 CPU. YOLOv3 weights were downloaded from [YOLO website](https://pjreddie.com/darknet/yolo/). The classifier is based on MobileNet  (OpenCV DNN backend). It takes 35 milliseconds on Intel Core i5-7600 CPU for a single classification.
Here is a web demo to test the full version: [Vehicle Make and Model Recognition](http://spectrico.com/demo-car-mmr.html)

![image](https://github.com/spectrico/car-make-model-classifier-yolo3-cpp/blob/master/car-make-model.png?raw=true)

---
## Object Detection and Classification in images
This example takes an image as input, detects the cars using YOLOv3 object detector, crops the car images, makes them square while keeping the aspect ratio, resizes them to the input size of the classifier, and recognizes the make and model of each car. The result is printed on the display.


#### Usage
```
$ car-make-model-classifier-yolo3-cpp cars.jpg
```
The output is printed to the console:
```
------------------------------------------------
Object box: [440 x 193 from (606, 144)]
Inference time, ms: 26.2037
Top 3 probabilities:
make: Volkswagen        model: Arteon   confidence: 99.6351 %
make: Volkswagen        model: T-ROC    confidence: 0.0392523 %
make: Volkswagen        model: Touareg  confidence: 0.0319628 %
------------------------------------------------

------------------------------------------------
Object box: [318 x 158 from (958, 157)]
Inference time, ms: 8.0567
Top 3 probabilities:
make: Volkswagen        model: Polo     confidence: 45.5947 %
make: Volkswagen        model: Golf     confidence: 16.0215 %
make: Volkswagen        model: Jetta    confidence: 6.41334 %
------------------------------------------------

------------------------------------------------
Object box: [277 x 176 from (362, 137)]
Inference time, ms: 8.4046
Top 3 probabilities:
make: Volkswagen        model: Tiguan   confidence: 80.6286 %
make: Volkswagen        model: Touareg  confidence: 4.5901 %
make: Volkswagen        model: Golf     confidence: 4.12266 %
------------------------------------------------
```

---
## Requirements
  - C++ compiler
  - OpenCV
  - yolov3.weights must be downloaded from [https://pjreddie.com/media/files/yolov3.weights](https://pjreddie.com/media/files/yolov3.weights) and saved into the project folder

---
## Credits
The YOLOv3 object detector is from: [YOLO: Real-Time Object Detection](https://pjreddie.com/darknet/yolo/)

```
@article{yolov3,
  title={YOLOv3: An Incremental Improvement},
  author={Redmon, Joseph and Farhadi, Ali},
  journal = {arXiv},
  year={2018}
}
```
The make and model classifier is based on MobileNet neural network architecture: [MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/abs/1704.04861)


