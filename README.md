![image](https://user-images.githubusercontent.com/65314799/100488445-f1545280-30d3-11eb-80b8-21bf43b2ed85.png)

# Credit Risk Analysis using Machine Learning

For this project, I used machine learning techniques to predict credit risk using data from LendingClub. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so I had to employ different techniques for training and evaluating models with imbalanced classes. 

## Resampling

In the credit_risk_resampling notebook, I used the imbalanced learn library to resample the LendingClub data and built and evaluated logistic regression classifiers using the resampled data.

The first model oversamples the data using the `Naive Random Oversampler` and `SMOTE` algorithms.
The second model undersamples the data using the `Cluster Centroids` algorithm.
The third model uses Over- and under-sampling through a combination `SMOTEENN` algorithm.

I evaluated each model by doing the following:
* Train a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.
* Calculate the `balanced accuracy score` from `sklearn.metrics`.
* Calculate the `confusion matrix` from `sklearn.metrics`.
* Print the `imbalanced classification report` from `imblearn.metrics`.

A balanced accuracy score is defined as the average of recall obtained on each class which means it is useful in evaluating how good a binary classifier is.
The `Naive Random Oversampler` model had the best balanced accuracy score with a score of .65.

The recall is the ratio `tp / (tp + fn)` where `tp` is the number of true positives and `fn` the number of false negatives. The recall is intuitively the ability of the classifier to find all the positive samples.
The model that had the best recall score was also the `Naive Random Oversampler` model with a score of .68.

The geometric mean is the root of the product of class-wise sensitivity. 
The model that had the best geometric mean score was also the `Naive Random Oversampler` model with a score of .65

## Ensemble Learning

In the credit_risk_ensemble notebook, I trained and compared two different ensemble classifiers (`balanced random forest classifier` and the `easy ensemble AdaBoost classifier`) to predict loan risk and I evaluated each model. 

Each model was evaluated in the same way the resampling models were evaluated. For the balanced random forest classifier only, the feature importance is printed and sorted in descending order (most important feature to least important) along with the feature score.

The model that had the best balanced accuracy score was Easy Ensemble Adaboost Classifier which had a score of .93
The model that had the best recall score was also the Easy Ensemble Adaboost Classifier.
The model that had the best geometric mean score was also the Easy Ensemble Adaboost Classifier with a score of .93.

The Top Three Features:

| Feature         | Importance |
|-----------------|------------|
| total_rec_prncp |   0.078768 |
|     total_pymnt |   0.058838 |
| total_pymnt_inv |   0.056256 |

