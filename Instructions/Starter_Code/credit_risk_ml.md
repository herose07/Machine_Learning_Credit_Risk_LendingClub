# UNIT 11 CLASSIFICATION HOMEWORK

In this assignment, I attempted to build and evaluate several machine-learning models to predict credit risk using free data from LendingClub. 

The data presents an imbalanced classification problem, so I employed different techniques for training and evaluating models with imbalanced classes. 

I used the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:
* Resampling
    * Oversample the data using the Naive Random Oversampler and SMOTE algorithms.
    * Undersample the data using the Cluster Centroids algorithm.
    * Over- and under-sample using a combination SMOTEENN algorithm.
* Ensemble Learning
    * Balanced Random Forest Classifier
    * Easy Ensemble AdaBoost Classifier


## Which model had the best balanced accuracy score?

The model that had the best balanced accuracy score was Easy Ensemble Adaboost Classifier which had a score of .93

## Which model had the best recall score?

The model that had the best recall score was also the Easy Ensemble Adaboost Classifier.

## Which model had the best geometric mean score?

The model that had the best geometric mean score was also the Easy Ensemble Adaboost Classifier with a score of .93.

## What are the top three features?

| Feature         | Importance |
|-----------------|------------|
| total_rec_prncp |   0.078768 |
|     total_pymnt |   0.058838 |
| total_pymnt_inv |   0.056256 |