Beer Rating Prediction
This repository contains a machine learning pipeline for predicting the overall rating of beers based on textual reviews, beer attributes, and user-related information. The project demonstrates advanced feature engineering techniques, text processing using TF-IDF, and model training with Random Forest Regressors.

Table of Contents
Problem Statement
Dataset
Approach
Feature Engineering
Model Training
Results
How to Use
Future Improvements
Problem Statement
Given a dataset containing beer reviews, beer attributes, and user-related features, the goal is to predict the overall rating of the beer (review/overall) using machine learning techniques. The problem is treated as a regression task, with the target variable ranging from 1.0 to 5.0.

Dataset
The dataset consists of the following columns:

Textual Data: review/text
Categorical Data: beer/name, beer/style, user/gender
Numeric Data: beer/ABV, review/appearance, review/aroma, review/palate, review/taste, user/ageInSeconds, review/timeUnix
Approach
Data Cleaning:

Handled missing values for textual, numeric, and categorical data.
Normalized timestamps (review/timeUnix) to align with other numeric features.
Feature Engineering:

Textual features (review/text) processed using TF-IDF Vectorization.
Categorical features (beer/name, beer/style, user/gender) encoded using One-Hot Encoding.
Numeric features (beer/ABV, review/appearance, etc.) standardized to ensure uniform scaling.
Model Training:

Used Random Forest Regressor for prediction.
Evaluated model performance using Mean Squared Error (MSE) and R² Score.
Feature Engineering
TF-IDF Vectorization: Extracted text features from review/text with 100 important terms.
One-Hot Encoding:
Encoded high-cardinality categorical features (beer/name, beer/style) to avoid introducing ordinal relationships.
Standardization:
Scaled numeric features to standardize their ranges, improving model convergence.
Model Training
Algorithm: Random Forest Regressor
Train-Test Split: 80-20 split for training and testing.
Hyperparameters:
Number of Trees (n_estimators): 50
Random State: 42
Results
Mean Squared Error (MSE): Calculated during testing
R² Score: Calculated during testing
Feature importance analysis highlighted key contributors to the model's predictive power, including beer/ABV, review/aroma, and certain terms from review/text.

How to Use
Prerequisites
Python 3.7+
Required Libraries: numpy, pandas, scikit-learn, matplotlib
Steps
Clone this repository:

bash
Copy code
git clone https://github.com/yourusername/beer-rating-prediction.git
cd beer-rating-prediction
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Run the script:

bash
Copy code
python main.py
Future Improvements
Experiment with advanced models like XGBoost or LightGBM for better performance.
Explore Word2Vec embeddings for richer text representation.
Perform hyperparameter tuning to optimize model performance.
Implement frequency encoding for high-cardinality features as an alternative to One-Hot Encoding.
Enhance EDA with deeper analysis of user behavior and beer preferences.
License
This project is licensed under the MIT License. See the LICENSE file for details.
