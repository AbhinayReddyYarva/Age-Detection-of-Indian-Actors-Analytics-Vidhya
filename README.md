# Age Detection of Indian Actors | Analytics Vidhya | Active Competition | 19th Position

Link - https://datahack.analyticsvidhya.com/contest/practice-problem-age-detection/

#### Got 88.53% accuracy on test set which put this result in 19th position in the competetion. This can be taken further if more time is spent with GPU and need to tweak parameters on the best model till date.
 
Code - https://github.com/AbhinayReddyYarva/Age-Detection-of-Indian-Actors-Analytics-Vidhya/blob/master/age_pred_alexnet.ipynb 

#### About Problem
Indian Movie Face database (IMFDB) is a large unconstrained face database consisting of 34512 images of 100 Indian actors collected from more than 100 videos. All the images are manually selected and cropped from the video frames resulting in a high degree of variability interms of scale, pose, expression, illumination, age, resolution, occlusion, and makeup. IMFDB is the first face database that provides a detailed annotation of every image in terms of age, pose, gender, expression and type of occlusion that may help other face related applications. For more details about the data set, read here

Data The dataset is cleaned and formatted to give you a total of 26742 images with 19906 images in train and 6636 images in test.

The task is to predict the age of a person from his or her facial attributes. For simplicity, the problem has been converted to a multiclass problem with classes as Young, Middle and Old.

The attributes of data are as follows: ID – Unique ID of image Class – Age bin of person in image

#### About competition, Dataset and leader board please go to below link
https://datahack.analyticsvidhya.com/contest/practice-problem-age-detection/

#### Datasets structure
train 

  |-Train (folder contains training all images) 
  
  |-train.csv (Contains image names as ID's and class label which it belongs to)

test 

  |-Test (folder contains test all images) 
  
  |-test.csv (Contains image names as ID's)
  
### Journey
For this competition I have fine tuned the VGG16 model by adding a dense layer to VGG16 architechture and it gave 78.3% accuracy. Next I have started with feature extraction using pretrained VGG16 by removing top layer (only convolutions are used) and then applied GridSearch on extracted VGG16 features, it gave me 71.5% accuracy. Later I have tried feature extraction from ResNet50 pretrained model by removing top layer (only convolutions are used) and applied GridSearch on extracted ResNet50 features, it gave 79.7 accuracy. As no model crossed 80% accuracy to tweak parameters so I have decided to apply some preprocessing techniques on given datasets and created new datasets in HDF5 format. As I have upscaled the images in dataset so picked an architecture which will start with large size convolution i.e., AlexNet. Also applied mean normalization for R, G, B pixels while training and it gave 85.3% accuracy and I decided to tweak the parameters. Finaly the same model gave 88.53% accuracy for this problem after tweaking few things in architecture. I have used Relu activation (tried ELU but not worked well), Adam optimizer with best learning rate 1e-4 for this model. For more details on the model please go to age_pred_alexnet.ipynb. 

When I get time next I want to test fine tuned ResNet model and if that doesn't work want try ResNet or VGG16 in the place of AlexNet. But trainings takes huge cost as it needs good amount of GPU. 

I have used Deep Learning instance in Google Cloud Platform with four 16GB P100 GPU's. Each epoch took around 210-300 seconds.

