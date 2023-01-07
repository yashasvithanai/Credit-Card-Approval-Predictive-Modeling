# Credit Card Approval - Predictive Modeling

The dataset provided gives characteristics of applicants for a major credit card. The business aim is to predict the probability of a credit card application getting approved based on the characteristics of the applicant.
These predictive models can help the bank to decide if the credit card should be approved and process credit card applications faster.

## Data Dictionary
_card_ Boolean. Was the application for a credit card accepted?
_reports_ Number of major derogatory reports.
_age_ Age in years plus twelfths of a year. income Yearly income (in USD 10,000). share: Ratio _share_ Ratio of monthly credit card expenditure to yearly income.
_expenditure_ Average monthly credit card expenditure.
_owner_ Boolean. Does the individual own their home?
_selfemp_ Boolean. Is the individual self-employed?
_dependents_ Number of dependents.
_months_ Months living at current address. 
_majorcards_ Number of major credit cards held. 
_active_ Number of active credit accounts. 

## Analytics Concepts
-	Building predictive models to predict the probability of a credit card application getting approved based on certain characteristics of the applicant.
-	Performing K-Cross Validation technique to train 50+ linear and MARS models and measuring their average performance across the 5 folds using the validation set.

## Model Selection 
We select the model with the lowest Mean Squared Error, indicating the best performance. 

### Model 1 (without reports)
`model1A = earth(card~income+share+majorcards+active+poly(months,2)+poly(expenditure,2)+age*owner, data=fullFile, degree=2)`

**MSE obtained: 0.3638674**

### Model 2 (with reports)
`model1B = earth(card~reports+income+share+majorcards+poly(active,2)+poly(months,2)+expenditure+age*owner, data=fullFile, degree=2, thres=.0001)`

**MSE obtained: 0.35499**

