# Stroke Prediction Analysis

**Authors:** Adam Richman & Ava Guy

A comprehensive analysis of stroke risk factors using machine learning techniques to identify key predictors and develop predictive models for early intervention strategies.

## Project Overview

Stroke is a leading cause of death and disability worldwide, making early detection and prevention crucial. This project analyzes the Stroke Prediction Dataset from Kaggle to:

- Identify significant risk factors for stroke
- Develop predictive models using logistic regression and Lasso regression
- Provide insights for healthcare professionals to aid in early intervention strategies

## Objectives

1. **Risk Factor Identification**: Determine which patient characteristics are most predictive of stroke risk
2. **Model Development**: Build and compare logistic regression and Lasso regression models
3. **Clinical Application**: Optimize probability thresholds for practical healthcare use
4. **Performance Evaluation**: Assess model accuracy using ROC curves and precision-recall analysis

## Dataset

The analysis uses the healthcare stroke dataset containing patient information including:

- **Demographics**: Gender, age, marital status
- **Health Conditions**: Hypertension, heart disease, BMI, average glucose level
- **Lifestyle Factors**: Smoking status, work type, residence type
- **Target Variable**: Stroke occurrence (binary: 0 = no stroke, 1 = stroke)

## Methodology

### Data Processing
- Missing value handling and data type conversion
- Categorical variable encoding
- Multicollinearity assessment using Variance Inflation Factor (VIF)

### Model Development
- **Train-Validation-Test Split**: 70%-15%-15% for robust evaluation
- **Stepwise Selection**: Automated feature selection using AIC
- **Lasso Regression**: Regularization technique for feature selection and overfitting prevention

### Model Evaluation
- ROC curve analysis and AUC calculation
- Precision-recall tradeoff analysis
- Cutoff probability optimization for clinical application

## Key Findings

### Primary Risk Factors
The analysis identified the following key predictors of stroke:

1. **Age**: Older patients show significantly higher stroke risk
2. **Hypertension**: Strong predictor of stroke likelihood
3. **Heart Disease**: Major risk factor for stroke occurrence
4. **Smoking Status**: Current and former smokers at elevated risk
5. **Average Glucose Level**: Higher glucose levels associated with increased risk

### Model Performance
- **Lasso Regression**: Retained the most clinically relevant features
- **Optimal Cutoff**: ~30% probability threshold balances precision and recall
- **Clinical Recommendation**: Patients with ≥30% predicted probability should receive enhanced monitoring

## Requirements

### R Packages
```r
library(ggplot2)    # Data visualization
library(dplyr)      # Data manipulation
library(caret)      # Machine learning framework
library(glmnet)     # Lasso regression
library(cluster)    # Clustering analysis
library(corrplot)   # Correlation visualization
library(pROC)       # ROC curve analysis
library(car)        # Regression diagnostics
```

## Installation & Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/Stroke-Prediction-Analysis.git
   cd Stroke-Prediction-Analysis
   ```

2. **Install required R packages**:
   ```r
   install.packages(c("ggplot2", "dplyr", "caret", "glmnet", 
                     "cluster", "corrplot", "pROC", "car"))
   ```

3. **Download the dataset**:
   - Obtain the healthcare stroke dataset from Kaggle
   - Update the file path in the R Markdown file

4. **Run the analysis**:
   ```r
   # Open and knit the R Markdown file
   rmarkdown::render("Stroke_Prediction_Analysis.Rmd")
   ```

## Results Visualization

The analysis includes several key visualizations:

- **Stroke Distribution**: Shows class imbalance in the dataset
- **Correlation Heatmap**: Reveals relationships between variables
- **ROC Curve**: Demonstrates model discriminative ability
- **Precision-Recall Tradeoff**: Guides optimal threshold selection

## Clinical Applications

### Recommended Threshold
- **30% probability cutoff** optimizes the balance between:
  - **High Recall**: Minimizes missed high-risk patients (false negatives)
  - **Reasonable Precision**: Reduces unnecessary interventions (false positives)

### Healthcare Implementation
Patients with ≥30% predicted stroke probability should receive:
- Enhanced monitoring for stroke symptoms
- Further diagnostic screening
- Preventive intervention strategies

## Limitations

1. **Dataset Representativeness**: Kaggle dataset may not reflect global populations
2. **Missing Variables**: Genetic factors, diet, and other health indicators not included
3. **BMI Classification**: Treated as continuous but technically discrete variable
4. **Class Imbalance**: Stroke cases are relatively rare in the dataset

## Future Work

- **Advanced Models**: Explore Random Forest, Neural Networks, and ensemble methods
- **Longitudinal Data**: Incorporate time-series health data for better predictions
- **Class Imbalance**: Apply resampling techniques (SMOTE, undersampling)
- **Feature Engineering**: Create new variables from existing health indicators
- **External Validation**: Test models on independent healthcare datasets
