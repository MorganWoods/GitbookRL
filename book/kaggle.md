---
description: Kaggle career
---

# Kaggle

## Introduction

> [https://medium.com/datadriveninvestor/introduction-to-kaggle-for-beginners-in-machine-learning-and-data-science-865199d7ead2](https://medium.com/datadriveninvestor/introduction-to-kaggle-for-beginners-in-machine-learning-and-data-science-865199d7ead2)

> clarification, the action of making a statement or situation less confused and more comprehensible;

Dataset - CSV file  
Kernels - Online script editors allow you to execute code without installing python. It make you woking in your browser and explore, model, visualize.  
Discussion - forum  
Blog - with tutorials, announcements.

## Getting started 🌀

### ➡ Titanic: ML from Disaster

In this challenge, we ask you to complete the analysis of what sorts of people were likely to survive. In particular, we ask you to apply the tools of machine learning to predict which passengers survived the tragedy.

Binary classification task

Data dictionary

* _PassengerID_ - A column added by Kaggle to identify each row and make submissions easier
* _Survived_ - Whether the passenger survived or not and the value we are predicting \(0=No, 1=Yes\)
* _Pclass_ - The class of the ticket the passenger purchased \(1=1st, 2=2nd, 3=3rd\)
* _Sex_ - The passenger's sex
* _Age_ - The passenger's age in years
* _SibSp_ - The number of siblings or spouses the passenger had aboard the Titanic
* _Parch_ - The number of parents or children the passenger had aboard the Titanic
* _Ticket_ - The passenger's ticket number
* _Fare_ - The fare the passenger paid
* _Cabin_ - The passenger's cabin number
* _Embarked_ - The port where the passenger embarked \(C=Cherbourg, Q=Queenstown, S=Southampton\)

```python
pd.df.pivot_table(index=None, columns=None, values=None)
'''in the dataframe, the index refer to the name of rows (first 
colums), columns refer to name of columns (first rows)'''
pd.df.plot.bar()
```

**Categorical features**,  is a variable that can take on one of a limited, and usually fixed number of possible values, assigning each individual or other unit of observation to a particular group or nominal category on the basis of some qualitative property.  
we can separate this continuous feature into a categorical feature by dividing it into ranges. We can use the `pandas.cut()` function to help us out.

```text
pandas.cut()
df.fillna()
```

three columns may be useful for predicting survival, sex, pclass, age.

create dummy columns for each unique value. Use the create\_dummies\(\) function to create dummy variables.

#### Machine Learning models

**Logistic Regression**, model for classification. We use the scikit-learn library.

* Instantiate \(or create\) the specific machine learning model you want to use
* Fit the model to the training data
* Use the model to make predictions
* Evaluate the accuracy of the predictions
* Each model in scikit-learn is implemented as a separate class and the first step is to identify the class we want to create an instance of. In our case, we want to use the LogisticRegression class.

The `.fit()` method accepts two arguments: X and y. X must be a two dimensional array \(like a dataframe\) of the features that we wish to train our model on, and y must be a one-dimensional array \(like a series\) of our target, or the column we wish to predict.

[`model_selection.train_test_split()`](http://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html) function that we can use to split our data.  it accepts two parameters X and Y, returns four objects: `train_X, train_y, test_X, test_y`

Once we have fit our model, we can use the `LogisticRegression.predict()` method to make predictions.

Get more accuracy error measurement by using cross validation. The most common form of cross validation is called k-fold cross validation.

```python
cross_val_score(estimator, X, y, cv=None)
# estimator is the estimator object
# X is all features
# y is the target variables
# cv specifies the number of folds
```























## NaN

