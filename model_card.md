# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** The input of the model is a 120x120 black and white image of a brain MRI scan.

**Output:** The output of the model are 4 probabilities of the image belonging to each class of the following: glioma, meningioma, notumor, pituarity. The model returns the class that has the highest probability.

**Model Architecture:** The model employs a CNN architecture with 3 convolutional layers, and 3 fully connected layers, as follows:
1) input layer (120x120 black & white image)
2) convolutional layer 1 > maxpooling > ReLu > batch normalization
3) convolutional layer 2 > maxpooling > ReLu > batch normalization
4) convolutional layer 3 > maxpooling > ReLu > batch normalization
5) fully connected layer 1 > ReLu
6) fully connected layer 2 > ReLu > droput
7) fully connected layer 3 > output



## Performance

The model's performance was analysed on a subset of brain MRI images, consisting of 2000 training images and 400 test images, which where taken randomly from the original data of 7023 images set described in data_sheet.md. The training contains 4 classes: gliomna (600 images), meningioma (600 images), notumor (400 images) and pituarity (400 images). Note that more training images were used for glioma and meningioma due to the their similarity and thus difficulty to tell apart. This set was used for training in 5 epochs and results. This reduced subset allowed for faster training and quicker comparison of metrics.

The model's accuracy was assessed on a test subset, consisting of 400 images, 100 of each class. The accuracy was measured based on the overall accuracy, i.e. number of instances when the model correctly predicted the class. This metric was used during hyperparameter optimisiation and CNN architecure engineering. The overalla accuracy varied depending on the hyperparameters used, and achieved a peak of 90% at one of the training settings during Bayesian Optimisation. The individual accuracies of each class were seen to always be the highest for notumor and pituarity, which are the most distinct cases. The final ridentifying of each class usGive a summary graph or metrics of how the model performs. After tens of Bayesina Optimisation iterations the final hyperparameters
The process of learning has been exposed in the appended .ipynb workboook. Remember to include how you are measuring the performance and what data you analysed it on. 

## Limitations

Outline the limitations of your model.

## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 
