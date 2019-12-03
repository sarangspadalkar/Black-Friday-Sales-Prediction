# Black Friday Purchase Amount Prediction

This repository contains data analysis of Black Friday purchase amount.

# Table Of Contents
  - [Project Introduction](#project-introduction)
  - [Data and Source Description](#data-and-source-description)
  - [Application of the CRISP-DM Process](#application-of-the-crisp-dm-process)
    <!-- - [Domain Knowledge](#domain-knowledge)
    - [Data Understanding and EDA](#data-understanding-and-eda)
    - [Data Preparation](#data-preparation)
    - [Machine Learning](#machine-learning)
    - [Evaluation](#evaluation)
    - [Conclusion](#conclusion) -->
  - [Conclusion](#conclusion) 


## Project Introduction
Black Friday is the day after American Thanksgiving, meaning the retailers often heavily promote their stores and markdown prices to entice shoppers to buy products both online and offline. Retailers have the freedom to set their Black Friday deals anyway they’d like to better entice purchases. So the major challenge for a Retail store or eCommerce business is to choose product price such that they get maximum profit at the end of the sales. Our project deals with determining the product prices based on the historical retail store sales data. After generating the predictions, our model will help the retail store to decide the price of the products to earn more profits.

## Data and Source Description
The dataset is acquired from an online data analytics hackathon hosted by [Analytics Vidhya](https://datahack.analyticsvidhya.com/contest/black-friday/). The aim of the platform is to become a complete portal serving all knowledge and career needs of Data Science Professionals. The data contained features like age, gender, marital status, categories of products purchased, city demographics, etc. The data consists of 12 columns and 550068 records. Our model will be predicting the purchase amount of the products.

## Application of the CRISP-DM Process

* **Business Knowledge**
  * The challenge is to predict the purchase prices of various products purchased by customers based on historical purchase patterns. The data contains features like age, gender, marital status, categories of products purchased, city demographics, etc. This model will help the retail stores to decide the prices of the products for the upcoming Black Friday sales.

* **Data Understanding**  
  * We used different data visualization and feature engineering techniques to extract insightful trends from the dataset. While performing feature engineering, we have added a few extra columns which give us more insights about the features.
    * **User_Count:** Number of observations of the user 
    * **Product_Count:** Number of observations of the product
    * **Product_Category_Count:** Number of product categories for the Product.
    * **Binned_Age:** Binning of the Age column into different insightful categories.
* **EDA:**   
Below are the observations which we have made from the data visualization done as part of the Data Understanding process.
  * Approximately, 75% of the number of purchases are made by Male users and rest of the 25% is done by female users. This tells us the Male consumers are the major contributors to the number of sales for the retail store.
  * When we combined Gender and Marital_Status for analysis, we came to know that Single Men spend the most during the Black Friday. It also tells that Men tend to spend less once they are married. It maybe because of the added responsibilities.
  * Then we did our analysis for Age features, here the column we designed as part of feature engineering Binned_Age was very helpful. We observed the consumers who belong to the age group 25-40 tend to spend the most. The effect of marriage remains the same, ie. the same age group spends less once they are married. Understandably, Teenagers and Elderly people spend the least.
  * There is an interesting column Stay_In_Current_City_Years, after analyzing this column we came to know the people who have spent 1 year in the city tend to spend the most. This is understandable as, people who have spent more than 4 years in the city are generally well settled and are less interested in buying new things as compared to the people new to the city, who tend to buy more.
  * The people having occupation as “Occupation 4”, are the major contributor's to the purchase amount. The people who are having occupation under “Occupation 8” are people who spend less. It can be inferred that the "Occupation 4" is one of the high paying jobs. When we combine this column with the Binned_Age Column, the age group 18-25 working under Occupation 4 are the people who spend the most. These are the young people who have high paying jobs and have the liberty to spend more.
  * Now we did product-based analysis, the most brought product was the product with Product Id: P00265242. This product was bought 1880 times. Then we, examined in which city the product was purchased to our surprise, even though the city B is majorly responsible for the overall sales income, but when it comes to the above product, it majorly purchased in the city C. The user with the User ID: 1001680 was the person who bought the most number of products (1026 products)

* **Data Preparation**
  * Fortunately, the dataset was clean and had no missing values. However, as part of Feature Engineering, we had to perform a few modifications to the original features of the dataset. 
  * The occupation feature had numerical values, which we transformed into an understandable string by adding word Occupation to the numerical values.
  * The Age column had age ranges, which had very broad classification of the ages, which would have been less fruitful, so we replaced it with random age values in that specific age group. 
  * We also transformed the Marital_Status column, as it had 1 and 0 numerical values, so we assigned 1 as Married and 0 as Single. The major reason behind eliminating these numerical values as they me affect the model’s prediction ability as our target variable is numerical.

* **Modeling Phase**
  * We are planning to implement the supervised model as we are aware of the target variable. The target variable can be predicted using basic Linear regression models and Random forests, which are known to have high accuracies. 
  * We can use Ensemble methods to use a combination of the above models, at this stage we have not implemented these models, this decision can be made after implementing those models individually and analyzing their performance parameters. 
  * We are also planning to implement clustering on the occupation column, as the column has very diverse values. Association rules machine learning method is also a feasible option to get relationships between the variables.

* **Evaluation**
  * We would be evaluating the models on the basis of the performance parameters such as Mean-squared errors, Model scores. We are planning to eliminate the User_ID and Product_ID columns while performing the predictions.

## Conclusion
  Our project deals with determining the product prices based on the historical retail store sales data. After generating the predictions, our model will help the retail store to decide optimal prices of the products to earn more profits on the upcoming Black Friday.  