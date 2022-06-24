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

A baseline simple linear regression model was used as a benchmark to compare model iterations to. Models were judged primarily on their validated R-squared and root mean squared error (RMSE) values. Root mean squared error was used over mean absolute error because the former penalizes large errors in prediction to a greater extent.

<br>

## Understanding the Data

This dataset contains data on over 20,000 home sales in King County, WA, from May 2014 to May 2015. Each home sale has a unique ID, sale price (the dependent variable in this analysis), and date of the transaction, along with 18 categorical and numerical features on the structure of the house and its accompanying property and neighborhood.

<br>

## Exploratory Data Analysis and Data Cleaning

Initial exploratory data analysis revealed that the dataset contains 15 numerical features and six object (string) features. Three of the object features: 'view', 'condition', and 'grade', are ordinal categorical variables. Additionally, NaN (missing) values are present in the 'waterfront', 'view', and 'yr_renovated' columns, and there are some '?' values in the 'sqft_basement' column, which explains why it is of datatype object. A quick analysis of the numerical data showed some large outliers in bedrooms and bathrooms variables of the dataset, along with the variables relating to square footage of the structure and property.

A visualization of the relationship between variables using a correlation heatmap indicated that the features most highly correlated with sale price are square footage of living area in the house and number of bathrooms. There were no variables with any meaningful negative correlation with price, and many of the independent variables are highly correlated with each other.

![Heatmap data visualization](https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/Graphs/Presentation%20Images/Slide_5.jpeg?raw=true)

<br>

## Modeling and Regression Results

The baseline model was a simple linear regression between square feet of living space, the most correlated feature in the correlation heatmap, and sale price. It was a decently strong baseline model, accounting for just under half the variation in sale price with an R-squared of about 0.48 and a RMSE just north of $238k. Successive models, displayed below, incorporated a variety of techniques to improve model performance, including feature enginnering, one-hot encoding, log-transforming, creating interaction terms in polynomial form, and recursive feature elimination.

The final model, model 9, clocked in with an R-squared of 0.891 and an RMSE $115,719

![Model iterations 0 - 4](https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/Graphs/Presentation%20Images/Slide_6.jpeg?raw=true)

<br>

![Model iterations 5 - 9](https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/Graphs/Presentation%20Images/Slide_7.jpeg?raw=true)

The final model was assessed on the assumptions of linear regression - linearity, homoscedasticity, normality, and minimal multicollinearit - using visualizations and variance inflation factor scores. The model displayed an acceptable adherence to the assumptions, as expected given the high R-squared and RMSE scores, but there is room for improvement. Namely, the regression plot and residuals plot both showed that the model performed particularly poorly on predicting prices of home sales above $2M; nearly all the largest errors came from home sales above this threshold.

Additionally, the model tended to underpredict sale prices by a slight bit, especially at the higher end of home sales, and a high degree of multicollinearity was present in 25 of the independent variables.

![Residuals plot of predicted prices](https://github.com/rjpost20/King-County-Housing-Data-Linear-Regression/blob/main/Graphs/Residuals_predicted.png?raw=true)

<br>

## Conclusions, Recommendations, and Next Steps

Key conclusions and takeaways from this analysis include the fact that square footage of home space and zip code appear to be the most effective predictors of home sale price, at least in this dataset. Additionally, log transforming the target variable also boosted model performance by a sizeable margin.

Though the model is quite effective in its intended purpose - prediction - caution should be taken when using the model for inferential purposes. As noted from the regression assumptions analysis, a high degree of multicollinearity was present among the input variables, which can render coefficients and standard errors less reliable.

Recommendations of use for the analysis include using the model to set a benchmark price when searching for a home, but not expecting perfection among predictions. The RMSE was about $115k, which may seem high, but it's important to keep in mind that outliers carry outsized influence on RMSE scores. The mean absolute error would likely be potentially lower, which would be more reflective of the expected error the majority of homebuyers purchasing homes under $2M could expect.

Next steps and possible areas of improvement on the analysis include gathering more years of data to factor in any potential irregularities of the mid 2014-2015 housing market, and gathering more independent variables on the structure, property and area associated with the sale. Remaining points of interest include determining how the model would perform if outliers above $2M were taken out of the dataset, and how the inclusion of variables containing information on nearby points of interest could improve the model.
