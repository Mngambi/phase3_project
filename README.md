# A MODEL TO PREDICT IF A CUSTOMER OF SYRIATEL WILL STOP USING THEIR SERVICES
## Overview
This project aims to develop a machine learning model to predict customer churn for Syriatel, a telecommunications company. The model will identify customers at risk of discontinuing their services, allowing Syriatel to implement targeted retention strategies and improve customer lifetime value.

## Business Understanding
SyriaTel faces a critical issue: customer churn. Subscribers discontinuing service leads to lost revenue and hinders the company's growth. To address this challenge, a comprehensive customer churn prediction model is proposed. This model will analyze customer data to identify those at high risk of churning. By recognizing these at-risk customers through predictive analytics, SyriaTel can take proactive measures to address their concerns and needs.

This data-driven approach aims not only to reduce churn but also to enhance customer lifetime value, increase revenue, and improve overall customer satisfaction. Key stakeholders—including the marketing team, customer service, and executive management—will be integral in implementing and benefiting from these insights

Our target audience for this project encompasses key decision-makers at Syriatel: the Management Team, Customer Service Department, and Marketing Department. This collaboration ensures we develop a customer churn prediction model that not only identifies at-risk customers but also translates into actionable insights for targeted retention strategies and improved customer service experiences.

## Problem Statement
Syriatel wants to predict whether a customer stops doing business with them in the future according to the data presented.

## Main objective
To develop a model which predicts if a customer of Syriatel will stop doing business with them

## Specific objectives
* To identify which data to be used during modelling
* To undertand and prepare the data for analysis
* To perform data analysis on the prepared data
* To develop a binary classification model that predicts if a customer stops business
* To evaluate the model findings and recommend actions to be done
  
# Data Understanding
The Dataset was acquired from Syriatel, a Telecommunications company. It contains 3333 rows and 21 columns, with the columns each having unique distinct names:

* state
* account length  
* area code 
* phone number
* international plan 
* voice mail plan
* number vmail messages 
* total day minutes
* total day calls  
* total day charge
* total eve minutes
* total eve calls  
* total eve charge 
* total night minutes 
* total night calls   
* total night charge
* total intl minutes
* total intl calls  
* total intl charge
* customer service calls 
* churn

## Data Preparation
After identifying the null, duplicate and outliers, we drop the unnecessary columns, which are state and phone number, and remail with a dataset with 3290 rows and 19 columns.

# Data Analysis
Here, we use the prepared data to perform analysis. We first begin with univariate analysis, which involves finding statistics such as mean , mode, standard deviation and variance

After, we perform bivariate analysis which involves finding the correlation between different columns using correlation coefficient. In the images below, there shows a basic pattern of how the data interact with each other.

![Calls vs charge](https://github.com/Mngambi/phase3_project/assets/92369455/8b5df5c8-a344-42fb-9836-f2d8b6d6638b)

![Calls vs minutes](https://github.com/Mngambi/phase3_project/assets/92369455/cf251962-84e1-4c1c-9f23-255c98e452db)

![Minutes vs charges](https://github.com/Mngambi/phase3_project/assets/92369455/b027345a-ed2f-4205-9504-3fa92657eea3)

![Day charge to churn](https://github.com/Mngambi/phase3_project/assets/92369455/1331799d-8972-4a3f-bc83-a1ed01c9df5f)

# Modelling
After performing analysis, we now move on to modelling. As this is a binary classification proble, we find the class imbalance using class imbalance ratio

![Class imbalance ratio](https://github.com/Mngambi/phase3_project/assets/92369455/30115bea-50d7-4a32-94ee-df6b2c90325a)

With a ratio of 5.84, we can conclude that the dataset is moderately imbalanced

There are various algorithms that can be used to model , but i have decided to use decision trees as it allows for easier intepretation , can handle both categorcal and numerical data, and is efficient to train. We first begin by separating the features and target variables, which in our case, the targer variable is the "churn" column  

Using a decision tree, we get the following metrics:
![Decision Trees summary](https://github.com/Mngambi/phase3_project/assets/92369455/d1288c3a-85c3-41ed-a784-eb87af7b930c)

A confusion matrix to visualize it better

![Decision tree Confusion Matrix](https://github.com/Mngambi/phase3_project/assets/92369455/35793cb3-f7e7-422e-b9e5-1acad9f4bfcf)

Next, we use a Random forest to see if there is any improvement. Here are the Metrics

![Random Forest Metrics](https://github.com/Mngambi/phase3_project/assets/92369455/49400435-d018-455a-b502-145de33c4bc3)

After tuning the decision tree, we acquire the metrics again to see if the accuracy changed

![Tuned Decision tree Metrics](https://github.com/Mngambi/phase3_project/assets/92369455/17f56418-0c04-4cd5-bbab-72ee29a1e582)

The confusion matrix:

![Tuned Decision Tree Matrix](https://github.com/Mngambi/phase3_project/assets/92369455/0eeb15ef-2105-4164-8f2a-9d43bbfb77a5)

# Model Evaluation
By comparing metrics between the 3 models, we can see that the base model, which was the decision tree, achieved an accuracy of 0.84, meaning the model was 84% accurate in its prediction.
As for the Random forest, it achieved an accuracy of 0.85, meaning it was 85% accurate. the Random forest uses Gridsearch to find the best parameters to ensure the most optimal solutions. Using the Best parameters, we can tune the decision tree that was modelled warlier with the new parameter and assign it as its own model to compare. 
After comparison, we can see the following metrics:

![Comparision Metrics](https://github.com/Mngambi/phase3_project/assets/92369455/7aa93b17-ea3f-4600-8ab0-6938c4ab8716)

To better visualize it, we can use a ROC AUC to visualize all 3 models. The closer the curve is to the top left, the better the performing model:

![ROC AUC](https://github.com/Mngambi/phase3_project/assets/92369455/dd5eb62f-8d6f-45c2-95fa-3b5d1eaedcf7)

# Recommendations
Possible recommendations include:

* Advertising for day customers - as they are the ones who are more likely to stay
* incentivize more people to use the service for long as the longer the minutes spent on the call, and therefore the service, leads to more retention
* Personalized offers, in that there will be a higher retention of customers as they will feel that the company is catering to their needs

# Next Steps

* Cost-Benefit Analysis - Examine the expenses associated with putting these suggestions into practice and weigh them against the possible income increases from client retention.

* A/B Testing - Use A/B testing to put selected strategies into practice, assess their efficacy, and identify which ones connect the most with the stakeholders



