# Titanic Dataset Analysis Using Machine Learning (Kaggle Dataset)

In this project, the titanic dataset from kaggle was used. The purpose of the project is to train models on the titanic data and make predictions about the Survival of a person, given some attributes that will be trained in the ML models.

There are three csv files attached.
- train.csv: This file was used to train the data. the contents of this file were split using train test split and evaluated.
- test.csv: This file does not contain the 'Survived' column and was used to make to make predections(Survived/Didn't Survive) 
    - Survived : 1
    - Didn't Survive: 0
- Predictions.csv: This file contains the results of our predicitons.


In this project, four machine learning algorithams were tested

- LogisticRegression 
- RandomForrestClassifier 
- GradientBoostingClassifier
- SVC 

With defgault parameters, the following results were obtained:

Model: LogisticRegression(max_iter=1000)  Training score: 0.819  Validation score 0.814 
Model: RandomForestClassifier(random_state=55)  Training score: 0.997  Validation score 0.808 
Model: GradientBoostingClassifier(random_state=56)  Training score: 0.941  Validation score 0.833 
Model: SVC()  Training score: 0.621  Validation score 0.623

Based on the above results, it was decided to select RandomForestClassifier and GradientBoostingClassifier for further hyper parameter tuning.
the optimum hyper parameters for RandomForestClassifier and GradientBoostingClassifier determined are:

RandomForestClassifier
Best parameters: {'max_depth': 5, 'n_estimators': 2000}
Best cross-validation score: 0.84

GradientBoostingClassifier

Best parameters: {'learning_rate': 0.1, 'n_estimators': 50}
Best cross-validation score: 0.83

Both these models were then retrained to the test split (from train.csv) and the classification report generated. Interestingly, RandomForestClassifier showed an accuracy of 0.83 compared to 0.84 for GradientBoostingClassifier, even though the results were the opposite when we applied these models on the training set.

Since GradientBoostingClassifier with learning_rate': 0.1, 'n_estimators': 50 performed better on the test set, this model was selected to make predections on our test.csv file in order to determine weather a person, given their Pclass, Sex, Age, SibSp, parch, Fare, Embarked Location would surviove or not.
