# Bone-Age-Estimation
Bone age estimation using hand X-Ray images

In this project, we intend to estimate the bone age of people using X-Ray images of the hand.

The dataset used for this project is the Atlas dataset, which is publicly available. But this dataset requires a pre-processing phase, which is explained below.

This dataset has 1390 photos of the left hand of people from infancy to 18 years old with 4 races and 2 genders.

We know that the images that enter the network as input must have the same size, but this dataset is not like that.

First, we resized the images to 928×928

The second step was to increase the number of photos to train the network better. For this reason, using the data augmentation technique, we increased the number of photos to 7393. We performed data augmentation manually with the operators such as rotate, flip, increase or decrease brightness according to that photo, color filters. The advantage of doing this process manually was that a number of anomaly photos were detected and removed.

The third step was to create an Excel file as a label for the network.
