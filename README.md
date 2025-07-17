# Telcom Churn Prediction

![alt text](images/AdobeStock_294948823.jpeg)

## Overview
Customer churn in the telcom industry is a big problem for service providers. As it is expensive to accuire new customers, keeping existing customers is a priority. This project aims to predict future churners so the company can take steps to retain them. Using company provided data we tried varuous Machine Learning models to 
make predictions, and chose the results from the best one. Our results show a recall score of .76

## Business Understanding
As it is very expensive for a telcom to accuire a new customer, every effort is made to retain it's existing customers. If we could identify customers that will leave the company can take steps to retain them. Even if there is a cost associated with the retention efforts, it is lower than the acquisition of a new customer.
Since there is a cost associated with losing a customer and getting a new one the company has determined the priority to be identifying all possible churners. For this reason we will use Recall score as our success metric.

## Data Understanding
The data set we used was provided by Kaggle. *https://www.kaggle.com/becksddf/churn-in-telecoms-dataset* 
The dataset contains information about customers of a telecom company, including their call history, 
account information, and whether they have churned. 

The data set has 3333 records with 21 attributes. Our feature engineering will add 2 additional attributes.
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

## Conslusion
Accquiring new customers is very expensive for a telcom services company. These companies have found that it is more cost effective to keep existing customers even if they have to offer incentives to those customers. A telcom company etasked us with predicting which of their customers might churn. Using an XGBoost model we were able to predict 74% of those customers which will churn.

The data provided by the telcom company was mostly user call data. We found this to be a limitation. Our reccomendation is to provide more demographic and other data from which we can use to do feature engineering and make better predictions.

Overall we were able to help the telcom company identify the majority of the churners, helpimg them retain those users and save money. In the future, possibly with more data, we can improve on these predictions and help save more money.

## Repository Structure
* README.md ---------> This file
* notebook.ipynb ----> Project Jupyter Notebook
* images ------------> Images used
* presentation.pdf --> Slide Presentation