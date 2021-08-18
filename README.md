# Credit_Risk_Analysis
Challenge 17 for UT Bootcamp - Supervised learning



# Overview of the Analysis
The purpose of this analysis is to practice training, fitting, and predicting with supervised learning models. The scenario context is loan approval for credit loans. In this case, the model is training on data to determine whether or not to approve loans based on the default or payback of loans by other customers with similar characteristics. A logistic regression model is used, and various techniques for resampling are explored as the training data is not balanced.



# Results
This analysis tested several machine learning models with various sampling techniques for compensating for the imbalanced training set. In all models, the response variable of risk level was coded as 0 being a 'low-risk' loan and 1 being a 'high-risk' loan. Thus, we will read the outputs with 1 being positive for a high-risk loan.

Accuracy interpretation: This number represents the percentage of people who are correctly identified as either high-risk OR low-risk by the model.

Precision interpretation: This number represents the percentage of people identified as high risk that actually are high-risk: TP/(TP + FP). As you will see, this number is close to zero for all of the models, which means that we are incorrectly labeling too many loans as high-risk when they actually are not. This is a problem as it could cause customers to go to other banks if we deny a loan. This number is low primarily due to the low number of high-risk loans overall in the training set. It means that we may need to consider other ways to improve our training set so that precision can be better.

Recall (Sensitivity): This number represents the percentage of people who are high-risk loaners and are correctly identified by the model. We would like this to be as close to 1 as possible because it lessens the potential losses for the bank due to loan defaults.


## Sampling Technique 1: Naive Random Oversampling

- Balanced Accuracy Score: 64%
- Precision: 1%
- Recall: 65%

![naive](link here)

## Sampling Technique 2: SMOTE Oversampling

- Balanced Accuracy Score: 66%
- Precision: 1%
- Recall: 63%

![smote](link here)

## Sampling Technique 3: Cluster Centroids Undersampling

- Balanced Accuracy Score: 57%
- Precision: 1%
- Recall: 57%

![cluster](link here)

## Sampling Technique 4: Combination Over-sampling and Under-sampling

- Balanced Accuracy Score: 68%
- Precision: 1%
- Recall: 81%

![combo](link here)

## Ensemble Technique 1: Balanced Random Forest Classifier and an Easy Ensemble AdaBoost 

- Balanced Accuracy Score: 73%
- Precision: 5%
- Recall: 50%

![randomForest](link here)

## Ensemble Technique 2: Easy Ensemble AdaBoost Classifier  

- Balanced Accuracy Score: 92%
- Precision: 5%
- Recall: 93%

![adaBoost](link here)



# Summary
All of the oversampling and undersampling models have an accuracy rate below 70% and have a precision of 1%. Thus, these are not good models because there are too many errors and far too many loans denied that do not have to be (precision). This is too likely to make customers angry or drive them to other loaning institutions, thus representing a potential loss in revenue for the bank.

The best model of the six tested here is the classifier with AdaBoost. It has the highest accuracy of all models (92%) and the highest precision (5%). While this precision value is still low, I recommend the bank use this model for the next 3 months and gather additional consumer data in an effort to obtain a better model so that the precision of a future model can be improved.