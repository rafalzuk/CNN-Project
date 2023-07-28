# Model Card


## Model Description

**Input:** The input of the model is a 120x120 black and white image of a brain MRI scan.

**Output:** The output of the model is a 4-dimensional vectors containing 4 probabilities of the image belonging to each class of the following: glioma, meningioma, notumor, pituarity. The model only shows and returns the class that has the highest probability.

**Model Architecture:** The model employs a CNN architecture with 3 convolutional layers, and 3 fully connected layers, as follows:
1) input layer (120x120 black & white image)
2) convolutional layer 1 > maxpooling > ReLu > batch normalization
3) convolutional layer 2 > maxpooling > ReLu > batch normalization
4) convolutional layer 3 > maxpooling > ReLu > batch normalization
5) fully connected layer 1 > ReLu
6) fully connected layer 2 > ReLu > droput
7) fully connected layer 3 > output

## Initial Performance

The model's performance was analysed on a subset of brain MRI images, consisting of 2000 training images and 400 test images, which where taken randomly from the original data of 7023 images set described in data_sheet.md. The training contains 4 classes: gliomna (600 images), meningioma (600 images), notumor (400 images) and pituarity (400 images). Note that more training images were used for glioma and meningioma due to the their similarity and thus difficulty to tell apart. This set was used for training in 5 epochs and results. This reduced subset allowed for faster training and quicker comparison of metrics.

The model's accuracy was first assessed on a test subset, consisting of 400 images, 100 of each class. The accuracy was measured based on the overall accuracy, i.e. number of instances when the model correctly predicted the class. This metric was used during hyperparameter optimisiation and CNN architecure engineering. The overalla accuracy varied depending on the hyperparameters used, and achieved a peak of 90% at one of the training settings during Bayesian Optimisation. This corresponded to individual accuracies of: glioma (91%), meningioma (81%), notumor (91%), pituarity (97%). The individual accuracies of each class were seen to always be the highest for notumor and pituarity, which are visually the most distinct cases. The process of learning and training convergence has been exposed in the appended .ipynb workboook. Below is summarised a final parameters of the model (some of them  obtained with Bayesian Optimisation), which used in the final (full) training of the model.

a) Hyperparameters that have been set by iterative manual testing and observations, reinforced with human understanding:
batch size (set and fixed to 4)
images resolutions (set and fixed at 120x120 pixels)
number of convolutional layers (set and fixed at 3)
number of fully connected layers (set and fixed at 3 including the output layer)
pooling size (set and fixed at 2)
number of epochs (during BO optimisation set to 5 for faster iterations, while for final training set to 25)
dropout (during BO optimisation set to 0 to reduce stochasticity/irregularity of optimisation, while in final training set to 0.2)

b) Final hyperparameters optimised with Bayesian Optimisation:
convolutional layer 1, number of maps: 14
convolutional layer 1, kernel size: 3x3
convolutional layer 2, number of maps: 20
convolutional layer 2, kernel size: 2x2
convolutional layer 3, number of maps: 30
convolutional layer 3, kernel size: 3x3
neurons in fully connected layer 1: 116
neurons in fully connected layer 2: 72

## Final Performance

Final (full) training of the model was set to last 25 epochs and used the above parameters (which were obtained after tens of iterations of Bayesian Optimisation). The dataset used for full training was larger than before and consisted of: gliomna (1300 images), meningioma (1300 images), notumor (1100 images) and pituarity (1100 images). As before, the glioma and meningioma were sampled more profusely becuase they are harder to discern. The final testing set consisted of 1200 images, 300 of each class. The model achived the overall accuracy of 95% and individual accuracies of: glioma (93%), meningioma (93%), notumor (98%), pituarity (99%).

## Limitations

The model is limited to predicting only 1 of the following four classes: glioma, meningioma, notumor, pituarity. Therefore, it would produce incomplete diagnosis in cases with several types of tumor, by predicting only the most probable one. The model cannot detect other types of brain tumors of diseases. Moreover, the model is best suited to capturing small- to medium -sized tumors, as larger ones may not be contextually captured. Orientation of the brain in the image may skew the prediction - the image should best be either from the front or top, but that depends on the tumor type. Gliomas and meningiomas could be confused with one another in top projection, yet that also depends on the diversity of the training data, not just the model itself. Moreover, blurr, occlusion, oversaturation could reduce the prediction accuracy. At last, individual characteristics of the brain, depending on ethnicity or nature, may confuse the model, so the image tested should ideally belong to the same race as the majority of the images used for training.

## Trade-offs

The model was seen to underperform in images of glioma and meningioma, due to their complex visual nature. Lumps of tumor in these cases may appear similar and are characterised mainly by their relative positions with respect to the skull (meningioma typically closer to skull). Furthermore, performance issues amplifying this visual similarity may occur with MRI scans made from top, i.e. above the head. In this projection, meningioma, at the top of the skull may appear in the middle of the image, which could be confused with a glioma, which typically occurs inside the central parts of the brain, or in fact anywhere. Thus, the model may confuse these 2 tumors depending on their size and location, as well as image projection. Moreover, it was noted that very large lumps of tumor (spanning approximately over 30% of brain scans, may be misclassifeid as no tumor at all, implying that the model loses context with very large objects. At last, MRI image artifacts, like discoloration, may be confused for a tumor, even in cases of a healthy brain.
