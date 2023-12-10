# Risky Business
 
![Credit Risk](Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, some clients want to be able to predict credit risk with machine learning techniques.

Build and evaluate several machine learning models to predict credit risk using data typically seen from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), employ different techniques for training and evaluating models with imbalanced classes. Use the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

### Instructions

#### Resampling

Use the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

1. Read CSV into a DataFrame.

2. Split data into Training and Testing sets.

3. Scale training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. Use provided code to run Simple Logistic Regression:
    * Fit `logistic regression classifier`.
    * Calculate `balanced accuracy score`.
    * Display `confusion matrix`.
    * Print `imbalanced classification report`.

Next:

1. Oversample data using `Naive Random Oversampler` and `SMOTE` algorithms.

2. Undersample data using `Cluster Centroids` algorithm.

3. Over- and undersample using combination `SMOTEENN` algorithm.


For each of the above:

1. Train `logistic regression classifier` from `sklearn.linear_model` using resampled data.

2. Calculate `balanced accuracy score` from `sklearn.metrics`.

3. Display `confusion matrix` from `sklearn.metrics`.

4. Print `imbalanced classification report` from `imblearn.metrics`.


Use above to answer following questions:

* Which model had best balanced accuracy score?
>
* Which model had best recall score?
>
* Which model had best geometric mean score?

#### Ensemble Learning

Train and compare two different ensemble classifiers to predict loan risk and evaluate each model. Use [Balanced Random Forest Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.BalancedRandomForestClassifier.html#imblearn-ensemble-balancedrandomforestclassifier) and [Easy Ensemble Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.EasyEnsembleClassifier.html#imblearn-ensemble-easyensembleclassifier). Refer to documentation for each of these to read about models and see examples of code.

To begin:

1. Read data into DataFrame.

2. Split data into training and testing sets.

3. Scale training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Then, complete following steps for each model:

1. Train model using quarterly data from LendingClub provided in `Resource` folder.

2. Calculate balanced accuracy score from `sklearn.metrics`.

3. Display confusion matrix from `sklearn.metrics`.

4. Generate classification report using `imbalanced_classification_report` from imbalanced learn.

5. For balanced random forest classifier only, print feature importance sorted in descending order (most important feature to least important) along with feature score.


Use above to answer following questions:

* Which model had best balanced accuracy score?

* Which model had best recall score?

* Which model had best geometric mean score?

* What are top three features?

- - -

### Considerations

Use quarterly data from LendingClub data provided in the `Resources` folder.

Refer to [imbalanced-learn](https://imbalanced-learn.readthedocs.io/en/stable/) and [scikit-learn](https://scikit-learn.org/stable/) official documentation for help with training the models. These models all use model->fit->predict API.

For ensemble learners, using 100 estimators for both models.

- - -
