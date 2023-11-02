# Credit-Risk-Classification

## Background: 

In this Challenge, you’ll use various techniques to train and evaluate a model based on loan risk. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers. 

## Credit Risk Analysis Report: 

1. Explain the purpose of this analysis: 

* The purpose of this analysis is to create and evaluate the accuracy of a model that predicts the credit worthiness of borrowers from peer to peer lenders. 

2. Explain what financial information the data was on, and what you needed to predict. 

* I was provided with a csv file called lending_data.csv, which contains 8 variables. Loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, total_debt, and loan_status. Loan_status contains either 0 or 1, where 0 means the loan is healthy, and 1 indicates the loan is at a high-risk for default. This file was read in and then stored in a dataframe called lending_df. 

3. Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

* To predict credit worthiness, and the likelihood a borrower could obtain a loan, I started by seperating out our loan_status column into the y variable. Then, the remaining variables were stored in our X variable. Following the splitting of these two variables, I used value_counts to check the amount of each type of loan in our y variable. The results showed that 75036 loans were healthy, and 2500 were high-risk. 

4. Describe the stages of the machine learning process you went through as part of this analysis.

* I started by splitting the data using the train_test_split module from sklearn. These are X_train, X_test, y_train, y_test. A random_state of 1 was also assigned to the function to ensure it was consistent when splitting the information across multiple runs of code. 

5. Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

* A LogisticRegression model was then created with the original data also using a random_state of 1. It was fit with the training data, X_train, and y_train, and predicted on testing data with predict() using X_test and the fitted model lr_model. As a result, I calculated the accuracy score and the confusion matrix of the model utilizing balanced_accuracy_score(), confusion_matrix(), and a classification_report() based on our y_test and predictions. Finally, I used RandomOverSampler() to resample the data, and repeated the above steps with our new resampled data. 


## Results: 

* Machine Learning Model 1: 
* Model 1 Accuracy: 0.952
* Model 1 Precision: Healthy Loans = 1.00, High-Risk loans = 0.85
* Model 1 Recall: Healthy Loans = 0.99, High-Risk loans = 0.91

* Machine Learning Model 2: 
* Model 2 Accuracy: 0.995
* Model 2 Precision: Healthy Loans = 0.99, High-Risk loans = 0.99
* Model 2 Recall: Healthy Loans = 0.99, High-Risk loans = 0.99

## Summary: 
* The oversampled data performed better when making predictions in our Logistic regression model. 
* Performance is very dependent on what we are looking to solve. If we are attempting to predict the healthy loans then our original data logistic regression would perform better given its precision of 1.00, recall of 0.99, and f1-score of 0.99. Compared to the resampled data having 0.99 across the board. However, when looking at high-risk loans, our resampled data had a better precision, recall and f1-score than our original data. 
* It is much more important to predict high-risk loans as those are the ones that end up costing money in the end if they don't work out. Therefore, I would recommend utilizing the second model to do our predictions given it has better marks on each stage than our original model. 