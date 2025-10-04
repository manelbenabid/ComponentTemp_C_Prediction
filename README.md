# Predictive Analysis of Component Temperature ($ComponentTemp\_C$)

This notebook details the structured machine learning pipeline used to predict the dependent variable, $ComponentTemp\_C$. The workflow focuses on data preparation, dimensional reduction, and rigorous cross-validated model comparison.

## Methodology Steps

### 1. Data Prep & Exploratory Data Analysis

* Initial cleaning involved removing rows where the target variable ($ComponentTemp\_C$) was null.
* The data was partitioned into 70% training and 30% testing sets for development and final validation.
* Exploratory Data Analysis (EDA) was performed, including distribution plots and outlier treatment.
* Feature correlations were investigated, and categorical variables were successfully encoded.

### 2. Feature Selection

* All numerical features were standardized using `StandardScaler` to ensure consistent contribution during training.
* Lasso Regression, utilizing cross-validation, was applied for automated feature selection.
* This step reduced dimensionality, eliminated multicollinearity, and identified the most predictive features for model generalization.

### 3. Model Training and Cross-Validation

* A diverse set of regression models was trained and evaluated using **5-fold cross-validation (CV)** on the selected features:
    * Linear Regression
    * Polynomial Regression
    * Decision Tree Regressor
    * Random Forest Regressor
    * Support Vector Regressor (SVR)
    * K-Nearest Neighbors (KNN)

### 4. Final Model Selection and Interpretation

* The **Random Forest Regressor** demonstrated the best performance among all models tested.
* The final model was retrained on the entire training set.
* Predictions were made on the hold-out test set, and detailed interpretations of the results are provided.
