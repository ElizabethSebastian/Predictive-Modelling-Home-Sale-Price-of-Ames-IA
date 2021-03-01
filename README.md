# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Predictive Modelling:Home Sale Price of Ames, IA

### Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

### Problem Statement

To predict as accurately as possible the sale price of a house based on the Ames Housing Dataset using regression techniques enhanced by feature engineering and regularization. Additionally, the model should also help to perform inferential learning to provide homeowners and investors with recommendation on the features that would fetch good sale price and those that would hurt the sale price.

### Executive Summary

#### Background
The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses.

#### Objective:
1. Use EDA, visualization, data cleaning, preprocessing, and linear models to predict home prices given the features of the home.<br> 
2. Interpret linear models to find out what features add value to a home.<br>
3. Using Kaggle to practice the modeling process.<br>
4. Provide business insights through reporting and presentation.

#### Modeling Process and Evaluation
Data was downloaded from Kaggle. Data was divided into training data for the purpose of training the model for predicting the house price and test data for the purpose testing the accuracy of the model's prediction. 

##### Data Import and Classification of Variables
Both training and testing datasets are imported and the features are classified based on its type. 
Out of the 80 features, 23 were nominal, 23 were ordinal, 14 were discrete and 20 were continuous. 

##### Data Cleaning
Data cleaning was performed on both training and test set and the major steps are as follows:<br>

1. Dropped off columns with huge number of null values i.e. more than 250 cell with null values after checking their correlation to sale price. Columns falling into this category are : Lot Frontage, Alley, FireplaceQu, Pool Qc, Misc Features, Fence<br>
2. Replaced values that are non existent with null values. Used 0 for numeric columns and NA for categorical columns<br>
3. Related/ dependent columns were dropped off : Basement finished sqft1, Basement finished sqft2 and Basement unfinished sqft,total Basement square feet, 1st floor square feet and 2nd floor square feet are redundant as these are summed up and stored in column : Total Sqft.<br>
4. Removed outliers that may distort model prediction. 

##### Exploratory Data Analysis(EDA)
The following steps were involved in EDA:
1. Used heatmap to display the most correlated features with sale price.<br>
2. Collinearity among fetaures were also checked.<br>
3. Checked the distribution of features using histograms.<br>
4. Normalized sale price to follow a normal distribution for the regressors to work better<br>

##### Preprocessing & Feature Engineering
Preprocessing & Feature Engineering involved:

1. Quantify Categorical Data<br>
2. Mapped Ordinal data with numerical values in the order of quality.<br>
3. Created some new features to better represent them. For example Year built and year sold were used to replace with property age.<br>
4. Train-test-split with 90% training set.<br>
5. Standardizing training sets.<br>

##### Model, Predict & Evaluate

1. Created 4 models - Linear Regression (LR), LR with regularization methods - Ridge, Lasso and Elastic Net.<br>
2. The models were measures with R-squared (relative measure of model fit) and RMSE (absolute measure of model fit).<br>
3. The higher the R-squared and lower the RMSE, the more accurate the model is. Both Lasso and Elastic Net perfomed very well and results of both the models were analysed.<br>
4. Both Lasso and Elastic Net was selected to predict sale price in test dataset and both the predictions were very close.<br>
5. The predicted saleprice was uploaded to Kaggle and scored RMSE Kaggle score of 22124.60916 which is the lowest thus far.<br>
6. The coefficients' information obtained from Lasso modeling can also be used for inferential learning resulting as recommendations to home owners on the features affecting the sale price of their property postively and negatively. 


### Data Dictionary

Data dictionary for the final set of features.

| Feature           | Type  | Description                                                                                    |
|-------------------|-------|------------------------------------------------------------------------------------------------|
| total_sf        | int   | Total square feet                                                                        |
|overall_qual      | int   | Overall quality - Rates the overall material and finish of the house  
|overall_cond        | int   | Rates the overall condition of the house                                             | 
|built_age         | float | Age of the property                                 |   
| bsmt_full_bath    | float | Basement full bathrooms                                    | remod/add_age       | int   | Age of any additional renovation done|                                   |
|bsmt_exposure     | int   | Refers to walkout or garden level walls                                                        |
 |lot_area          | int   | Lot size in square feet 
|bsmt_type1_unf   | int   | Rating of basement unfinished area                        |
|fireplace_qu      | int   | Fireplace quality 
|bsmt_qual         | int   | Basement quality - Evaluates the height of the basement                                     |kitchen_qual      | int   | Kitchen quality                                    |
|ms_zoning_C (all)      | int   | Indicates Commercial zoning classification of the sale                         |
| totrms abvgrd     | int   | Total rooms above grade (does not include bathrooms)  
| heating_qc        | int   | Heating quality and condition                                    |neighborhood_Crawfor     | int   | Crawfor neighborhood                                    |
|full_bath| float | Size of garage in square feet                                                                  |
| screen_porch     | int   | Interior finish of the garage                                                                  |
| bsmtfin_type_1_No      | int   | Garage quality                                                                                 |
| functional       | int   | Age of any additional renovation done|
| paved_drive       | int   | Heating quality and condition                    |                                                                    |
|kitchen_qual       |   int| Quality of Kitchen

Full data dictionary for the original Ames dataset [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

### Conclusions and Recommendations


Cleaning and preprocessing the data is extremely tedious work. But It was worth doing since the predictions of the saleprice was observed to be much accurate after that. 

Both Lasso and Elastic Net gave good R^2 score of 0.93% on unseen data. The data was analysed using both the models to predict the price. It should be notable that both the models predicted the sale price very accurately and rather close to each other.

Our models helped us also in feature selection by identifying features that strongly influences sale price both positively and negatively. It was observed that the features identified by both the models are more or less same. Thus we have addressed problem statement by developing a relatively accurate model to predict housing prices based on various features<br>
-  Top 3 features that can fetch higher sale price : Bigger houses, Overall material finish of the houses and Overall condition of the houses.<br>
- Features that may hurt the sale price : Age of the house, Age of renovation or additional work, Unfinished basement, Houses located in commercial zone<br>

With top features identifies, it is now more ideal and easy to explain to relevant stakeholders who include house owners and investors.. Ideally we would always want to have a model that is complex enough to fit all the points but still having enough simplicity to explain the model.

This model is a great first step to help our stakeholders to identify opportunities for investment. To be more helpful, the model needs retraining to include Landmrk, and it needs retraining to model price increases with time. Further investigation is needed regarding a small but significant number of very large residuals, which may lead to new insights in modeling.

