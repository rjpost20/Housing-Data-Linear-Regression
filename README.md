# Phase 2 Project: *King County Housing Data Fair Price Model*

![Bird's eye view of a neighborhood](https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/Data/AdobeStock_296805446.jpeg?raw=true)

## By Ryan Posternak

### Links

Presentation slidedeck PDF:
https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/KC_Housing_Data_Analysis_Slides.pdf

<br>

## Overview and Business Understanding

The housing market has been on a wild ride the past few years. According to St. Louis Fed data, the median price of a U.S. home [increased from around $320,000 at the start of the Covid-19 pandemic in 2020 to over $425,000](https://fred.stlouisfed.org/series/MSPUS) as of this writing in mid-2022. With the rise in prices and furious competition for homes, especially in hot real estate markets (geographically speaking), individual homebuyers face a daunting task in trying to obtain a fair deal on a new home. The purpose of this analysis is to provide a sophisticated, data-driven product to assist homebuyers moving to King County, WA in determining a fair deal on their purchase of a new house, whether they are first-time buyers looking to start a family or retirees looking to settle down in their golden years.

Using the model, homebuyers will be able to input the features of their new house of interest and receive an estimated "fair price" based on the model. They can then use this fair price estimate to assist in their decision-making process. This will be the predictive value of the model.

While homebuyers moving to King County are the primary stakeholders for this analysis, the model could also be used by the county government of King County, in promotional material for the town or for their own analysis. Local real estate agencies may find value in the model as well.

<br>

## Understanding the Data

This dataset contains data on over 20,000 home sales in King County, WA, from May 2014 to May 2015. Each home sale has a unique ID, sale price, and date of the transaction, along with 18 categorical and numerical features on the structure of the house and its accompanying property and neighborhood.

<br>

## Exploratory Data Analysis and Data Cleaning

Initial exploratory data analysis revealed that the dataset contains 15 numerical features and six object (string) features. Three of the object features: 'view', 'condition', and 'grade', are ordinal categorical variables. Additionally, NaN (missing) values are present in the 'waterfront', 'view', and 'yr_renovated' columns, and there are some '?' values in the 'sqft_basement' column, which explains why it is of datatype object. A quick analysis of the numerical data showed some large outliers in bedrooms and bathrooms variables of the dataset, along with the variables relating to square footage of the structure and property.

A visualization of the relationship between variables using a correlation heatmap indicated that the features most highly correlated with sale price are square footage of living area in the house and number of bathrooms. There were no variables with any meaningful negative correlation with price, and many of the independent variables are highly correlated with each other.

![Heatmap data visualization](https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/Graphs/Presentation%20Images/Slide_5.jpeg?raw=true)

<br>

## Exploratory Data Analysis and Data Cleaning




