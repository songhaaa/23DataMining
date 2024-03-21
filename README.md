# 23DataMining
**2023-2 Final project in Data Mining course, majoring in Statistics, Hankuk University of Foreign Studies** </br>
We worked on a data mining project using R to analyze the Wine Quality dataset.</br>
</br>

## Data Mining Team Project Final Report
### 0. Team Members
- Songha Kim (Dept. of Computer and Electronic Systems Engineering, Hankuk University of Foreign Studies)
- Minkyu Jung (Dept. of Computer and Electronic Systems Engineering, Hankuk University of Foreign Studies)
### 1. Project Overview
#### Goal
 - To visually analyze the given dataset, Wine Quality Dataset, to analyze the correlation between quality and other factors such as fixed acidity and volatile acidity, and to classify them into various quality score categories by conducting two experiments using three models. Train three ML models and determine which model is the best.

#### Experimental Settings
- We conducted two experiments. One is to predict quality using all the factors and the other is to predict quality using the factors that are highly correlated with quality through visual analysis (correlation coefficient is greater than 0.2). All experiments were conducted under the following conditions Experiments were run in
- R version: 4.3.2 (2023-10-31)
- R package versions: pROC_1.18.5, reshape2_1.4.4, MASS_7.3-60, MLmetrics_1.1.1, yardstick_1.2.0, caret_6.0-94, lattice_0. 21-9, rpart_4.1.23, randomForest_4.7-1.1, e1071_1.7-14, corrplot_0.92, ggplot2_3.4.4, readr_2.1.4, dplyr_1.1.4

### 2. Project Process
#### Dataset </br> 
→ Wine Quality Dataset (WineQT): https://www.kaggle.com/datasets/yasserh/wine-quality-dataset </br>
 - Size: total data size: 1143 </br>
 - columns : 13 (fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol, quality, Id)
#### Models
 1. **Support Vector Machines (SVM)** </br>
 A binary linear classification model that determines which category a given piece of data belongs to. The goal of SVM is to find the maximum of the margin, which is the distance between support vectors.
 The advantages of SVM models are that they can be used for classification and prediction problems at the same time, and they have less overfitting and higher prediction accuracy than neural network techniques. It is also easy to use.
 The disadvantages of this model include the need for multiple tests to adjust the kernel and model parameters to create an optimized model, long model building time, and poor explanatory power of the results. </br></br>
 2. **Decision Trees** </br>
 A decision tree is a model that represents the predicted value of an input value as a tree with nodes. It is a tree-structured model used to predict or classify a target variable according to the relationship or scale between explanatory variables. It is a methodology based on supervised learning to classify or predict target variables by inputting observations of explanatory variables into the model.
 The main reason for using a decision tree model is that you can check which explanatory variables are the most important influencing factors in predicting or classifying a target variable, and furthermore, you can know the detailed criteria for predicting or classifying each explanatory variable according to the scale. </br></br>
 3. **Random Forest** </br>
 An ensemble model that utilizes the advantages of the existing decision tree and improves the prediction power by reducing the correlation of individual nodes by adding a process of randomly selecting bagging variables. Random forests have the characteristic that the trees have slightly different characteristics from each other due to randomness.
 This characteristic makes the predictions of each tree uncorrelated and has the effect of improving generalization performance. </br></br>
 4. **Logistic Regression** </br>
 A data analysis technique that uses mathematics to find the relationship between two data factors and uses the relationship between the two data to predict the value of one of these factors based on other factors. The prediction usually has a finite number of outcomes.
 Logistic regression has advantages in simplicity, speed, flexibility, and visibility.
