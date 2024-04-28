# A-comparative-analysis-of-Yolo-models-for-traffic-sign-detection

## Overview
In this repository you will find an overview of the most important files and resources related to our computer vision project focused on YOLO models.

## Contents

1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [How to use](#how-to-use)

## Introduction 
The objective of this project is to evaluate and compare three different models: YOLOv3, YOLOv5 and YOLOv8 with two traffic signs dataset. In particular we compare YOLOv3, YOLOv5n, YOLOv5m, YOLOv5x, YOLOv8n, YOLOv8m, YOLOv8x with a traffic sign dataset with and without data augmentation. 

## Dataset
1. We select a dataset from kaggle that contains 741 labelled photos of roads with different traffic signs.
   -  https://www.kaggle.com/datasets/valentynsichkar/traffic-signs-dataset-in-yolo-format

2. We increased the number of classes from 4 to 10, so we modify by hand all the .txt file to align the label class we added.

4. Additionally, upon realizing that no zebra crossing signs were labelled, we manually labelled some of them to address the issue.

5. To enhance dataset diversity, we opted some augmentation techniques that manipulate image contrast and brightness. Our process entailed duplicating both the images and labels folders of the original training set, applying data augmentation only to the replicated folder. We merge the first training set folder with the augmented one. Consequently, now we have two dataset, the ‘normal’ one that contains 444 train images, 148 validation images and 149 test images and the new ‘augmented’ dataset that contains 888 train images, 148 validation images and 149 test images.

## How to use
1. Clone the repo
2. Open *.ipynb file
3. Load the dataset
4. modify data.yaml file with your folder's path
5. To load the model
```bash
model = YOLO("yolov3.pt") #modify the model name
```
5. To perform training and validation, run the following command:
```bash
model.train(data="/content/drive/MyDrive/computervision/dataset/data.yaml", epochs = 30) #change the number of epochs
```
NB: remeber to insert your onwn path to data.yaml file
After train phase will appear a run folder in which where you will find saved all the metrics and the best and last model weigth (respectively best.pt and last.pt)
6. For predict purposes, run the following command:
```bash
infer = YOLO("/content/drive/MyDrive/computervision/runs/detect/v8_xl_aug/weights/best.pt")
infer.predict("/content/drive/MyDrive/computervision/dataset/dataset/datasets/test/images", save = True , save_txt = True )
```
NB: remeber to insert your onwn path to best.pt file in the first line and to the test directory in the second line
7. For test and metrics calculation, run the following command:
first you have to change the data.yaml file with the path to the test folder
```bash
model_test = YOLO("/content/drive/MyDrive/computervision/runs/detect/v5_m_30epoche/weights/best.pt")
results = model_test.val(data='/content/drive/MyDrive/computervision/dataset/data.yaml',conf=0.2,iou=0.5,split='test')
```
NB: remeber to insert your onwn path to best.pt file in the first line and to the data.yaml file in the second line



