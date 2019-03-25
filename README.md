# Credit_Risk
My solution for Analyze This 2018 by American Express

Disclaimer :- It's a bit of a mess right now. I lost a lot of my files after my computer crashed. I've uploaded all the files I could salvage. I'm in the process of redoing it.

Our method

We started with Exploratory Data Analysis (EDA) by doing univariate and multivariate analysis of variables, data cleaning and feature engineering, and then proceeded for modelling.

Beginning with weak learners like logistic regression and C5.0 decision tree, we moved on to ensemble decision tree models like GBM, XgBoost and Light GBM.

We used  Bayesian Optimization techniques with stratified k-fold cross validation to find the best values of the parameters used.

We sorted the application ID of the customers by discretizing the confidence values and assigning them the appropriate weights.

Since we wanted to avoid overfitting for the final submission (evaluation dataset), we submitted the predictions of a more robust model, rather than the predictions of the model which gave the best score on the Leaderboard.

The model used for the Leaderboard submission was an ensemble model based on majority voting of C5.0 decision tree, GBM and Logistic Regression models, whereas the model used for final submission was an ensemble model based on majority voting of XgBoost and Logistic Regression.

The predictions of the majority ensemble models were sorted according to the weighted average of the confidence values of the individual models.

New variables created :-
Approximate net worth of the customer.
Severity of liability of the customer (created using loan variables).
Average missed payments in a year.
Types of cards owned by the customer.
Average tenure of repayment.
Overall credit worthiness of the customer (created using credit score and other related scores).
Affluence of the customer (categorical).

Already available variables :-
Dropped some redundant variables manually by selecting relevant variables.
Dropped some variables on the basis of lasso feature selection.

The data contained a lot of missing values, and we imputed them by using LDE, wherein we fed relevant variables to the algorithm to predict the missing values.

The data was very skewed, so we had to do power transformation, (boxcox transformation) to normalize the data for the logistic regression model.

We created new variables and removed redundant ones with dimensionality reduction to ensure that each variable becomes nearly independent.

As XgBoost alone has trouble with extrapolation, we chose an ensemble of XgBoost and Logistic Regression, since it would also account for a lot of the multi-collinearity in the data.

A little more data engineering will definitely go a long way, and will improve the overall accuracy. I'll upload the new files as soon as possible.
