# Using Neural Networks to Classify Breast Cancer 
![header](https://https://https://github.com/Bryan-Lange/Breast-Cancer-Classification-with-Neural-Networks/blob/master/presentation%20images/breast_cancer_classification_header.jpg)
---
## By: Bryan Lange - [LinkedIn](https://www.linkedin.com/in/bryanrobertlange) 

---
## Executive Summary

-[Introduction and problem statement](#Introduction "Intro")

-[Data overview](#Data-Information "Data")

-[Data Preprocessing and EDA](#Data-Preprocessing "EDA")

-[Modeling the data](#Modeling-Process "Models")

-[Key observations from analysis](#Key-Findings "Go to Key-Findings")

-[Challenges and recommendations](#Obstacles-and-recommendation "EDA")

### Introduction

- About 1 in 8 U.S. women will develop breast cancer over the course of her lifetime

- The American Cancer Society estimates over 275,000 new cases in 2020 with over 40,000 deaths attributed to breast cancer

- Second highest cancer death rate in American females (behind lung cancer)

- Over 3.5 million women with a history of breast cancer in the U.S.

- Breast cancer can be non-invasive, which means it does not spread beyond the lobule or duct, or it can be invasive where it spreads beyond the duct into the normal tissue 

- 80% of malignant breast cancers are Invasive Ductal Carcinoma (IDC) which can invade surrounding tissue, lymph nodes and possibly other areas of the body

### Problem Statement
- Invasive breast cancer detection can be a time consuming task
- A pathologist needs to scan large, mostly benign areas to ultimately hone in on a malignant region, which can be very tedious 
- Errors can be made in the process and smaller malignant areas can be overlooked by the human eye 
- Advancements in technology should be able to assist by automating part of the process and double checking the diagnosis given by the pathologist 


    **Using histopathological images, can we train a neural network to accurately detect the presence of invasive ductal carcinoma?**


---
## Data Information

The original dataset consisted of 162 whole mount slide images of Breast Cancer (specifically Invasive Ductal Carcinoma) specimens scanned at 40x. From that, 277,524 patches of size 50  x 50 were extracted (198,738 IDC negative and 78,786 IDC positive).

Each patch’s file name is of the format:

u_xX_yY_classC.png   — > example 10253_idx5_x1351_y1101_class0.png

Where u is the patient ID (10253_idx5), X is the x-coordinate of where this patch was cropped from, Y is the y-coordinate of where this patch was cropped from, and class indicates where 0 is non-IDC and 1 is IDC.

| Data Source | Description | Link |
| --- | --- | --- |
| Andrew Janowczyk - Deep Learning Datasets | Original data | [Link](http://www.andrewjanowczyk.com/use-case-6-invasive-ductal-carcinoma-idc-segmentation/)|
| Kaggle | 50x50 pixel image patches | [Link](https://www.kaggle.com/paultimothymooney/breast-histopathology-images)|

---
## Data Preprocessing 
- The images were scanned at 40x
- Those images were then broken into 277,526 patches patches 
- Each patch is then reshaped to be 50 x 50 pixels

---
## Modeling Process

- Using random sampling, the classes are balanced before the modeling begins 

- Data is divided into training, testing, and validation sets

- My first attempt utilized Conv2D layers in a Sequential Model to help identify essential features that classify the images and dropouts were used to help avoid overfitting the model 

- This is a binary classification problem and we want to produce a probability so the sigmoid activation layer is generally used for the output

- Given the nature of the subject matter, our goal is to limit the number of false-negatives (recall) to ensure those with IDC do not walk away believing they are healthy 
---
## Key Findings

- The learning rate is the most influential hyperparameter

- Trained models alleviate pathologist work and provide a second set of eyes

- Transfer learning and ensemble methods will continue to assist in accurate and reliable classification

---
### Obstacles and recommendations


