# Credit_Risk_Analysis

## Overview
**Brief**
The purpose of this analysis is to display the differences between various machined learning models applied to a credit card lending dataset and to determine which models should or should not be used to determine credit risk.

**Detailed**
Various machined learning techniques were employed to train and evaluate models with unbalanced classes while building and evaluating models using resampling of a credit card dataset from LendingClub. Models used were Oversampling with both RandomOverSampler and SMOTE, Undersampling using ClusterCentroids, and a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Then, a comparison of two new machined learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, was done to predict credit risk. Each technique and model is highlighted below and a recommendation is given for each based on whether or not they should be used to predict credit risk.

## Results 
Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

**Naive Random Oversampling**<br><br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_ran_over.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_ran_over.png">

**SMOTE Oversampling**<br><br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_smote_over.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_smote_over.png">

**Cluster Centroids Undersampling**<br><br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_under_cc.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_under_cc.png">

**Combination(Over and Under) Sampling with SMOTEENN**<br><br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_ov_un_smoteenn.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_ov_un_smoteenn.png">

**Balanced Random Forest Classifier**<br><br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_brf.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_brf.png">

**Easy Ensemble AdaBoost Classifier**<br><br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_boost.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_boost.png">

## Summary: Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
