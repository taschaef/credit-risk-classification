# Module 12 Report

## Overview of the Analysis
1. Explain the purpose of the analysis.
   
The purpose of the analysis in this challenge was to use supervised machine learning models to predict loan risk based on provided data. The data provided was historical lending activity from a peer-to-peer lending service. 

3.  Explain what financial information the data was on, and what you needed to predict.
   
The data was provided in the form of an Excel sheet, which I then imported into a Pandas dataframe. The categories in the data include: 
  * Loan Size
  * Interest Rate
  * Borrower Income
  * Debt to Income Ratio
  * Number of Accounts
  * Derogatory Marks 
  * Total Debt

3.  Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
   
The machine model was trying to predict whether active loans were "healthy" or "high risk" (i.e. at risk of defaulting) based on the provided data. As seen in my Jupyter notebook, I split the loans into these two categories and can easily see how many loans are considered healthy or high risk by calling the value_counts command. 

5.  Describe the stages of the machine learning process you went through as part of this analysis. Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
   
To begin, the first model was subjected to a logistic regression model using the original data. To simplify, a subsets of the total original data were used. This first model was trained on a subset of the orignial data, then it was tested and it's accuracy, precision, and recall rates tested and recorded on a different subset of the data. 
Then, for a more wholistic view of the data, a second model was trained based on a randomly oversampled data from the original dataset. This step is necessary because of the disparity between the two groups: the healthy loans and the high risk loans. 
75036 loans are deemed healthy while only 2500 loans are considered high risk. Because there is a significant difference between the number of healthy loans vs the number of high risk loans, the randomly oversampled method was applied to even out the number of samples in each category so comparison is clearer.  The second model also subjected to a logistical regression model, and the accuracy, precision, and recall rates were recorded. 

## Results
Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
* Description of Model 1 Accuracy, Precision, and Recall scores.
  * Balanced Accuracy: 95%
  * Precision Healthy: 100% 
  * Precision High Risk: 85% 
  * Recall Healthy: 99% 
  * Recall High Risk: 91% 
  * F1-score Healthy: 100% 
  * F1-score High Risk: 88% 



* Machine Learning Model 2:
* Description of Model 2 Accuracy, Precision, and Recall scores.
  * Balanced Accuracy: 99%
  * Precision Healthy: 100% 
  * Precision High Risk: 84%
  * Recall Healthy: 99%
  * Recall High Risk: 99%
  * F1-score Healthy: 100% 
  * F1-score High Risk: 91% 

## Summary
Based on the metrics above, the second machine learning model based on the randomly oversampled data is superior in predicting creditworthiness of borrowers. While both models have a high balanced accuracy rate, the first model is sighly inferior with a score of only 95% compared to the 99% of the second model. Both models have nearly identical scores between healthy and high risk loans when it comes to precision. When looking at recall, it is obvious the second model outshines the first at predicting high risk loans; the recall for high risk loans on the first model is merely 91% whereas it is 99% on the second model. Therefore, if given the choice between the two models I would use the second model because it is more accurace at predicting both types of loans. 
