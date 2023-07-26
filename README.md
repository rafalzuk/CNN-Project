# CNN-Project
The CNN-Project is a project developed for educational purposes within the realm of ML and AI. It utilised Bayesian Optimisation to tune 8 hyperparameters of a Convolutional Neural Network, which is used for brain MRI classification among 4 classes: glioma, meningioma, notumor, pituitary. Fully trained model obtains overall 95% accuracy.

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
The project uses Bayesian Optimisation (BO) and Convolutional Neuronal Networks (CNN), to classify brain MRI scans. It has been developed to quickly distinguish between scans depicting one of the following conditions: glioma, meningioma, no tumor, pituarity. The model captures complex patterns in the images in the process of learning. Later, when exposed to training sets, it obtained overall 95% accuracy, with even 99 % accuracy in classes such as no-tumor. The lower accuracy of about 93% was observed among the meningioma and glioma, which are the most frequently confused tumors in this study, due to their strong visual similarity in certain projections. Utilisation of such techniques in critical medical fields can an accelerate and improve the accuracy of diagnosis, and assist doctors with their assessment, particularly in areas with limited health care. Early detection and classification of brain tumors is an important research domain in the field of medical imaging and accordingly helps in selecting the most convenient treatment method to save patient's life.

## DATA
The dataset used in this project consists of approximately 6000 training and 1200 testing images (in black and white) of various brain MRI scans, in various conditions, mostly with tumors. The dataset has been downlaoded from https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset [10.34740/kaggle/dsv/2645886]. A subset of the available data (1800 training & 400 testing images) has been pre-processed and used for BO optimisation to speed it up, while for final training a larger subset, also pre-processed (4800 training and 1200 testing images) was used to obtain higher accuracy.

## MODEL 
The model used for this task is a CNN, made up of 3 convolutional layers and 3 fully connected layers (including output) with approx. 500,000 parameters. CNN model has been chosen for this task becuase of it good capabilities to analyse images and infer complex patterns. The model contains such transformations as: pooling, ReLu function, batch normalisation, dropout.

## HYPERPARAMETER OPTIMSATION
The project contains several hyperparameters, some of them were tuned manually by iterative observations with use of knowledge and good judgement, while some using BO optimisation. The total number of all hyperparameters was too large to use BO for all of them.

a) hyperparameters that have been set by iterative manual testing and observations, reinforced with human understanding:
- batch size (set and fixed to 4 for all)
- images resolutions (set and fixed at 120x120 pixels)
- number of convolutional layers (set and fixed at 3)
- number of fully connected layers (set and fixed at 3 including the output layer)
- pooling size (set and fixed at 2)
- number of epochs (during BO optimisation set to 5 for faster iterations, while for final training set to 25)
- dropout (during BO optimisation set to 0 to reduce stochasticity/irregularity of optimisation, while in final training set to 0.2)
  
b) hyperparameters optimised with Bayesian Optimisation:
- convolutional layer 1, number of maps
- convolutional layer 1, kernel size
- convolutional layer 2, number of maps
- convolutional layer 2, kernel size
- convolutional layer 3, number of maps
- convolutional layer 3, kernel size
- neurons in fully connected layer 1
- neurons in fully connected layer 2

## RESULTS
The fully trained model incorporating the optimised hyperparameters, obtains overall 96% accuracy in distinguishing between the 4 types of brain conditions, with even 99 % accuracy in classes such as no-tumor. The lower accuracy of about 93% is obtained in distinsguishing between the meningioma and glioma, which are the most frequently confused tumors in this study, due to their strong visual similarity in certain projections (particularly in images from top).
