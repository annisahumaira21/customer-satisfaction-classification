# customer-satisfaction-classification : Project Overview

- this project using Invistico Airlines dataset.
- Customer give rating 1-5 to services of Invistico Airlines and conclude that customer satisfied or not.
- Clean data (fix missing values, duplicate data), replace 0 in rating services into median of each services.
- Do data preprocessing to optimize learning process of model
- Train model with 6 different algorithms and choose top 2 for next hyperparameter tuning
- Validate model with data test.

## Problem
- Invistico Airlines have dissatisfaction rate reached 45% of total customers.
- Invistico Airlines want to know which services most impact on dissatisfaction customer and improved it.
- With improvement services, hopefully can increase customer satisfaction rate

## Purpose
- to find out which services need to be improved and impact on increasing customer satisfaction with model prediction.

## Early Insight from Data
if we look at distribution of customers based on type of travel and class<br>

![alt text](https://github.com/annisahumaira21/customer-satisfaction-classtification/blob/main/distribution%20of%20customers.JPG)<br>

top 3 most of customers:
- Business travel - business class
- Personal travel - eco class
- Business travel - eco class

if we look at distribution of dissatisfied customer based on type of travel and class

![alt text](https://github.com/annisahumaira21/customer-satisfaction-classtification/blob/main/distribution%20of%20dissatisfied%20customer.JPG)<br>

as we can see, Business travel - Eco Class and Personal Travel - Eco Class have most dissatisfied customer and also have most customers at top 2 and top 3, so we will focus on this segments to do some service improvements. Now, we gonna see feature correlation of this segment to find out which services will be improved.

1. Business Travel - Eco Class

![alt text](https://github.com/annisahumaira21/customer-satisfaction-classtification/blob/main/feature%20corr%20bus-eco.JPG)<br>

the most correlated feature is seat comfort

2. Personal Travel - Eco Class

![alt text](https://github.com/annisahumaira21/customer-satisfaction-classtification/blob/main/feature%20corr%20pers-eco.JPG)<br>

the most correlated feature is inflight entertaiment

## Machine Learning Model
Before train the model, split the data into train set & test set (80:20). Trained the model with 6 different algorithms and evaluated them with Precision score. The reason is to reduce False Positive. In the end, model can minimized the wrong predictions than can lead to another issues like dissatisfied customer turn into satisfied customer. The model was trained with:

1. Logistic Regression
2. KNN
3. Decision Tree
4. AdaBoost
5. Random Forest
6. XGBoost

## Model Evaluation
The model were evaluated with Precision score. Choose the top 2 Precision score for the next hyperparameter tuning
| Model Eval | Random Forest | XGBoost |
| --- | --- | --- |
|Accuracy |0.96 | 0.96 |
|Precision |0.97 | 0.97 |
|Recall | 0.95 | 0.95 | 
|F1 Score | 0.96 | 0.96 | 
|AUC | 0.96 | 0.96 | 

After doing hypertuning, the result is:
| Model Eval | Random Forest | XGBoost |
| --- | --- | --- |
|Accuracy |0.96 | 0.96 |
|Precision |0.96 | 0.97 |
|Recall | 0.95 | 0.96 | 
|F1 Score | 0.96 | 0.96 | 
|AUC | 0.96 | 0.96 | 

Based on Precision Score, we choose XGBoost for the best model. Other than that, accuracy score between data training and data testing not much different, so we conclude that there is no overfitting. if we look at feature importance, top 2 features is Inflight Entertaiment and Seat Comfort looks like feature correlation of Business Travel - Eco Class and Personal Travel - Eco Class before. So, we will do some improvement for this features.

![alt text](https://github.com/annisahumaira21/customer-satisfaction-classtification/blob/main/feature%20importance%20XGBoost.JPG)<br>

## Insight

we will give recommendation to improve Seat Comfort in Business Travel - Eco Class and Inflight Entertaiment in Personal Travel - Eco Class, for example:
- Seat Comfort : renew seat cushion with full foam
- Inflight Entertaiment : provide Tablet PC, Netflix for watching movies, Spotify for listening musics, games and apps.

We assumed that customer satisfied with improvement of the services, and we will see impact on customer satisfaction rate

![alt text](https://github.com/annisahumaira21/customer-satisfaction-classtification/blob/main/improvement%20of%20customer%20satisfaction.JPG)<br>

from the graph we conclude that improvement of 2 features impact on increasing customer satisfaction from 54.7% to 67.6%
