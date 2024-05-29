# **CreditCard Customer Default Prediction**

## **Overview**
Credit card default prediction is essential for banks and financial institutions to manage and mitigate the risk posed by defaulters. The main goal of this project is to predict customers who are likely to default on their credit card payments in the upcoming month.

In this model:
- Scores obtained from Generalized Low Rank Models (GLRM) for each cluster are used as inputs.
- Customers are classified as defaulters or non-defaulters based on these scores.
- Various correlation measures are applied to the features based on their types.
- Highly correlated features are clustered using hierarchical clustering.
- Feature dimensionality reduction is performed using GLRM.
- The reduced features are fed into different binary classification algorithms to predict defaulters.

## **Dataset**
The dataset is downloaded from the UCI Machine Learning Repository. It includes credit card data from clients in Taiwan collected between April 2005 and September 2005. The dataset consists of 30,000 samples and 25 features.
![image_page1_1](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/ab80502d-50d2-46e7-b8ed-3810da22e256)


## **Data Analysis**
From the below pie chart, observe that 78% of the customers are non-default and
22% of the customers are default, which clearly says that the dataset is a imbalanced
dataset. Categorical features contain the misrepresented values, those values are
adjusted by created one more level for those values.
![image_page1_2](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/515427c7-7a92-4967-ad98-c78c150c9d89)

### **Clustering Of Features Using Correlation Matrix**
Correlation Matrix: Various correlation techniques which are listed in the image below, helps to find the relationship between the different types of features.

![image_page1_3](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/b7e13014-900b-46b7-a569-0e5652327987)

### **Hierarchical Clustering:**
It is a bottom up approach. We can cut the dendrogram based on our interest.Here we cut the dendrogram at y=2, which leads to 5 clusters.

### ** Apply GLRM To Calculate The Cluster Scores:**
Generalized Low Rank Models (GLRM) is an algorithm for dimensionality reduction of a dataset.It is like PCA, but it can handle mixed numeric, categorical, ordinal and Boolean data with an arbitrary number of missing values.

![image_page1_6](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/6dc63d72-825e-4b66-94cd-ad5d56833f45)

We draw the dendrogram for 5 clusters. Let us say if the first cluster contains some 6 features, GLRMwill combine these features and gives one feature which is called cluster score. After applying GLRM the dimensionality of the dataset is changed from (30000,23) to (30000,5)

### **Splitting The Dataset Into Train Data And Test Data:**
Split the data in such a way that 75% of the data is used for training and 25% of the data is used for testing.

### **Oversampling Of Data Using SMOT (Synthetic Minority Over-Sampling Technique):**
As our dataset is a imbalanced data we are using oversampling technique called SMOT to balance the data. Before applying oversampling, proportions of class 0 and class 1 is of 78:22.

### **Binary Classification Algorithms:**
Binary classification algorithms such as Logistic regression and Support Vector machines are applied to the reduced dimension dataset and the results of confusion matrix, precision, recall is compared. Figure below shows the confusion matrix for Logistic regression and SVM.

  ![image_page1_7](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/1f5b59ea-e78b-4d97-a33b-d12f0cc96e32)

### **Result:**
Table below shows the accuracy, Precision, Recall, Specificity and F1-score obtained for both algorithms


  ![image_page1_8](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/209f4bec-15b6-43dc-b7b1-1dc78d1dd728)

### **Receiver Operating Characteristic Curve :**
The ROC curve is plotted on a graph with the True Positive Rate (Sensitivity) on the Y-axis and False Positive Rate (1 - Specificity) on the X-axis. The values of the TPR and the FPR are found for many thresholds from 0 to 1.The main objective here is to find a point on the ROC curve where the Area under it is the maximum. This is because it is at this point, where the model could correctly distinguish between binary classes with there being minimum overlap between them. So as the AUC increases the overlap between the binary classes decreases. At that threshold point, the model can distinguish classes the best.

 ![image_page1_9](https://github.com/Shreya18/CreditCard_Customer_Default_Prediction/assets/28389439/bdc57492-857a-4079-9b3a-4c50e2ceedca)

### Summary:
The confusion matrix for Logistic Regression shows that only 53% of all the defaulters (884 out of 1659) which means that misses 53% of all the defaulters. While the recall score for Support Vector Machine of 66.5% (1103 out of 1659). This means that our model can accurately catch around 67% of all the defaulters which is better than Logistic Regression.

## Requirements
- Python 3.x
- Libraries: pandas, numpy, scikit-learn, matplotlib, seaborn, etc.


