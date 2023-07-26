# Datasheet 

## Motivation

This dataset is a combination of the following datasets: figshare, SARTAJ, dataset Br35H. This dataset contains 7023 images of human brain MRI images which are classified into 4 classes: glioma - meningioma - no tumor and pituitary. The original dataset was created for medical diagnostics and medical educational purposes and later aggregated and released for broader educational purposes including ML and AI.

Various entities have contributed to the creation of this dataset, yet are not explicitly mentioned in the source. In every probability, as it is the case with medical imaging, the data has been created by various health centres and hospitals during treatment of patients. No specific infrimary or country is mentioned. The data has been collected from various smaller sources and published on Kaggle by Msoud Nickparvar. No information regarding funding has been contained in the source.

 
## Composition

The dataset comprises of labelled black-and-white brain MRI scans grouped into 4 classes: glioma, meningioma, no tumor, pituarity. In total there are 7023 images, with approxiamtely 1700 samples of each class. Some of the images are said to be mislabelled. Images are in varying resolutions and aspect ratios and require unification pre-processing before being used. The dataset depicts data that can be considered confidential under the doctor-patient category.

## Collection process

Altough not explicity mentioned, it should come across as obvious that data was originally obtained from MRI scans of peoeples brains in hospitals. Whether it was done as part of a general study encompassing specific ethnicities or populations, or was just aggregated from casual brain scans is unknown. Sampling strategy and time frame is not mentioned.

## Preprocessing/cleaning/labelling

The data is provided as labelled images, distributed in 4 folders. The names of these folders serve as labels: glioma, meningioma, no tumor, pituarity. Before being used for the CNN model in this project, the data had to be standardised by bringing all images to common resolution and aspect ratio. Some images require cleaning as they may exhibit inadvertently wrong labelling. 
 
## Uses

The dataset can be used for various studies in the fields of medicine, ML, AI, and others.
- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? - No.
The dataset should not be used for any purpose that could express discrespect to those affected and portrayed in the images, e.g. forms of art.

## Distribution

The data has been distributed through Kaggle wesbite. It is distributed under CC0: Public Domain licence. No copyright information contained.

## Maintenance

The data is maintained by it publisher - Msoud Nickparvar, however it is not expected to be updated.

