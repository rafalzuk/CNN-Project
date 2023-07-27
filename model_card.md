# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** The input of the model is a 120x120 black and white image of a brain MRI scan.

**Output:** The output of the model are 4 probabilities of the image belonging to each class of the following: glioma, meningioma, notumor, pituarity. The model returns the class that has the highest probability.

**Model Architecture:** The model employs a CNN architecture with 3 convolutional layers, and 3 fully connected layers, as follows:
1) ipnut > convolutional layer 1 > maxpooling > ReLu > batch normalization
2) convolutional layer 2 > maxpooling > ReLu > batch normalization
3) convolutional layer 3 > maxpooling > ReLu > batch normalization
2) fully connected layer 1 > ReLu
2) fully connected layer 2 > ReLu > droput
2) fully connected layer 3 > output



## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

## Limitations

Outline the limitations of your model.

## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 
