# Credit_Risk_Analysis

## Overview
**Brief**
The purpose of this analysis is to display the differences between various machined learning models applied to a credit card lending dataset and to determine which models should or should not be used to determine credit risk.

**Detailed**
Various machined learning techniques were employed to train and evaluate models with unbalanced classes while building and evaluating models using resampling of a credit card dataset from LendingClub. Models used were Oversampling with both RandomOverSampler and SMOTE, Undersampling using ClusterCentroids, and a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Then, a comparison of two new machined learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, was done to predict credit risk. Each technique and model is highlighted below and a recommendation is given for each based on whether or not they should be used to predict credit risk.

## Results 
Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

**(1) Naive Random Oversampling**<br><br>
Accuracy Score: .66
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00
Recall Score
  - High Risk: .63
  - Low Risk: .69

<!-- <img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_ran_over.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_ran_over.png"> -->

**(2) SMOTE Oversampling**<br><br>
Accuracy Score: .62
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00
Recall Score
  - High Risk: .59
  - Low Risk: .66

<!-- <img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_smote_over.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_smote_over.png"> -->

**(3) Cluster Centroids Undersampling**<br><br>
Accuracy Score: .52
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00
Recall Score
  - High Risk: .60
  - Low Risk: .43

<!-- <img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_under_cc.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_under_cc.png"> -->

**(4) Combination(Over and Under) Sampling with SMOTEENN**<br><br>
Accuracy Score: .63
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00
Recall Score
  - High Risk: .69
  - Low Risk: .58
<!-- 
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_ov_un_smoteenn.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_ov_un_smoteenn.png"> -->

**(5) Balanced Random Forest Classifier**<br><br>
Accuracy Score: .79
Precision Score 
  - High Risk: .03
  - Low Risk: 1.00
Recall Score
  - High Risk: .69
  - Low Risk: .89

<!-- <img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_brf.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_brf.png"> -->

**(6) Easy Ensemble AdaBoost Classifier**<br><br>
Accuracy Score: .93
Precision Score 
  - High Risk: .07
  - Low Risk: 1.00
Recall Score
  - High Risk: .91
  - Low Risk: .94

<!-- <img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_boost.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_boost.png"> -->

For a cleaner display, results were shown as lists under each category. For coding screenshot support, please refer to the raw readme file where image files can be uncommented to be seen.

**Analysis**<br><br>
For easy comparison, the respective model number results are shown side by side respectively<br>
1, 2, 3, 4, 5, 6 <br>
Accuracy Score: .66, .62, .52, .63, .79, .93 <br>
Precision Score 
  - High Risk: .01, .01, .01, .01, .03, .07
  - Low Risk: 1.00, 1.00, 1.00, 1.00, 1.00, 1.00 <br>
Recall Score
  - High Risk: .63, .59, .60, .69, .69, .91
  - Low Risk: .69, .66, .43, .58, .89, .94

## Summary: 

**Accuracy**
- As seen from the results, all models prior to the ensemble learners had accuracies ranging from .62 to .66 with Naive Random Oversampling being the highest. The Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifiers were the highest with accuracies of .79 and .93 respectively.

**Precision**
- Out of all of the models, all of them were able to perfectly precise for predicting the low risk candidates but were not precise at all in predicting high risk candidates. This means that for the high risk candidates, there were a lot of false positives. This means that the models predicted that certain candidates were flagged as high risk although they were actually low risk.
- For low risk candidates, there were no false positives meaning that every pick the model made for a low risk candidate was 100% precise. 

**Recall (Sensitivity)**
- For most all models, there was very low recall for both high risk and low risk candidates. This means that in those models, there were high numbers of false negatives. For high risk candidates, this means that they were predicted as low risk when they were actually high risk. For low risk candidates, this means they were predicted as high risk candidates although they were really low risk.
- The Easy Ensemble AdaBoost Classifier had both high and low risk recalls above 90%. This means that when predicting each, there were a very low number of false negatives, so candidates were less likely to be in the wrong classification.

**Overall Winner**
- The Easy Ensemble AdaBoost Classifier was the only model that had all of its categories 90% above with .93, .91, and .94 for accuracy, precision, and recall respectively. I would recommend using this model out of the other models because of this. The only thing to be aware of is it was not precise in predicting high risk candidates. This means candidates might be flagged for high risk although they may be low risk. Other methods like credit score could be a final check for those who believe they are actually low risk candidates but got flagged as high risk.
