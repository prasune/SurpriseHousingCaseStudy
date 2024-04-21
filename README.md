# Surprise Housing Case Study - Advanced Regression (Ridge & Lasso) 
> A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price.


## Table of Contents
* [General Info](#general-information)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
### Problem Statement
A US-based housing company named Surprise Housing has decided to enter the Australian market. 
The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia.

The company is looking at prospective properties to buy to enter the market. You are required to build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.

The company wants to know:

* Which variables are significant in predicting the price of a house

* How well those variables describe the price of a house.


Also, determine the optimal value of lambda for ridge and lasso regression.


### Business Goal:
You are required to model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.



<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
* The housing data is read and analyzed and observations are noted.
* SalePrice is the target column here.
* Outliers are detected and updated
* The columns with all zero values and all same constant values are removed after outlier detection
* Columns with very low number of missing values are removed
* Based on data dictionary, missing value of category variables are added
* New features are extracted, redundant features dropped and categorical features are encoded accordingly.
* Dummy variables were created for categorical variables and it increased the number of features greatly, highly imbalanced columns were dropped.
* Trend of SalePrice is observed for change in individual features.

* Target variable SalePrice is right skewed. Natural log of the same is Normal distributed, hence for model building, natural log of SalePrice is considered.

* Then the data in split into train and test data and feature scaling is performed.
* Top 45 features are selected through RFE and adjusted R*square. 45 features : 
['LotArea', 'OverallQual', 'OverallCond', 'YearBuilt', 'BsmtQual', 'BsmtFinSF1', 'BsmtUnfSF', 'HeatingQC', 'CentralAir', '1stFlrSF', '2ndFlrSF', 'BsmtFullBath', 'FullBath', 'HalfBath', 'KitchenQual', 'Functional', 'Fireplaces', 'GarageArea', 'GarageQual', 'MSZoning_RL', 'Neighborhood_Edwards', 'Neighborhood_NAmes', 'Neighborhood_NWAmes', 'Neighborhood_NridgHt', 'Neighborhood_Somerst', 'Condition1_Feedr', 'Condition1_Norm', 'RoofStyle_Gable', 'RoofStyle_Hip', 'Exterior1st_HdBoard', 'Exterior1st_Plywood', 'Exterior1st_Wd Sdng', 'Exterior2nd_HdBoard', 'Exterior2nd_Plywood', 'Exterior2nd_VinylSd', 'Exterior2nd_Wd Sdng', 'MasVnrType_BrkFace', 'MasVnrType_Not_applicable', 'MasVnrType_Stone', 'Foundation_PConc', 'Heating_GasA', 'GarageType_Attchd', 'GarageType_Detchd', 'GarageType_Not_applicable', 'PavedDrive_Y', 'SaleCondition_Normal', 'SaleCondition_Partial']


* Ridge and Lasso Regression Model are built with optimum alpha calculated in GridSearchCV method.
Optimum alpha = 10.0 for ridge and 0.001 for lasso model.

* Model evaluation is done with R2 score and Root Mean Square Error.
* Lasso Regression is chosen as final model for having slightly better R*square value on test data.
* Out of 45 features in the final model, top 10 features in order of descending importance are ['1stFlrSF', '2ndFlrSF', 'OverallQual', 'OverallCond', 'LotArea', 'SaleCondition_Partial', 'BsmtFinSF1', 'BsmtQual', 'SaleCondition_Normal', 'MSZoning_RL']

* Model coefficients are listed in a table along with the corresponding features
* Predicted value of SalePrice is transformed into its original scale by performing antilog. 

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- pandas
- seaborn
- matplotlib
- statsmodels
- sci-kit learn
- scipy


## Contact
Created by [@prasune] - feel free to contact me!


