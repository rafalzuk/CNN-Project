# CNN-Project
The project uses Bayesian Optimisation to tune 8 hyperparameters of a Convolutional Neural Network, which is used for brain MRI classification among 4 classes: glioma, meningioma, notumor, pituitary. Fully trained model obtains overall 96% accuracy.

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
The project uses Bayesian Optimisation (BO) and Convolutional Neuronal Networks (CNN), to classify brain MRI scans. With over 96% accuracy, it can distinguish between scans depicting: glioma, meningioma, no tumor, pituarity. Utilisation of such techniques in critical medical fields can an accelerate and improve the accuracy of diagnosis, and assist doctors with their assessment, particularly in areas with limited health care.

## DATA
The dataset used in this project consists of approximately 6000 training and 1200 testing images (in black and white) of various brain MRI scans, in various conditions, mostly with tumors. The dataset has been downlaoded from https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset. [10.34740/kaggle/dsv/2645886]. A subset of the available data (1800 traing & 400 testing images) has been preprocessed and used for BO optimisation for speed it up, while for final training a larger subset, also pre-processed (4800 training and 1200 testing images) was used to obtain higher accuracy.

## MODEL 
The model used for this task is a CNN, made up of 3 convolutional layers and 3 fully connected layers (including output) with approx. 500,000 parameters. CNN model has been chosen for this task becuase of it good capabilities to analyse images and infer complex patterns. 

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
The fully trained model incorporating the optimised hyperparameters, obtains overall 96% accuracy in distinguishing between the 4 types of brain conditions, with even 99 % accuracy in classes such as no-tumor.
