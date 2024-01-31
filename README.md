# Project: Houses' Price prediction by Regression Models

## Table of Contents
* [General Info](#general-information)
* [Findings](#Findings)
* [Summary on conclusion](#Summary-on-conclusion)
* [Contact](#Contact)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
> ### * Problem statement
The company is looking at prospective properties to buy to enter the market.
 We are required to build a regression model using regularisation in order to 
 predict the actual value of the prospective properties and decide whether to invest in them or not.

The company wants to know:

    Which variables are significant in predicting the price of a house, and

    How well those variables describe the price of a house.

Also, determine the optimal value of lambda for ridge and lasso regression.
 
> ### * Business Goal 

We are required to model the price of houses with the available independent variables. 
This model will then be used by the management to understand how exactly the prices vary with the variables. 
They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. 
Further, the model will be a good way for management to understand the pricing dynamics of a new market.

> ### * Dataset
We are given a dataset that the company has collected from the sale of houses in Australia. The data is provided in the CSV file named "train.csv" as attached. From this, we will use to train and test the models' performance and select the best ones for this project

## Findings
- After pre-processing raw data, we have a cleaned dataset of 1460 rows and 259 columns (features). It is a high-dimensional dataset
- The optimal lambda (or alpha) for both 2 models of full all 259 features as following: Lasso(alpha=100) and Ridge(alpha=10); they have resulted not-perfectly fitted Normal Distributions due to some outliers (abnormally-high) sales prices where the models cannot fit them all. However, they are well-fitting for most points and residuals mostly vary from -100,000 to +100,000 - centering at 0; their r2_scores are around 0.86 (very well) and Mean Absolute Error-MAE is around 19000 ~ 10% SalePrice (median 163000, mean 181000). Hence, we accept these models for prediction in next steps of analysis
- Out of 259 full features, according to the best Lasso(alpha=100) model resulted, we have 106 features selected those are significant to the target variable SalePrice. And their significant Coef are sorted from highest to lowest.
-  Top 12 features have significant trends vs./impacts on the SalePrice visually. It provides us some hints for deeper numeric analysis on how they impact on the salePrice
- The models of top 12 significant features resulted r2_score for test data is around 81%, decreased 0.5-0.6% comparing to r2_score of test data from the full features' models first run (Mean Absolute Error-MAE is around 23500 comparing to last MAE of 19500 ~ 2% MAE increased). Therefore, we can find the models simplied with top 12 features (fewer but significant features) can also result approximately same same prediction performance in comparing to the models with full 259 features (or reduced to 105 features by the model Lasso(alpha=100)). And, up to the business expectation, we can decide which models (simplifed or full features) to be selected for the prediction.

## Summary on conclusion
- The optimal lamda (or alpha) for Lasso and Ridge regression as following:
    + Lasso(alpha=100) and Ridge(alpha=10): for all full 259 features as model's inputs/predictors
    + Lasso(alpha=100) and Ridge(alpha=1): for top 12 significant features as model's inputs/predictors
- Lasso(alpha=100) and Ridge(alpha=1) models with the top 12 features significant in predicting the price of a house are: GrLivArea, PoolQC_Gd, OverallQual, Condition2_PosN, GarageCars, Neighborhood_StoneBr, Neighborhood_NoRidge, Exterior2nd_ImStucc, Neighborhood_NridgHt, LotArea, 2ndFlrSF, and	OverallCond. They are accounting for around 81% variances of predicted results vs. actual results, and around 13% of Mean Abs. Errors/Mean (or Median) of a house's price.

## Contact
Created by nguyenhoangthangbt@gmail.com - feel free to contact me!
https://github.com/nguyenhoangthangbt/Houses_SalePrice_prediction
