## Project 2 Report
**Date:** 5/2/2024  
**Team 12:** Jakob Kindle, Alejandro Mirafuentes, Samuel Nicklaus, Lane Swartzendruber

### Title: Utilizing Transfer Learning for Image Classification of Sports

### Authors:
- Jakob Kindle
- Alejandro Mirafuentes
- Samuel Nicklaus
- Lane Swartzendruber

## Introduction
In this project, our team focused on classifying images into the sports categories: Football, Basketball, Hockey, Volleyball, and Baseball respectively. We did this by following the transfer learning tutorial (which we go into more detail later) and used a dataset posted on Kaggle.

## Methods: Approach
For our project, we used a modified version of the skorch transfer learning tutorial and a PyTorch example. While we did not use the PyTorch example, it was a good resource for seeing a more in-depth look at transfer learning. Some of the modifications we made in the skorch tutorial to fit our data include:

- Deleted the Preparations section, as our data was already downloaded and in their respective folders.
- Changed the data directory to just data instead of datasets/hymenoptera_data.
- Changed the module__output_features from 2 to 5.
- Added a class variable to NeuralNetClassifier that outlined the sports we were predicting.
- Changed device from cuda to cpu (since we were running it locally).

## Methods: Data
The dataset we used is based on an existing dataset on Kaggle. The original dataset was a collection of sports images covering 100 different sports. Images were already formatted in a 224x224x3 jpg format and the data was pre-separated into train, test, and valid directories. The original dataset had 13,493 train images, 500 test images, and 500 validate images.

For our own data, we tried to collect images off of Google that were more recent than the dataset to ensure we were not repeating images. The images from the dataset were taken at least a year ago, so we attempted to grab photos that were taken in the last year. We mostly grabbed photos from professional leagues (NBA, MLB, etc.) or from Iowa College Games.

## Methods: Training/Validation
We took the Kaggle dataset and shrunk it down by picking only 5 of the 100 sports to fit our model on. This left us with the sports Baseball, Basketball, Football, Hockey, and Volleyball. One of the initial problems we ran into with shrinking the dataset was that the total number of validations was too small, where we only had 25 images total, which is not ideal. To fix this, we moved all the test images into the validation folder, along with some of the training images. The final train/validation split for the sports are as follows:

- **Basketball:** 108 Training Images, 71 Validation Images
- **Baseball:** 105 Training Images, 79 Validation Images
- **Football:** 104 Training Images, 97 Validation Images
- **Hockey:** 108 Training Images, 74 Validation Images
- **Volleyball:** 108 Training Images, 44 Validation Images

After we made this split, we fit the model against the test set and ran it against the validation set using the net.fit method. After we got a baseline, we adjusted some of the parameters of the NeuralNetClassifier such as max_epochs, batch_size, and learning rate (lr). Our best model produced a 95.07% accuracy on the validation set with the following parameters: Epoch: 12, lr: 0.0001, batch size: 4.

## Methods: Testing
For our testing set, we took 5 images from each sport. Overall, our model correctly predicted 23/25 images, which is an accuracy of 92%. Below is a breakdown of our images and what the model predicted.

## Discussion/Conclusion
Our project demonstrated a good example of transfer learning for classifying images into five sports categories, achieving a validation accuracy of 95.07% and a testing accuracy of 92%. This project was actually easier for us than project one due to the model being pre-trained as well as us picking a more detailed dataset.

As for the experience of completing the project, we think it was laid out well and was a good way for us to get hands-on experience with going through the process of adapting an existing model to our needs. This project gives us the tools to develop more complex solutions to ML problems by using these pre-trained models. We wouldn’t really change anything about the project.

## Disclosure
N/A
```
