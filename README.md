# :eye:MultipleOcularDisorders_CV

This project creates a classifier that is able to categorize ocular pathologies into 4 categories i.e. Diabetic Retinopathy, Glaucoma, Other, and Normal. We will be using multiple ML methods as a means of learning how to apply those ML methods and also to find out the best methods. 
The kaggle dataset can be found [here]( https://www.kaggle.com/c/vietai-advance-course-retinal-disease-detection/overview)

## Table of Contents
The following topics will be covered:

### 1\. Task 1: Classification Models
  - Model 1: AlexNet
  - Model 2: VGG16
  - Model 3: Xception

### 2\. Task 2: Visualizing Regions of Interest using GradCAM
  - Setting up the CAM
  - Superimposing the gradCAM on the Image
  - Individual Analysis
    - Diabetic Retinopathy
    - Galucoma
    - Normal
    - Other
### 3\. Taks 3: Semi-Supervised Learning
### 4\. Conculsuion


## Tools Used:

* Tensorflow 2.3
* Python 3.8
* Google Colab

## Takeaways
### Task 1 Takeaways

* Our output metrics of choice were: Precision, Recall, F1, Accuracy
* We ran a simple AlexNet and then added a layer of image augmentation, but the simple AlexNet had a better performance
* We ran a VGG16 with ImageNet weights and image augmentation, and then fine-tuned it for our data, whereby the fine-tuned version proved better.
* We ran an Xception model with similar modifications as the VGG16. Performance did not improve.

### Task 2 Takeaways

* gradCAM is a good technique for diving into a domain called model interpretability
* You can see how the model gives importance to certain features of an image to be able to classify it appropriately
* Diabetic Retinopathy:  

![dr](https://github.com/AShahLab/MultipleOcularDisorders_CV/blob/main/Images/dr.jpg)  

* Glaucoma:  

![g](https://github.com/AShahLab/MultipleOcularDisorders_CV/blob/main/Images/glauc.jpg)  

* Other:  

![o](https://github.com/AShahLab/MultipleOcularDisorders_CV/blob/main/Images/other.jpg)  

* Normal:  

![n](https://github.com/AShahLab/MultipleOcularDisorders_CV/blob/main/Images/normal.jpg)

### Task 3 Takeaways

* We used Label Propagation on the unlabeled images, after predicting them through our model. 
* We were able to concatenate the labeled and unlabeled data (post label propagation) and retrain the network (AlexNet)
* The results are shown below for all models:  

|Models          | Precision|Recall|Accuracy   |F1    |
|------|-------|---------|-------------|----------|  
|AlexNet    |   0.73   |  0.70   |  0.71  |0.70   
|AlexNet with Image Augmentation|0.20|0.29|0.44|0.23 
|VGG16 with Image Augmentation and Regularization|     0.40  | 0.47 | 0.59 |0.41  
|VGG16 Fine Tuned|   0.62  |  0.56  |  0.60  | 0.57    
|Xception with Image Augmentation and Regularization|0.63 |0.48 |0.59 |0.41 |  
|Xception Fine Tuned| 0.61|0.58 |0.60 |0.59 |  
|AlexNet with unsupervised learning predictions|0.68|0.66|0.66|0.65|    


## Authors

* **Awais Shah** 

