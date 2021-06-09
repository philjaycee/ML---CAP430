# Covid - 19 Prediction Using Respiratory Disease Images Imported in a Mobile Application


Project ID : B21 - CAP00430

Project Name : Covid - 19 Prediction Using Respiratory Disease Images Imported in a Mobile Application 

Project Themes : Healthcare

Mobile Development : wahyuirgan/Predict-19(github.com)

Github Flask : haidarfahmii/predict-covid-model(github.com)




# Download the dataset

```
!wget https://md-datasets-cache-zipfiles-prod.s3.eu-west-1.amazonaws.com/jctsfj2sfn-1.zip
```


# Introduction

Coronavirus Disease (Covid-19). In 2020, a new type of coronavirus (SARS-CoV-2) was spread, called a disease called Coronavirus disease 2019 (COVID-19). This virus was discovered in Wuhan, China for the first time and has infected 90,308 people as of March 2, 2020. Common symptoms include fever, cough and difficulty breathing. Clinical syndrome is divided into uncomplicated, mild pneumonia and severe pneumonia. Specimen examination is taken from the throat swab and lower airway. Isolation was carried out on patients proven to be infected with Covid-19 to prevent wider spread.

Up until now COVID-19 case is still continuing and recorded on WHO Website on June 4, 2021, there have been 171,708,011 confirmed cases of COVID-19, including 3,697,151 deaths in the world, reported to WHO.


# Flowchart of the pipeline:

![alt text](https://raw.githubusercontent.com/ramkicse/covid19-chest-x-ray/master/readme_assets/flowchart.jpg)

# Dataset:
 
# Data Augmentation

Another way to mitigate data deficiency is data augmentation: from the limited training data, creating new image-label pairs and adding the synthesized pairs into the training set. Color Jitter, Scaling, Flip, Rotations and other affine transformations are typical. This makes the neural network exposed to a wide variety of variations and less likely to recognize unwanted characteristics in the data-set.

Data set preparation



To train a binary classification model for predicting whether an X-ray image is COVID or non-COVID, we collect 405 X Ray that are negative for COVID means Normal patient X-ray and 114 which are positive for covid19 and 423 pneumonia patient X-ray. We split the dataset into a train, validation,.

Table summarizes the number of COVID and Normal images in each set. All images are resized to 224x224. The hyperparameters are tuned on the validation set. The weight parameters in the networks were optimized using Adam. We evaluate our method using five metrics: (1) Accuracy; (2) Precision; (3) Recall; (4) F1 score; (5) Area under ROC curve (AUC).

Our dataset is an imbalance dataset, meaning the number of x-ray images in the training dataset for each class label is not balanced. Imbalanced classification refers to a classification predictive modeling problem where the number of examples in the training dataset for each class label is not balanced. That is, where the class distribution is not equal or close to equal, and is instead biased or skewed.




# Model Training
During the training we using the VGG16 architecture based pre - trained model. VGG16 pretrained model classified around 1000 classes and changed the classifier layers into 3 classes ( Normal, Covid-19, Pneumonia).

The technique used is transfer learning where a model trained on one task is repurposed for another task.

![image](https://user-images.githubusercontent.com/67178498/121296609-2828e200-c91b-11eb-9352-ac5a6b801137.png)


Train the model against our dataset for 100 epoch using Adam Optimizer with 0.001 learning rate.

[![message-Image-1623215586612.jpg](https://i.postimg.cc/W4RypSxD/message-Image-1623215586612.jpg)](https://postimg.cc/xXR5tGfY)
[![message-Image-1623215694938.jpg](https://i.postimg.cc/vB0Xnv2t/message-Image-1623215694938.jpg)](https://postimg.cc/G8skwvC4)


# Evaluation metrics 

Classification metrics

There are for type of outcome that would be occur
True positives are when you predict an observation belongs to a class and it actually does belong to that class.

True negatives are when you predict an observation does not belong to a class and it actually does not belong to that class.
False positives occur when you predict an observation belongs to a class when in reality it does not.
**False negatives **occur when you predict an observation does not belong to a class when in fact it does.

The four outcomes can be plot using confusion matrix:

DICT : 0 = Normal, 1 = COVID -19, 2 = Pneumonia
[![message-Image-1623214757509.jpg](https://i.postimg.cc/QNqTxtKh/message-Image-1623214757509.jpg)](https://postimg.cc/XXpJsngz)

Three main metrics used for classification models are precision, accuracy, and recall.
[![message-Image-1623224932462.jpg](https://i.postimg.cc/4xhjHY6K/message-Image-1623224932462.jpg)](https://postimg.cc/Xr4sT7D3)



# AUC - ROC Curve

AUC - ROC curve is a performance measurement for the classification problems at various threshold settings. ROC is a probability curve and AUC represents the degree or measure of separability. It tells how much the model is capable of distinguishing between classes. Higher the AUC, the better the model is at predicting 0s as 0s and 1s as 1s. By analogy, the Higher the AUC, the better the model is at distinguishing between patients with the disease and no disease.

[![message-Image-1623225069949.jpg](https://i.postimg.cc/RF7qGCwG/message-Image-1623225069949.jpg)](https://postimg.cc/R60MZBsn)

[![message-Image-1623225093783.jpg](https://i.postimg.cc/3rL3hDrm/message-Image-1623225093783.jpg)](https://postimg.cc/hh7kbvdt)

[![message-Image-1623225344675.jpg](https://i.postimg.cc/kMHLwNX1/message-Image-1623225344675.jpg)](https://postimg.cc/RqcPZHtK)

















