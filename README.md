# Bone-Age-Estimation
Bone age estimation using hand X-Ray images

Well, in this project, we are going to estimate the bone age of people using X-Ray images of the hand.

The dataset used for this project is the Atlas dataset, which is publicly available.
https://ipilab.usc.edu/research/baaweb/

But this dataset requires a pre-processing phase, which is explained below.

This dataset has 1390 photos of the left hand of people from infancy to 18 years old and with 4 different races and 2 types of gender.

Our work is not classification, but regression. The input of our Convolutional Neural Network will be the photo and the output will be the bone age of the person.

We know that the images that enter the network as input must have the same size, but this dataset does not follow this rule. So the first thing we did was to resize all the images to 928×928.

On the other hand, for better training of the network, it is necessary to increase the number of photos. For this reason, we increased the number of photos to 7393 by using the data augmentation technique. Also, in this dataset, the number of photos in different age ranges was unbalanced, which makes the neural network always converge to the age that has the most photos. For example, the number of photos for babies was 23 samples, which was less compared to the age group of 12 years, which had 117 samples, and we increased the number of photos in a balanced way to solve this problem. We used data augmentation manually with the operators such as rotate, flip, increase or decrease brightness according to the needs of that photo, and color filters. The advantage of doing this manually was that some anomaly photos like the ones below were detected and removed to make the network work properly.

| Having a ring | Having a bracelet | Skeletal unknown | Bone growth abnormality in the age group of 7 years |
| --- | --- | --- | --- |
|![image](https://user-images.githubusercontent.com/103449830/233351110-a0c9aba9-c870-40f3-911c-3bd4d7c6bf8a.png)|![image](https://user-images.githubusercontent.com/103449830/233351305-9d66ed34-90ec-4e3c-a548-b63b4674936d.png)|![image](https://user-images.githubusercontent.com/103449830/233351333-8c94cda3-f0db-4e44-a248-af5846896123.png)|![image](https://user-images.githubusercontent.com/103449830/233379866-acdf2760-e112-4240-99be-1c6bfb6d32e9.png)

Because our learning is a supervised learning type; The next step is to create an Excel file as a label for Convolutional Neural Network (CNN).
We created the Excel file in the following order.
- First of all, we changed the names of the photos for convenience, then we entered the names of the photos under the title (Case ID) in the Excel file.
- Second, we created another field to specify the bone age of each photo and entered its bone age for each photo. It is necessary to add that we had to use the number 0 to define the baby's age.
- Third, we created another field to specify the gender type of each photo and used true or false to specify the gender.
- And finally, we created a field to determine the race of people called location.

Note that we save the Excel file with the .csv extension.

|||
| --- | --- |
|![00](https://user-images.githubusercontent.com/103449830/233405982-ff4ec267-e8b6-40f7-b8b1-62f1920b0b6f.jpg)|![01](https://user-images.githubusercontent.com/103449830/233406671-d268e90d-ad09-42f6-bc88-9144759c1339.jpg)

Due to hardware limitations in training, we run our Convolutional Neural Network on the Google Colab platform. Also, to speed up the process of neural network training, we set the runtime type to GPU.


## 10 Epoch 

|  | MAE | Validation MAE | Loss | Validation Loss | Accuracy | Validation Accuracy |
| --- | --- | --- | --- | --- | --- | --- |
| VGG19 | --- | --- | --- | --- | --- | ---
| VGG16 | --- | --- | --- | --- | --- | ---
| CNN | --- | --- | --- | --- | --- | ---
| U-net | --- | --- | --- | --- | --- | ---
| Attention Mechanism | --- | --- | --- | --- | --- | ---
| EfficientNetV2S | --- | --- | --- | --- | --- | ---
| Resnet50 | --- | --- | --- | --- | --- | ---
| Vision-Transformer | --- | --- | --- | --- | --- | ---
| Yolo | --- | --- | --- | --- | --- | ---


## 18 Epoch 

|  | MAE | Validation MAE | Loss | Validation Loss | Accuracy | Validation Accuracy |
| --- | --- | --- | --- | --- | --- | --- |
| VGG19 | --- | --- | --- | --- | --- | ---
| VGG16 | --- | --- | --- | --- | --- | ---
| CNN | --- | --- | --- | --- | --- | ---
| U-net | --- | --- | --- | --- | --- | ---
| Attention Mechanism | --- | --- | --- | --- | --- | ---
| EfficientNetV2S | --- | --- | --- | --- | --- | ---
| Resnet50 | --- | --- | --- | --- | --- | ---
| Vision-Transformer | --- | --- | --- | --- | --- | ---
| Yolo | --- | --- | --- | --- | --- | ---


-THE END-
