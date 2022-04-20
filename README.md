# Credit_Risk_Analysis

## Overview
**Brief**
The purpose of this analysis is to display the differences between various machine learning models applied to a credit card lending dataset and to determine which models should or should not be used to determine credit risk.

**Detailed**
Various machined learning techniques were employed to train and evaluate models with unbalanced classes while building and evaluating models using the resampling of a credit card dataset from LendingClub. Models used were Oversampling with both RandomOverSampler and SMOTE, Undersampling using ClusterCentroids, and a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Then, a comparison of two new machined learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, was done to predict credit risk. Each technique and model is highlighted below and a recommendation is given for each based on whether or not they should be used to predict credit risk.

## Results 

**(1) Naive Random Oversampling**<br><br>
Accuracy Score: .66<br>
Precision Score
  - High Risk: .01
  - Low Risk: 1.00

Recall Score
  - High Risk: .63
  - Low Risk: .69

**Supporting Code Screenshots**<br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_ran_over.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_ran_over.png">

**(2) SMOTE Oversampling**<br><br>
Accuracy Score: .62<br>
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00

Recall Score
  - High Risk: .59
  - Low Risk: .66

**Supporting Code Screenshots**<br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_smote_over.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_smote_over.png">

**(3) Cluster Centroids Undersampling**<br><br>
Accuracy Score: .52<br>
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00

Recall Score
  - High Risk: .60
  - Low Risk: .43

**Supporting Code Screenshots**<br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_under_cc.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_under_cc.png">

**(4) Combination(Over and Under) Sampling with SMOTEENN**<br><br>
Accuracy Score: .64<br>
Precision Score 
  - High Risk: .01
  - Low Risk: 1.00

Recall Score
  - High Risk: .69
  - Low Risk: .58

**Supporting Code Screenshots**<br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_ov_un_smoteenn.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_ov_un_smoteenn.png">

**(5) Balanced Random Forest Classifier**<br><br>
Accuracy Score: .79<br>
Precision Score 
  - High Risk: .03
  - Low Risk: 1.00

Recall Score
  - High Risk: .69
  - Low Risk: .89

**Supporting Code Screenshots**<br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_brf.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_brf.png">

**(6) Easy Ensemble AdaBoost Classifier**<br><br>
Accuracy Score: .93<br>
Precision Score 
  - High Risk: .07
  - Low Risk: 1.00

Recall Score
  - High Risk: .91
  - Low Risk: .94

**Supporting Code Screenshots**<br>
<img height="35%" width="35%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/acc_boost.png">
<img height="75%" width="75%" src="https://github.com/smyoung88/Credit_Risk_Analysis/blob/main/Resources/matrix_boost.png">



**Analysis**<br><br>
For easy comparison, the respective model number results are shown side by side respectively<br>
1.Naive Random Oversampling, 2. SMOTE Oversampling, 3. Cluster Centroids Undersampling, 4. Combination(Over and Under) Sampling with SMOTEENN, 5. Balanced Random Forest Classifier, 6.Easy Ensemble AdaBoost Classifier <br>
Accuracy Score: .66, .62, .52, .63, .79, .93

Precision Score
  - High Risk: .01, .01, .01, .01, .03, .07
  - Low Risk: 1.00, 1.00, 1.00, 1.00, 1.00, 1.00

Recall Score
  - High Risk: .63, .59, .60, .69, .69, .91
  - Low Risk: .69, .66, .43, .58, .89, .94

## Summary: 

**Accuracy**
- As seen from the results, all models before the ensemble learners had accuracies ranging from .62 to .66 with Naive Random Oversampling being the highest. The Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifiers were the highest with accuracies of .79 and .93 respectively.

**Precision**
- Out of all of the models, all of them were perfectly precise for predicting the low-risk candidates but were not precise at all in predicting high-risk candidates. This means that for the high-risk candidates, there were a lot of false positives. This means that the models predicted that certain candidates were flagged as high risk although they were low risk.
- For low-risk candidates, there were no false positives meaning that every pick the model made for a low-risk candidate was 100% precise. 

**Recall (Sensitivity)**
- For most all models, there was very low recall for both high-risk and low-risk candidates. This means that in those models, there were high numbers of false negatives. For high-risk candidates, this means that they were predicted as low risk when they were high risk. For low-risk candidates, this means they were predicted as high-risk candidates although they were low-risk.
- The Easy Ensemble AdaBoost Classifier had both high and low risk recalls above 90%. This means that when predicting each, there were a very low number of false negatives, so candidates were less likely to be in the wrong classification.

**Overall Winner**
- The Easy Ensemble AdaBoost Classifier was the only model that had all of its categories 90% above with .93, .91, and .94 for accuracy, precision, and recall respectively. For credit score, we would care more about low false negatives than low false positives (high recall vs high precision). I would recommend using this model out of the other models because of this. The only thing to be aware of is it was not precise in predicting high-risk candidates but that is okay because it means candidates might be flagged for high-risk although they may be low risk. Precautionary measures may be taken on an individual when they didn't need to be. Other analyses like credit scores could be a final check for those who believe they are low-risk candidates but got flagged as high risk. High recall means there is a low chance of not warning about a high-risk candidate when in fact they are high-risk candidates, leading to high-risk candidates being approved and there being possible repercussions because of it.
- Since this model has such high accuracy, precision, and recall, it is advised to keep an eye on the model in case it is overfitted to the dataset provided and that it continues to be evaluated as newer data is introduced to it.
