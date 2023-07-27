# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** The input of the model is a 120x120 black and white image of a brain MRI scan.

**Output:** The output of the model are 4 probabilities of the image belonging to each class of the following: glioma, meningioma, notumor, pituarity. The model returns the class that has the highest probability.

**Model Architecture:** The model employs a CNN architecture with 3 convolutional layers:


## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

## Limitations

Outline the limitations of your model.

## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 
