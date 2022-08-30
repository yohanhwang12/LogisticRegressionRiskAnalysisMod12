# LogisticRegressionRiskAnalysisMod12
Credit Risk Analysis using Logistic Regression

This is Challenge 12, of Module 12 from Northwestern's Fintech Bootcamp:

### Background
Credit risk poses a classification problem that’s inherently imbalanced. The reason is that healthy loans easily outnumber risky loans. For this Challenge, you’ll use various techniques to train and evaluate models with imbalanced classes. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

What You’re Creating
Using your knowledge of the imbalanced-learn library, you’ll use a logistic regression model to compare two versions of the dataset. First, you’ll use the original dataset. Second, you’ll resample the data by using the RandomOverSampler module from the imbalanced-learn library.

For both cases, you’ll get the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

As part of the README.md file in your GitHub repository, you’ll create a credit risk analysis report based on the provided template in your Starter_Code folder.

The instructions for this Challenge are divided into the following subsections:

Split the Data into Training and Testing Sets

Create a Logistic Regression Model with the Original Data

Predict a Logistic Regression Model with Resampled Training Data

Write a Credit Risk Analysis Report

### Split the Data into Training and Testing Sets
Open the starter code notebook, and then use it to complete the following steps:

Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.

Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.

NOTE
A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.

Check the balance of the labels variable (y) by using the value_counts function.

Split the data into training and testing datasets by using train_test_split.

### Create a Logistic Regression Model with the Original Data
Use your knowledge of logistic regression to complete the following steps:

Fit a logistic regression model by using the training data (X_train and y_train).

Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.

Evaluate the model’s performance by doing the following:

Calculate the accuracy score of the model.

Generate a confusion matrix.

Print the classification report.

Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

### Predict a Logistic Regression Model with Resampled Training Data
Did you notice the small number of high-risk loan labels? Perhaps, a model that uses resampled data will perform better. You’ll thus resample the training data and then reevaluate the model. Specifically, you’ll use RandomOverSampler.

To do so, complete the following steps:

Use the RandomOverSampler module from the imbalanced-learn library to resample the data. Be sure to confirm that the labels have an equal number of data points.

Use the LogisticRegression classifier and the resampled data to fit the model and make predictions.

Evaluate the model’s performance by doing the following:

Calculate the accuracy score of the model.

Generate a confusion matrix.

Print the classification report.

Answer the following question: How well does the logistic regression model, fit with oversampled data, predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

## My Credit Risk Analysis Report

#### Overview of the Analysis

The purpose of this analysis was to evaluate a logistic regression model and see how well it discriminates between what would be healthy loans vs risky loans based on other customer data such as derogatory marks, borrower's income, income to debt ratio, etc. The data given had over 75,000 healthy loans (marked with '0') and only about 2500 unhealthy loans (marked with '1'). Using train-test-split, initially the first Linear Regression model used was simply fed the data as it is. Loan status, whether healthy or unhealthy was considered the dependent variable (y) and all other data were collectively the independent variables (X). Then we tried improving the Logistic Regression model by first resampling the data using RandomOverSampler, which basically adds other fake data to provide a balance between healthy and unhealthy loans. Since the machine could train equally for healthy and unhealthy loans this time, results improved by several percentage points.

#### Results

* The balanced accuracy score without resampling came to 94%. Precision was 1 for healthy loans and .87 for unhealthy. Recall was 1 for healthy and .89 for unhealthy. F1 was 1 for healthy and .88 for unhealthy. All of this is expected given that there were a lot more healthy loans for the machine to train with than unhealthy ones.<br>

* After resampling and making the value count of healthy and unhealthy loans similar, we see a balanced accuracy score of 99%. Precision score is still 1 for healthy and .87 for unhealthy loans. Recall is 1 and 1 for both! F1 is 1 for healthy and up to .93 for unhealthy loans.

#### Summary

The second model, with the data resampled works better. We know this from the higher scores for the unhealthy loans and the overall balanced accuracy score.

I would recommend this model as there is significant improvement in predicting default loans. Yes, predicting default loans are more important than predicting healthy loans as one default is more harmful for a lender than missing out on a potentially good customer. But with a 99% balanced accuracy score, much of the risk is mitigated.
