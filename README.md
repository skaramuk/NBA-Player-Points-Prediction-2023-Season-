🏀 NBA Player Points Prediction (2023 Season)

This project aims to predict NBA players’ total points (PTS) for the 2023 season using various machine learning regression algorithms.
The study follows a complete end-to-end ML pipeline including EDA, preprocessing, feature selection, data leakage handling, model comparison, and hyperparameter tuning.

📌 Dataset

Source: Kaggle – NBA Players Stats 2023 Season

Rows: 539 players

Target Variable: PTS (Total Points)

The dataset contains player demographics, playing time, team information, and various performance statistics.

🎯 Objective

The main goal of this project is to:

Predict a player’s total season points (PTS)

Compare multiple regression algorithms

Identify the most suitable model for this task

Demonstrate correct handling of data leakage

🔍 Exploratory Data Analysis (EDA)

Key analyses performed:

Distribution of total points (PTS)

Relationship between minutes played and points

Points by player position

Team win percentage vs scoring

Outlier analysis

Top 10 scorers visualization

EDA results guided feature selection and model design decisions.

⚙️ Data Preprocessing
🧹 Cleaning

Removed player names (PName) as they do not contribute to prediction.

Categorical features (POS, Team) were encoded using One-Hot Encoding.

🚫 Data Leakage Prevention

To avoid unrealistic performance, features that directly or indirectly encode PTS were removed, including:

Shooting statistics (FGM, FTM, 3PM, percentages, etc.)

Fantasy points (FP)

Double-double (DD2) and triple-double (TD3) indicators

This ensured the model learns patterns, not formulas.

🧠 Models Used

The following regression models were implemented and compared:

Linear Regression

Ridge Regression

Lasso Regression

ElasticNet

Decision Tree Regressor

Random Forest Regressor

Gradient Boosting Regressor

XGBoost

LightGBM

Support Vector Regression (SVR)

All applicable models were trained using a Pipeline with StandardScaler.

🔧 Hyperparameter Tuning

GridSearchCV was applied for:

Ridge

Lasso

ElasticNet

RandomizedSearchCV was applied for:

Random Forest

Gradient Boosting

5-fold cross-validation was used with RMSE as the primary scoring metric.

📊 Results Summary
Model	RMSE	R²
Linear Regression	~162	~0.92
Ridge / Lasso	~163–164	~0.91–0.92
ElasticNet	~166	~0.91
LightGBM	~171	~0.91
XGBoost	~179	~0.90
Gradient Boosting	~189	~0.89
Random Forest	~193	~0.89
Decision Tree	~226	~0.84
SVR	Poor	Negative R²

📌 Best Model: Linear Regression
This indicates that the relationship between selected features and total points is largely linear, and simpler models generalize better for this dataset.

🧠 Key Insights

Data leakage can dramatically inflate model performance if not handled carefully.

Removing score-derived features leads to more realistic and reliable results.

Complex ensemble models do not always outperform simpler linear models, especially on structured tabular data.

🛠️ Technologies Used

Python

Pandas, NumPy

Seaborn, Matplotlib

Scikit-learn

XGBoost

LightGBM
