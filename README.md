# Covid - 19 Prediction Using Respiratory Disease Images Imported in a Mobile Application


Project ID : B21 - CAP00430

Project Name : Covid - 19 Prediction Using Respiratory Disease Images Imported in a Mobile Application 

Project Themes : Healthcare

Mobile Development : wahyuirgan/Predict-19(github.com)

Github Flask : haidarfahmii/predict-covid-model(github.com)

![alt text](https://github.com/wahyuirgan/Predict-19/blob/mobile-dev/app/src/main/ic_launcher-playstore.png?raw=true)




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

# Saliency Maps 

Grad-CAM is a more versatile version of CAM that can produce visual explanations for any arbitrary CNN, even if the network contains a stack of fully connected layers too (e.g. the VGG networks).  So it is applicable to only the CNN architectures that perform global average pooling over convolutional maps immediately before prediction (i.e conv feature maps → global average pooling → softmax layer). By using the model interpretability we will be able to figure out why the predictions not supposed we want to be.

![alt_text](https://camo.githubusercontent.com/6cfc4c55fc42379fb9866f5c2bf410d49805a435e57c6d3116263b20d8c08d1d/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f797243747755343566344e6461387676494258493459694a46717679425347655a747a7a424d2d4f65713034797366676c6257457469486341526f444f67766e6e5674784d41705452485a4b5a45787a5a694d646f6b614d424164494e756f666535776d5f5a46555755422d4f2d5a5071663757337761525241444879454e59734a6b2d562d5737)

[![message-Image-1623236142170.jpg](https://i.postimg.cc/wMpNwph9/message-Image-1623236142170.jpg)](https://postimg.cc/VrK5N2Gh)

[![message-Image-1623236232306.jpg](https://i.postimg.cc/CLvZqD6h/message-Image-1623236232306.jpg)](https://postimg.cc/ykZYqJHt)


# Oxygen Avaibility decision
The decision that have been made to determine whether someone is COVID - 19 can made a life saver decision if right action taken by, especially for people who have organ complication and other acute respiratory disease, we try to make a decision making algorithm based on several classes by using classification to generate more better decision, combined with ct image scan it can mitigate current death toll.























