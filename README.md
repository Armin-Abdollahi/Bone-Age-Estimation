# Bone-Age-Estimation
Bone age estimation using hand X-Ray images

Well, in this project, we are going to estimate the bone age of people using X-Ray images of the hand.

The dataset used for this project is the Atlas dataset, which is publicly available.
https://ipilab.usc.edu/research/baaweb/

But this dataset requires a pre-processing phase, which is explained below.

This dataset has 1390 photos of the left hand of people from infancy to 18 years old and with 4 different races and 2 types of gender.

Our work is not classification, but regression. The input of our Convolutional Neural Network will be the photo and the output will be the bone age of the person.

We know that the images that enter the network as input must have the same size, but this dataset does not follow this rule. So the first thing we did was to resize all the images to 928×928.

On the other hand, for better training of the network, it is necessary to increase the number of photos. For this reason, we increased the number of photos to 7393 by using the data augmentation technique. We used data augmentation manually with the operators rotate, flip, increase or decrease the brightness according to that photo, and color filters. The advantage of doing this manually was that some anomaly photos like the ones below were detected and removed.

![image](https://user-images.githubusercontent.com/103449830/233351110-a0c9aba9-c870-40f3-911c-3bd4d7c6bf8a.png)
![image](https://user-images.githubusercontent.com/103449830/233351283-bdea03d1-f3c2-4b98-af9e-6a66ba9ff756.png)
![image](https://user-images.githubusercontent.com/103449830/233351305-9d66ed34-90ec-4e3c-a548-b63b4674936d.png)
![image](https://user-images.githubusercontent.com/103449830/233351333-8c94cda3-f0db-4e44-a248-af5846896123.png)

Because our learning is a supervised learning type; The next step is to create an Excel file as a label for Convolutional Neural Network (CNN). In the Excel file, the names of the photos under the title (ID Case) and instead of not entering any type of gender, we used true or false for male. And also we had to use the number 0 to define the baby's age in Excel.

![image](https://user-images.githubusercontent.com/103449830/233353452-22167659-737d-4601-8372-531dd8e68ee4.png)

Note that we save the Excel file with the .csv extension.

Due to hardware limitations in training, we run our Convolutional Neural Network on the Google Colab platform. Also, to speed up the process of neural network training, we set the runtime type to GPU.

-THE END-
