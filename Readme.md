# Fraud Detection
## Analysis of creditcard transactions in order to predict fraudulent ones

For this analysis, I used creditcard transaction dataset from Kaggle: https://www.kaggle.com/mlg-ulb/creditcardfraud/data

In this analysis, I have used SVM Classifiers. I tried two kernels � RBF and Linear. I have also checked the effect of feature normalization on classifier performance. I found that the SVM classifier with the RBF kernel with feature normalization has the best test set performance. 

Since we have an unbalanced dataset and for fraud detection we care more about getting a high recall rate and ideally would like to reduce the false positive rate as well, I used area under the ROC as my evaluation metric. 

I further optimized the SVM model with RBF kernel using GridSearchCV on the gamma parameter and auc_roc as the scoring parameter and found that the default parameter itself gave the best test score � 0.96 

I also used undersampling method to get a better classifier since our dataset is highly unbalanced (less than 0.2% of the transactions are fraudulent!). As expected my test set recall score greatly improved using undersampling (from 0.59 to 0.79 for the default decision threshold) and my AUC score jumped to 0.98. This score did not change after hyper parameter tuning with undersampled majority class. 
