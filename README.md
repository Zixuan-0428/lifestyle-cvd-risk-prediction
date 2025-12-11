# Predicting Cardiovascular Disease from Lifestyle Behaviors
BA810 Machine Learning

Boston University

## Contributors

 Zixiao Jiao | Junyi Liu | Hanchao Tang |Zixuan Zhu

 ## Decription
 
This project applies machine learning techniques to predict cardiovascular disease (CVD) risk using **lifestyle and demographic data only**, without relying on clinical tests or laboratory measurements. The goal is to evaluate how far low-cost, survey-based data can go in identifying high-risk individuals for early prevention.

The analysis is based on the **2015 Behavioral Risk Factor Surveillance System (BRFSS)** dataset and was completed as part of the **BA810 course project (Team B08)**.

## Motivation

Cardiovascular disease is one of the leading causes of death worldwide, yet many cases are preventable through early lifestyle interventions. In many settings, clinical data are expensive or unavailable. This project explores whether **behavioral and demographic information alone** can meaningfully predict CVD risk, providing insight into scalable, population-level prevention strategies.

## Data Source

* **Dataset:** BRFSS 2015 (CDC)
* **Size:** Original dataset >300,000 observations
* **Working sample:** 100,000 randomly sampled records
* **Source:** Kaggle (CDC BRFSS)

The BRFSS survey contains self-reported information on demographics, health behaviors, chronic conditions, and healthcare access. Variables with excessive missingness or irrelevant clinical content were removed to ensure data quality and feasibility.

## Feature Overview

The final feature set focuses on:

* **Demographics:** age group, sex, education, income, marital status, employment
* **Lifestyle behaviors:** smoking status, alcohol consumption, physical activity, fruit and vegetable intake
* **Self-reported health indicators:** general health, physical health days, mental health days
* **Healthcare access (limited):** personal doctor access

The target variable is **coronary heart disease status**, converted into a binary classification outcome.


## Data Preparation

Key preprocessing steps include:

* Random sampling to improve computational efficiency
* Removal of variables with excessive missingness
* Recoding categorical variables based on BRFSS codebooks
* Grouping mixed numeric codes into meaningful categories
* Imputation of missing values using original BRFSS “Don’t know / Refused” codes
* One-hot encoding for all categorical features
* Train–test split using an 80/20 ratio

## Modeling Approach

All models were trained using a unified preprocessing pipeline and evaluated primarily on **recall**, reflecting the importance of identifying at-risk individuals.

Models implemented:

* Logistic Regression (with hyperparameter tuning)
* K-Nearest Neighbors (KNN)
* Decision Tree
* Random Forest
* XGBoost
* Ensemble methods: Voting and Stacking

Cross-validation and randomized hyperparameter search were applied where appropriate.

## Key Results

* **Best-performing models:** Decision Tree and Random Forest
* **Recall:** approximately **0.77–0.79**
* **AUC:** plateaued around **0.83** across multiple models
* KNN and XGBoost performed poorly due to high-dimensional, categorical feature space
* Ensemble methods did not significantly outperform simpler tree-based models

Tree-based models performed best because they naturally capture nonlinear thresholds and interactions common in behavioral survey data.

## Key Insights

* Lifestyle and demographic data alone can meaningfully identify high-risk individuals
* Increasing model complexity does not necessarily improve performance
* Recall–precision trade-offs are unavoidable in prevention-focused classification
* Interpretability remains critical for trust and real-world adoption

## Limitations & Future Work

* Behavioral data may not fully capture physiological disease mechanisms
* Performance appears capped without richer behavioral depth
* Future improvements could include:

* Behavioral intensity measures (e.g., pack-years, diet quality scores)
* Psychological and social factors (stress, depression, social support)
* Environmental context (air quality, walkability, food access)

## Slide Deck
https://docs.google.com/presentation/d/1hKvk3FFPNLbpZ46c7d1ulr6QGg8kuRhD/edit?usp=sharing&ouid=106428496311069685275&rtpof=true&sd=true
