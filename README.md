# Age Detection of Indian Actors | Analytics Vidhya
#### About Problem
Indian Movie Face database (IMFDB) is a large unconstrained face database consisting of 34512 images of 100 Indian actors collected from more than 100 videos. All the images are manually selected and cropped from the video frames resulting in a high degree of variability interms of scale, pose, expression, illumination, age, resolution, occlusion, and makeup. IMFDB is the first face database that provides a detailed annotation of every image in terms of age, pose, gender, expression and type of occlusion that may help other face related applications. For more details about the data set, read here

Data The dataset is cleaned and formatted to give you a total of 26742 images with 19906 images in train and 6636 images in test.

The task is to predict the age of a person from his or her facial attributes. For simplicity, the problem has been converted to a multiclass problem with classes as Young, Middle and Old.

The attributes of data are as follows: ID – Unique ID of image Class – Age bin of person in image

#### Dataset in below link
https://datahack.analyticsvidhya.com/contest/practice-problem-age-detection/

#### Datasets structure
train 
  |-Train (folder contains training all images) 
  |-train.csv (Contains image names as ID's and class label which it belongs to)

test 
  |-Test (folder contains test all images) 
  |-test.csv (Contains image names as ID's)
  
#### This approach worked well for this problem and got 88.53 accuracy on test set which put this result in 19th position in this competetion. This can be taken further if more time is spent with GPU and need to tweak parameters on the best model till date.
 
