# A-comparative-analysis-of-Yolo-models-for-traffic-sign-detection

## Overview
In this repository you will find an overview of the most important files and resources related to our computer vision project focused on YOLO models.

## Contents

1. [Introduction](#introduction)
2. [Dataset](#dataset)

## Introduction 
The objective of this project is to evaluate and compare three different models: YOLOv3, YOLOv5 and YOLOv8 with two traffic signs dataset. In particular we compare YOLOv3, YOLOv5n, YOLOv5m, YOLOv5x, YOLOv8n, YOLOv8m, YOLOv8x with a traffic sign dataset with and without data augmentation. 

##Dataset
1. We select a dataset from kaggle that contains 741 labelled photos of roads with different traffic signs.
   -  https://www.kaggle.com/datasets/valentynsichkar/traffic-signs-dataset-in-yolo-format

2. We increased the number of classes from 4 to 10, so we modify by hand all the .txt file to align the label class we added.

4. Additionally, upon realizing that no zebra crossing signs were labelled, we manually labelled some of them to address the issue.

6. To enhance dataset diversity, we opted some augmentation techniques that manipulate image contrast and brightness. Our process entailed duplicating both the images and labels folders of the original training set, applying data augmentation only to the replicated folder. We merge the first training set folder with the augmented one. Consequently, now we have two dataset, the ‘normal’ one that contains 444 train images, 148 validation images and 149 test images and the new ‘augmented’ dataset that contains 888 train images, 148 validation images and 149 test images. 



