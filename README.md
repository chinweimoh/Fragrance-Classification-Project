# Introduction

The purpose of the project is to accurately classify the fragrances 1, 2, 3 & 4 based on the data logged on 12 different human subjects on the brainwave activities in the alpha, delta and theta wave spectrum. 20 channels of 5 explanatory variables - alpha wave, delta wave, theta wave, sample entropy and Higuchi Fractal Dimension - are given for every row. The approach for the project shown in the notebook is to visualise the data, clean the data and, finally, model the data to determine highest accuracy score.

# Data Exploration

Data is visualized using matplotlib to identify their distribution and determine the best data cleaning techniques. To clean the data, columns found to have logarithmic distributions (such as Alpha, Delta and Theta variables) are logged (using natural logarithm) and scaled using MinMaxScaler from Scikit-Learn to be more normally distributed. This allows some ML algorithms such as regression techniques to perform better.

Also, outliers that lie outside of 3 standard deviations are treated as extreme values and are removed.

# Dimension Reduction Techniques

Dimension reduction techniques are also applied to engineer variables that contains information from all the columns. The techniques used here are Principle Component Analysis (PCA), Linear Discriminant Analysis (LDA), Independent Component analysis (ICA). These methods are applied and the accuracies are be compared.

# Machine Learning Algorithms

Five machine learning modelling techniques are used after each data cleaning method and dimension reduction:

-   Logistic Regression,
-   K-Nearest Neighbour Classifier,
-   Support Vector Machine,
-   Random Forest Classifier and,
-   Decision Tree Classifier

to classify the fragrances. An accuracy score is then calculated based on whether the model predicted the test dataset correctly and a confusion matrix is shown to see the accuracy across the 4 fragrances.

# Cross Validation

The accuracy of the result is further complimented using cross validation. An average accuracy score is calculated using StratifiedKFold cross validation technique that randomly splits training and test data to 5-fold splits. Multinomial Logistic Regression performed the best with an average of **89.5%**. Therefore, this method is used in conjunction with the data cleaning techniques for this project.

# Conclusion

**Removing the rows that contain outliers beyond 3 standard deviations, reduce the dimensions using linear discriminant analysis and modelling with logistic regression produced the highest average accuracy score of 89.5%.**
