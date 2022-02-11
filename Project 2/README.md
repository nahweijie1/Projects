# Project 2 - Ames Housing Data and Kaggle Challenge

## Problem Statement

As a researcher in the R&D team for a real estate firm whose main business activity is house flipping and property development which recently expanded into Ames, we were tasked to analyze the housing transaction data in Ames, to come up with recommendations on where the firm can focus its efforts in a bid to increase revenue.  

As the firm primarily engages in house flipping and property development, we will base our recommendations with regards to these activities.  

Additionally as a researcher, our R&D team would also like to find out which modelling approach yields the most accurate predicitions for sale prices.

## Dataset
The datasets used for their project are:
- [Ames Housing Data](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge)  

The dataset used consisted of over 2000 entries with 80 features for properties sold in Ames, Iowa between year 2006 to 2010.

To find out more about the information within the dataset and what each feature represents, you may visit this [site](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/data).

## Executive Summary

The study included a detailed look at the various neighborhood of Ames, as well as the different features and conditions relating to each part of the property.

It has been observed that the key features that affect the sale price of a property is overall quality, age, size and the neighborhood that the property is located. The feature that appears to add most value to a property is the overall quality of the house and size of the ground living area. The fact that quality has more correlation than condition is that condition defect progress with age while in contrast a quality property grows with age. While size of property is always one of the factor when it comes to measuring of price, we have observed that the greater the proportion of overall ground living area, the higher the sale price is. However, there's one features that can negatively affect the sale price of a property. In one of the correlation analysis, we saw that an increase in the age of the property leads to drop in sale price.

Homeowners can actually consider furnishing the overall quality and condition of the house before making a sale so that there's a higher probability that it can fetch a higher price. Since the heart of the home lies in the ground living area, it would be good to give a little update on the tiles and wall paint. Quality repairs to the fixtures and plumbing should also take into considerations as quality is one of the top positive correlation to sale price. Moreover if the property is located in areas like NorthRidge Heights and NorthRidge, homeowners can expect a higher sale price as compared to property in the other neighborhood.

It should be noted that this model will not generalize to a certain extent as the model only take into consideration of how property price is valuated in Aimes. The model includes the neighborhoods of Aimes in the modelling process hence it might not be applicable to other county or countries. However, in order to create a generalized model that can be used for any property, more datasets from various countries might be needed in the analysing process.  
### Overview of models:

|Model|Description|Regression Type|Precedent Model|Adj R-square|RMSE|
|-|-|-|-|-|-|
|Model 1|Regression with all regressors|Linear Regression|NA|0.90964|23606|
|Model 2|Regression with all regressors|Ridge|NA|0.90798|23479|
|Model 3|Regression with all regressors|Lasso|NA|0.90925|23344|
|Model 4|Regression with all regressors|ElasticNet|NA|0.90492|24335|  

- Note that Precedent Model indicates the model that the current model is built on top of.

## Contents:
 
- [Data Import & Cleaning](#1.Data-Import-and-Cleaning)
- [Exploratory Data Analysis + Feature Engineering](#2.EDA-&-Feature-Engineering)
- [Data Visualization](#3.Data-Visualization)
- [Data Modelling](#4.Data-Modelling)
- [Conclusions and Recommendations](#5.Conclusions-and-Recommendations)