# Customer Churn Analysis and Prediction

Our client PowerCo is a a major gas and electricity utility who is concerned about losing customers. 

My project is aimed at : 

* Interpreting the business context and breakdown of problem for data Analysis.

* Investigate whether price sensitivity is the most influential factor for a customer churning.

* Use feature engineering can be used to test hypotheses.

* Build new features to analyse data for PowerCo 

* Build a predictive model for churn using a random forest technique

### Exploratory Data Analysis

![alt]{https://github.com/Param1304/Customer-Churn-Analysis-and-Prediction/blob/main/Churning_status.png}
About 10% of the total consumers gets churned and these are distributed across 5 different sales channels.

![alt]{https://github.com/Param1304/Customer-Churn-Analysis-and-Prediction/blob/main/Sales_channel.png}

Plotting histogram for forecast variables reveals that a lot of variables are highly positively scewed creating a very long tail for higher values. 

![alt]{https://github.com/Param1304/Customer-Churn-Analysis-and-Prediction/blob/main/forecast.png}

Outliers in margin variables

![alt]{https://github.com/Param1304/Customer-Churn-Analysis-and-Prediction/blob/main/margin.png}

### Feature Engineering  
* Difference between off-peak prices in December and preceding January.
* Average price change across periods
  * Calculates the mean prices for different periods grouped by 'id' and then compute the differences between consecutive periods for both variable and fixed prices. Finally merge these differences back into the original DataFrame. This feature adds more granularity to previous feature.
* Maximum change in price across periods and months
  * For customer there is nothing more annoying than sudden price changes and a large increase in prices within a short time span would be an influencing factor in causing customer to look for better deal.
* Transforming dates into months
  * Further calculate how many months are left before contract ends, whether client has made recent updates to their contract and number of months since the client last renewed a contract.
* Transform boolean data into binary data.
* Transform categorical data.
* Transform numerical data

### Churn Prediction
* Model
Random Forest classifier has been used for this task. Random Forest sits within the category of ensemble algorithms because internally the forest refers to a collection of decision trees. Ensemble algorithms are powerful because of the laws of averaging, weak learners and central limit theorem. With ensemble methods instead of banking on one single trained model we can train 1000's of decision trees all using different splits of the data and learning different patterns. 
* Evaluation
Three metrics are used for evaluation of predictions on test data
  * Accuracy - the ratio of correctly predicted observations to the total number of observations.
  * Precision - the ability of the classifier to not label a negative sample as positive.
  * Recall - the ability of the classifier to find all the positive samples.
