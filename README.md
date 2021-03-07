# Face-Mask-Detection
This project is using a dataset of images of different people either wearing masks or not. It is then used to create a deep learning model and check the accuracy and validation score.

## What is SSD?

<p align="center">
<img src="https://www.researchgate.net/profile/Adam_Nowosielski/publication/332948824/figure/fig5/AS:767146284036100@1559913335810/The-model-of-Single-Shot-MultiBox-Detector-SSD-25.ppm"></img>
</p>

SSD stands for Single Shot Multibox Detector. It is a technique that is used to detect objects in images using a single deep neural network. Basically its used for object detection in an image. By using a base architecture of VGG-16 Architecture, SSD is able to out perform other object detectors like YOLO and Faster R-CNN in both speed and accuracy. The architecture of SSD is given in the figure below. Training a SSD model from scratch will require a lot of data, so here I am using Caffe Face Detector Modelin OpenCV. This pre-trained model is part of the OpenCV library (version 3.3 onwards). It has been uploaded [here](https://github.com/asad-mahmood/Face-Mask-Detection/tree/main/caffe-face-detector-opencv-pretrained-model) for convenient usage.

## Data Label Count

<img src="https://github.com/asad-mahmood/Face-Mask-Detection/blob/main/Label%20Count.png"></img>

The visualization tells us that the **Number of Mask images > Number of Non-Mask images**, so this is an imbalanced dataset. But since we are using a SSD pretrained model, which is trained to detect non-mask faces, this imbalance would not matter a lot. Along with that we are using keras preprocessing techniques to artifically increase our dataset size such as by flipping images horizontally, rotating them and etc.

## Traing VS Validation Data

I trained the model for 100 epochs and below I will discuss the results of accuracy and loss.

### Accuracy

I achieved accuracy on training set: 96.86 % and on validation set: 96.87%. Please see the attached picture below.

![](https://github.com/asad-mahmood/Face-Mask-Detection/blob/main/Training%20Vs%20Validation%20Acc.png)

### Loss

I achieved loss on training set: 0.0791 and on validation set: 0.117.  Please see the attached picture below.

![](https://github.com/asad-mahmood/Face-Mask-Detection/blob/main/Training%20Vs%20Validation%20Loss.png)

## Model Testing

The test dataset has 1698 images and to evaluate the model I have taken a handful of images from this dataset as there are no labels for faces in the dataset.
* Gamma Correction for making the image appear in more light.**(Gamma = 2)**
* blobFromImage creates 4-dimensional blob from image. Optionally resizes and crops image from center, subtract mean values, scales values by scalefactor, swap Blue and Red channels.
* The blob is passed through the SSD network and detections are made with some confidence score.
* Define a threshold confidence score, above which the detection will be considered as a candidate of being a face. (In this case **confidence threshold = 0.2**)
* All the detections that qualify the confidence score are then passed to the architecture for classification into mask or non-mask image.

The results are as follows:

![](https://github.com/asad-mahmood/Face-Mask-Detection/blob/main/result.png)
