# CreditCard Customer Default Prediction

## Overview
Credit card default prediction is essential for banks and financial institutions to manage and mitigate the risk posed by defaulters. The main goal of this project is to predict customers who are likely to default on their credit card payments in the upcoming month.

In this model:
- Scores obtained from Generalized Low Rank Models (GLRM) for each cluster are used as inputs.
- Customers are classified as defaulters or non-defaulters based on these scores.
- Various correlation measures are applied to the features based on their types.
- Highly correlated features are clustered using hierarchical clustering.
- Feature dimensionality reduction is performed using GLRM.
- The reduced features are fed into different binary classification algorithms to predict defaulters.

## Dataset
The dataset is downloaded from the UCI Machine Learning Repository. It includes credit card data from clients in Taiwan collected between April 2005 and September 2005. The dataset consists of 30,000 samples and 25 features.

## Project Details
For a complete explanation of the project, please refer to the [CreditCard_Customer_Default_Prediction.pdf](CreditCard_Customer_Default_Prediction.pdf) file.

## Requirements
- Python 3.x
- Libraries: pandas, numpy, scikit-learn, matplotlib, seaborn, etc.


