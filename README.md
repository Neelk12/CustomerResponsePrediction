# Customer Response Prediction

## Overview
This repository contains code and datasets for the machine learning project aimed at predicting customer responses to catalog mailers. It is designed to assist a direct marketing firm in identifying and targeting profitable customers.

## Project Description
A direct marketing firm distributes catalogs to its customer base of about 5 million households. The objective of this project is to help the firm to improve their performance by predicting the customers who are likely to respond and make profitable orders, thereby justifying the printing and mailing costs.

## Dataset
The `dmtrain.csv` dataset includes information about 2,000 customers from the firm's last mailing campaign. It includes the following variables:

- `id`: Customer ID
- `n24`: Number of orders in the last 24 months
- `rev24`: Total order amount ($) in the last 24 months
- `revlast`: Amount of last order ($)
- `elpsdm`: Time elapsed since last order (months)
- `ordfreq`: Order frequency over the last 24 months
- `ordcat`: Order amount category
- `response`: 1 indicates the customer responded, 0 indicates no response

The broad objective is to classify customers who are likely respond to mailers (i.e., response is the dependent variable).

## Project Workflow

### Data Processing
1. Read in the data and review the non-binary variables to see if any are skewed and need to be transformed.

### Decision Tree Classifier
2. Generate a decision tree on the entire dataset, without any limitations on the depth of the tree. Use entropy as the metric. 
3. Identify the best decision tree classifier by pruning the tree at different depths. 

### Random Forest Classifier
4. Develop random forest classifiers with 100 trees, using the three best values of tree depth identified in the previous step. 
5. Repeat this experiment with 50 trees.

### k-Nearest Neighbor Model
6. Identify the best value of k for k-nearest neighbor models using 10-fold cross-validation.

### Logistic Regression Model
7. Develop a logistic regression model using 10-fold cross-validation.
8. Develop a logistic regression model on the entire training dataset. 

### Model Comparison and Selection
9. Perform an evaluation with 10-fold cross-validation on the four best models identified (decision tree, random forest, k-nearest neighbor, logistic regression). 
10. Use the entire dataset to develop a final version of the recommended model for testing.

### Predictions
11. Use the final model to make predictions on new data from `dmtest.csv`.

### Special Focus: Lapsing Customers
12. Compare the quality of predictions for "lapsing customers" relative to predictions for the others on records in the training set.
