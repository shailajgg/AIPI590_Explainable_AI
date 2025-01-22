# Telco Customer Churn Analysis  

This repository contains the code and analysis for understanding and predicting customer churn using a dataset from a telecommunications company. The dataset can be found [here](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/code). The goal is to identify factors contributing to churn and build interpretable models to predict customers at risk of leaving the company.  

## Instructions  

This project involves the following tasks:  

### 1. **Exploratory Data Analysis (EDA) to Check Assumptions**  
- Perform exploratory analysis of the dataset to examine relationships between features and the target variable (churn).  
- Use appropriate visualizations and statistical methods to assess whether assumptions for linear regression, logistic regression, and Generalized Additive Models (GAM) are met.  

### 2. **Linear Regression**  
- Treat the churn variable as a continuous variable (e.g., 0 for staying, 1 for churning).  
- Build a linear regression model to predict churn.  
- Interpret the coefficients and evaluate the model's performance.  

### 3. **Logistic Regression**  
- Treat churn as a binary variable.  
- Build a logistic regression model to predict the probability of churn.  
- Interpret the coefficients.  

### 4. **Generalized Additive Model (GAM)**  
- Build a GAM to model non-linear relationships between customer features and churn.  
- Interpret the results of the GAM model.  

### 5. **Model Comparison**  
- Compare the performance and interpretability of the linear regression, logistic regression, and GAM models.  
- Discuss the strengths and weaknesses of each approach.  
- Provide recommendations on which model(s) the telecommunications company should use to address their customer churn problem.  

## Dataset  

The dataset includes customer demographics, account details, and service usage information. The target variable is `Churn`, indicating whether a customer has left the company (1) or not (0).  
