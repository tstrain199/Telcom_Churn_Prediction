# Telcom Churn Prediction

## Overview
Customer churn in the telcom industry is a big problem for service providers. As it is expensive to accuire new customers, keeping existing customers is a priority. This project aims to predict future churners so the company can take steps to retain them. Using company provided data we tried varuous Machine Learning models to 
make predictions, and chose the results from the best one. Our results show a recall score of .76

## Business Understanding
As it is very expensive for a telcom to accuire a new customer, every effort is made to retain it's existing customers. If we could identify customers that will leave the company can take steps to retain them. Even if there is a cost associated with the retention efforts, it is lower than the acquisition of a new customer.
Since there is a cost associated with losing a customer and getting a new one the company has determined the priority to be identifying all possible churners. For this reason we will use Recall score as our success metric.

## Data Understanding
The data set we used was provided by Kaggle. *https://www.kaggle.com/becksddf/churn-in-telecoms-dataset* 
The dataset contains information about customers of a telecom company, including their demographics, 
account information, and whether they have churned (i.e., stopped using the service). 

The data set have 3333 records with 21 attributes. Our feature engineering will add 2 additional attributes.
There are no missing values in the data set. However there is a data imbalance with poisitive cases (customers 
that churned) being only 14% of the total records.

# Model 1 Decision Tree
For the first model we've use a DecisionTree classifier with a max depth of 8. This prodiced better results than a max depth of 10.
For the target attribute this produced a recall score of .64

## Model 2 XGBoost
Here we used an untrained XGBoost model with a max depth of 8, 100 estimators and a learning rate of .1
This model produced a target recall score of .72

## Model 3 MLP Classifier
The MLP Classifier may work with some tabular data, but we saw poor results in precision and recall.

## Tuned XGBoost model
By tuning the XGBoost model we were able to improve on the target metric. Using a learning rate of .2, a max depth of 10 and 100 estimators this model had a recall of .74

## Evaluation
To evaluate the results we use a 2x2 confusion matrix, precision and recall scores. Our mandate here was to identify actual churners we focused on the recall score. The model with the best recall score was the Tuned XGBoost model with a recall of 74%.