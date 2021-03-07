# Face-Mask-Detection
This project is using a dataset of images of different people either wearing masks or not. It is then used to create a deep learning model and check the accuracy and validation score.

## What is SSD?
SSD is Single Shot Multibox Detector. It is a technique that is used to detect objects in images using a single deep neural network. Basically its used for object detection in an image. By using a base architecture of VGG-16 Architecture, SSD is able to out perform other object detectors like YOLO and Faster R-CNN in both speed and accuracy. The architecture of SSD is given in the figure below. Training a SSD model from scratch will require a lot of data, so here I have imported pretrained weights (Caffe Face Detector Model) using OpenCV.
