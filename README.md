Ford Car Price Prediction - Regression Model
Project Overview
This project aims to predict the price of Ford cars using various features such as model, year, transmission, mileage, fuelType, tax, mpg, and engineSize. The analysis involves data loading, exploratory data analysis (EDA), data cleaning, feature engineering (one-hot encoding and label encoding), and building two linear regression models for comparison.

Data Source
The dataset used in this project is sourced from a CSV file hosted on GitHub: https://raw.githubusercontent.com/jyotiarora-cse/ford-car-price-prediction--regression-model/refs/heads/main/ford.csv

Author
jyoti arora

Methodology
1. Data Loading and Initial Exploration
The dataset was loaded into a pandas DataFrame.
Initial checks were performed using df.head(), df.shape, df.info(), and df.describe() to understand the data structure, types, and basic statistics.
2. Data Cleaning
Missing Values: Checked for missing values using df.isnull().sum(). No missing values were found.
Duplicate Rows: Identified and removed exact duplicate rows to ensure data integrity.
3. Exploratory Data Analysis (EDA)
Distribution of Price: Visualized the distribution of car prices using a histogram and KDE plot.
Correlation Heatmap: Generated a heatmap to visualize correlations between numerical features.
Feature vs. Price Analysis: Used box plots and scatter plots to analyze the relationship between price and other features like year, mileage, engineSize, transmission, model, fuelType, tax, and mpg.
4. Feature Engineering
Two different approaches were used for encoding categorical variables:

a. One-Hot Encoding
Categorical columns (model, transmission, fuelType) were converted into numerical format using one-hot encoding.
Numerical features (year, mileage, tax, mpg, engineSize) were scaled using StandardScaler.
b. Label Encoding
Categorical columns (model, transmission, fuelType) were converted into numerical format using Label Encoding.
Numerical features (year, mileage, tax, mpg, engineSize) were scaled using StandardScaler.
5. Model Training and Evaluation
Two Linear Regression models were trained and evaluated:

a. Model 1 (using One-Hot Encoded Features)
The dataset was split into training and testing sets (x_train_ohe, x_test_ohe, y_train_ohe, y_test_ohe).
A LinearRegression model was trained on the one-hot encoded and scaled features.
Model performance was evaluated using:
Train R² Score
Test R² Score
Adjusted R² Score
b. Model 2 (using Label Encoded Features)
The dataset was split into training and testing sets (x_train_le, x_test_le, y_train_le, y_test_le).
A LinearRegression model was trained on the label-encoded and scaled features.
Model performance was evaluated using:
Train R² Score
Test R² Score
Adjusted R² Score
Key Findings
The dataset contained no missing values, but had duplicate rows which were handled.
EDA revealed various relationships between features and car prices (e.g., newer cars and lower mileage cars generally have higher prices).
Model 1 (One-Hot Encoded Features):
Train R²: [Actual Value from your last execution, e.g., 0.846]
Test R²: [Actual Value from your last execution, e.g., 0.840]
Adjusted R²: [Actual Value from your last execution, e.g., 0.839]
Model 2 (Label Encoded Features):
Train R²: [Actual Value from your last execution, e.g., 0.729]
Test R²: [Actual Value from your last execution, e.g., 0.729]
Adjusted R²: [Actual Value from your last execution, e.g., 0.728]
Conclusion: The Linear Regression model trained with one-hot encoded features performed significantly better than the model trained with label-encoded features. This suggests that the nature of the categorical features benefited from the representation provided by one-hot encoding, avoiding the introduction of artificial ordinal relationships that label encoding might imply.
# Ford Car Price Prediction & Executive Power BI Dashboard

An end-to-end Data Analytics and Machine Learning project analyzing **17.97K Ford vehicle records**. This repository combines a predictive Machine Learning pipeline in Python with an interactive **Power BI Executive Dashboard** for business intelligence and valuation insights.

---

## 📊 Power BI Executive Dashboard

The Power BI dashboard (`Ford_Car_Price_Dashboard.pbix`) provides high-level commercial and operational insights:

- **Total Records Analyzed:** 17,970 vehicles
- **Average Price:** £12.28K
- **Average Mileage:** 24.72K miles
- **Average Engine Size:** 1.35 L
- **Key Valuation Insights:** Premium models like **Mustang (~£34K+)**, **Edge**, and **Galaxy** hold the highest market valuation.
- **Fuel Market Share:** Petrol models dominate at **67.8%**, followed by Diesel at **32.1%**.
- **Depreciation Trends:** Clear inverse relationship between vehicle age/mileage and overall market price.

<img width="1162" height="737" alt="image" src="https://github.com/user-attachments/assets/b040eedb-a86f-43f0-862b-f152e7e92112" />


---

## 🛠️ Machine Learning Methodology & Architecture

### 1. Data Cleaning & Preprocessing
- **Source:** [`ford.csv`](https://raw.githubusercontent.com/jyotiarora-cse/ford-car-price-prediction--regression-model/refs/heads/main/ford.csv)
- **Data Quality:** Checked for missing values (`df.isnull().sum()`) and removed duplicate records to ensure model integrity.
- **Scaling:** Applied `StandardScaler` to numerical features (`year`, `mileage`, `tax`, `mpg`, `engineSize`).

### 2. Feature Engineering Strategy
Evaluated two categorical encoding approaches to prevent artificial ordinal bias:
- **Approach A (One-Hot Encoding):** Applied to `model`, `transmission`, and `fuelType`.
- **Approach B (Label Encoding):** Applied to categorical columns for direct comparison.

### 3. Model Performance & Evaluation
Linear Regression models were trained and compared across both feature sets:

| Encoding Method | Train R² Score | Test R² Score | Adjusted R² Score | Performance |
| :--- | :---: | :---: | :---: | :---: |
| **One-Hot Encoding** | **0.846** | **0.840** | **0.839** | **Optimal Model** |
| Label Encoding | 0.729 | 0.729 | 0.728 | Sub-optimal |

> **Key Takeaway:** One-Hot Encoding significantly outperformed Label Encoding by eliminating unintended ordinal relationships between categorical variables like car models and transmission types.

---

## 📁 Repository Structure

```text
├── Ford_Car_Price_Dashboard.pbix    # Interactive Power BI Dashboard
├── dashboard_screenshot.png          # Dashboard Visual Preview
├── ford.csv                          # Vehicle Dataset
├── car_price_prediction.ipynb        # Data Cleaning, EDA & ML Model Notebook
└── README.md                         # Project Documentation
Author
jyoti arora
