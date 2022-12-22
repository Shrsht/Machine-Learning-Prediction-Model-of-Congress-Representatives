# Predicting-Party-of-Congress-Member-from-Stock-Trading-History

-This project builds on a previous exploration of the 'House Stock Watcher" data set. In continuation I now attempt explore a prediction problem involving the same data set using a Machine Learning pipeline in the sklearn ML Package.
We will attempt to form a prediction of the Party Affiliation of a given Individual representative, given their stock trading hitsory.

The above prediction represents a 'Classification Problem' , where out target variable will be the Party of the representative, as recorded in the _party_ column of our dataset. Our evalutation metrics will be the _representative , ticker , type _ columns.

This project consists of 2 models:

## 1) Baseline Model
-The baseline model of this project contains a total of 4 nominal features:
  * representative
  * ticker
  * type
  -* party

-Seeing as all of these are 'categorical' features as opposed to 'quantitative' features, we engineer them into a binary format using a Binarizer and OneHoteEncoder using the sklearn Machine Learning package.
-Finally we incorporate all of these 'engineered' features into a Pipeline object and use a <b>RandomForestClassifier</b> as the predicting feature of our model.
-The metric we will use to judge the prediction will be *accuracy* of the model.

* Baseline Training set Accuracy: *79%**
* Baseline Test set Accuracy: *80%**

## 2) Improved Model 

- This model is attempt to determine whether or not we could increase accuracy scores found in the Baseline Model.
One of the ways through which we can improve our model is adjusting hyperparameters on our RandomForestClassifier class . In our Baseline Model, the hyperparameters we feed into our Random ForestClassfier() were:

* max_depth* = 7
* n_estimators* = 7 

We wanted to see if there was a better combination of these hyperparamters to improve the accuracy of prediciotn model. To achive this, we used <b>GridSearchCV</b>. 

GridSearchCV performs k-fold cross-validation to identify the set of hyperparameters that provides the best validation performance on average from arrays that we created for hyperparameters. 
Upon fitting our training sets on this GridSearchCV() object we use *grids.best_params_* t0 obtain the best combination of hyperparameters:

* max_depth* = 92
* n_estimators* = 44

Using these parameters above allows to obtain a much higher accuracy score from our model:

* Final Training set Accuracy*: **99.8%**

* Final Test set Accuracy*: **99.6%**

These above results imply a satisfactory level of Accuracy for our developed predictive model.






