# Face-Mask-Detection
This project is using a dataset of images of different people either wearing masks or not. It is then used to create a deep learning model and check the accuracy and validation score.

## What is SSD?
<center>
![SSD Architecture](https://www.researchgate.net/profile/Adam_Nowosielski/publication/332948824/figure/fig5/AS:767146284036100@1559913335810/The-model-of-Single-Shot-MultiBox-Detector-SSD-25.ppm)
<center>
  
SSD stands for Single Shot Multibox Detector. It is a technique that is used to detect objects in images using a single deep neural network. Basically its used for object detection in an image. By using a base architecture of VGG-16 Architecture, SSD is able to out perform other object detectors like YOLO and Faster R-CNN in both speed and accuracy. The architecture of SSD is given in the figure below. Training a SSD model from scratch will require a lot of data, so here I am using Caffe Face Detector Modelin OpenCV. This pre-trained model is part of the OpenCV library (version 3.3 onwards). It has been uploaded [here](https://github.com/asad-mahmood/Face-Mask-Detection/tree/main/caffe-face-detector-opencv-pretrained-model) for convenient usage.

## Data Label Count

The visualization below tells us that the **Number of Mask images > Number of Non-Mask images**, so this is an imbalanced dataset. But since we are using a SSD pretrained model, which is trained to detect non-mask faces, this imbalance would not matter a lot.

![Image](https://github.com/asad-mahmood/Face-Mask-Detection/blob/main/Label%20Count.png)
