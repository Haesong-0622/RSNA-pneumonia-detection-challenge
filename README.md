# Defining a Problem
---
Pneumonia is diagnosed by chest X-ray, and a quick and accurate diagnosis is essential.
The competition aims to automatically classify pneumonia patients using machine learning, and locate them through bounding boxes if pneumonia is present.

# Task
---
Classification
Localization

# Data Source
---
30,000 X-ray examination images extracted from the NIH CXR14 dataset (2017 released)

# Configuration
---
Chest X-ray image of DICOM Format

Label
>Class
>>No Lung Opacity / Not Normal : 11,821
>>Lung Opacity : 9,555
>>Normal : 8,851
>Bounding Box

Image Size: 1024x1024

Check Data Size
>Total number of cases: 26,684
>Number of X-ray slides: 30,227 sheets

Check the number of data
>Classification
>>Total number of images : 18,406
>>the number of patients : 14,863
>Localization
>>Total number of images : 9,555
>>the number of patients : 6,012

# Classification Model
---
Select Model : ResNet50, ResNet101, EfficientNet_B2, EfficientNet_B5, VGG1
Loss function : Cross-Entropy Loss
Performance Evaluation Indicators : Accuracy, Sensitivity, Specificity, AUC ROC, Confusion Matrix

# Localization Model
---
Select Model : Faster R-CNN (ResNet50)
Loss function : Smooth L1 Loss
Performance Evaluation Indicators : IoU, mAP

# Classification Data Preprocessing
---
Image conversion and normalization
>DICOM -> RGB conversion for ImageNet pre-trained models
>Normalization for ImageNet pre-trained models
>Resizing to size 224x224 for ImageNet pre-trained models
>CLAHE application (improved contrast)

Split Train/Val/Test Data
>80% (Train), 20%(Test)
>Split 20% of Train into Val

# Localization Data Preprocessing
---
Image conversion and normalization
>DICOM -> RGB conversion for ImageNet pre-trained models
>Normalization for ImageNet pre-trained models
>Resizing to 600x600 size

Split Train/Val/Test Data
>80% (Train), 20%(Test)
>Split 20% of Train into Val


 

