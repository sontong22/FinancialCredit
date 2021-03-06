# Predicting personal financial distress

## Context

### Introduction

Banks play a crucial role in market economies. They decide who can get finance and on what terms and can make or break investment decisions. For markets and society to function, individuals and companies need access to credit.

Credit scoring algorithms, which make a guess at the probability of default, are the method banks use to determine whether or not a loan should be granted.

We want to build a model that borrowers can use to help make the best financial decisions, by predicting the probability that somebody will experience financial distress in the next two years.

### Purpose

What purpose do you expect of having such model?

### Data Explanation


The dataset obtained from https://www.kaggle.com/c/GiveMeSomeCredit contains 11 fields for 150,000 people.

SeriousDlqin2yrs: Person experienced 90 days past due delinquency or worse

RevolvingUtilizationOfUnsecuredLines: Total balance on credit cards and personal lines of credit except real estate and no installment debt like car loans divided by the sum of credit limits

age: Age of borrower in years

NumberOfTime30-59DaysPastDueNotWorse: Number of times borrower has been 30-59 days past due but no worse in the last 2 years.

DebtRatio: Monthly debt payments, alimony,living costs divided by monthy gross income

MonthlyIncome: Monthly income

NumberOfOpenCreditLinesAndLoans: Number of Open loans (installment like car loan or mortgage) and Lines of credit (e.g. credit cards)

NumberOfTimes90DaysLate: Number of times borrower has been 90 days or more past due.

NumberRealEstateLoansOrLines: Number of mortgage and real estate loans including home equity lines of credit

NumberRealEstateLoansOrLines: Number of mortgage and real estate loans including home equity lines of credit

NumberOfTime60-89DaysPastDueNotWorse: Number of times borrower has been 60-89 days past due but no worse in the last 2 years.

NumberOfDependents: Number of dependents in family excluding themselves (spouse, children etc.)

We would construct several classification models, trying to predict whether a person would experience 90 days past due delinquency or worse.


### Process

1. Explore and clean up data: 

- Plot to see the relationships among variables, find out data characteristics.

- Remove unreasonable observation.

- Implement data preprocessing pipeline to fill missing values with median and perform log transformation on right-skewed explanatory variables. 


2. Train Models:

- Use: SGDClassifier, KNNClassifier, DecisionTree, Random Forest, Voting Classifier (from KNN, Decision Tree, and Random Forest).

- Evaluation method: use ROC curve and the area under the curve for evaluation since the classes are imbalanced.

- Hyperparameter tuning: use GridSearch and RandomizedSearch with error score F1 (the harmonic mean of precision and recall).

- Plot the importance of each explanatory variables in making predictions.

- Choose the best model by plotting the ROC curve and the area under the curve with cross-validation.  
