# 🚀 KaggleX Skill Assessment Challenge: Car Price Prediction

## 🔍 Overview

This repository contains my solution for the **KaggleX Skill Assessment Challeng**e, where I ranked 🥇 `8th out of 1,846 participants`. The challenge required building an accurate machine learning model to predict car prices based on structured data containing attributes such as brand, model year, mileage, transmission type, and fuel type.

This document provides a comprehensive walkthrough of my `data preprocessing strategies`, `feature engineering methodologies`, `model selection` and `evaluation criteria`, and insights gained from the competition. 📊

## 🎯 Problem Statement

The primary challenge of this project was dealing with missing values and inconsistencies in key features like `engine data`, `horsepower`, and `capacity`. Given the diverse nature of the dataset, traditional imputation methods such as classification or clustering were ineffective. Instead, I employed a self-supervised learning approach, leveraging the dataset itself to impute missing values, ensuring greater consistency and accuracy in predictions.

Additionally, handling high-cardinality categorical features, optimizing feature engineering techniques, and deploying an efficient model pipeline were critical aspects of this project. 🏎️💰

## ⚙️ Approach

My methodology was structured into the following key stages:

### 1️⃣ Data Exploration and Cleaning 🔬

Understanding the dataset was crucial for designing an effective modeling pipeline. I conducted:

- **Exploratory Data Analysis (EDA)**:

  - 📈 Visualizing price distributions and identifying key patterns.

  - 🔗 Analyzing correlations between numerical features.

  - 🏷️ Understanding categorical distributions and their impact on pricing.

  - 🧐 Detecting outliers using boxplots and statistical methods.

### 2️⃣ Handling Missing Values 🛠️

A major hurdle was missing values in critical features like `transmission`, `fuel_type`, `horsepower`, and `capacity`. Instead of arbitrary imputation, I employed:

- **Mode-based Imputation** for `transmission`.

- **Domain-aware Substitution** (`'Electric'`) for missing or unsupported `fuel_type`.

- **Self-Supervised Learning-Based Imputation** for `horsepower` and `capacity`, using:

  - **Feature Extraction**: Horsepower and capacity were extracted from engine descriptions using regular expressions (regex).

  - **Contextual Median Imputation**: Missing values were replaced using median values grouped by brand, model, and fuel type to maintain contextual consistency.

  - **K-Nearest Neighbors (KNN) Regression**: Applied to fine-tune imputation, leveraging feature similarities.

This approach ensured that imputed values remained realistic and aligned with actual data trends. 🚀

### 3️⃣ Feature Engineering 🏗️

- 📅 **Vehicle Age Calculation**: Instead of using `model_year` directly, I introduced an `age` feature (`2024 - model_year`).

- 🔢 **Text-to-Numeric Conversion**:

  - 🔍 Extracted engine displacement and horsepower using regex.

  - 📊 Converted `milage` and `price` from string format to numerical values.

- 🎭**Categorical Encoding**:

  - 🎯 **Target Encoding**: Applied to high-cardinality features (`brand`, `model`, `transmission`).

  - 🏷️ **One-Hot Encoding**: Used for `fuel_type` and `accident`, with `drop_first=True`.

- 📏 **Feature Scaling**:

  - **Min-Max Scaling** for `milage`, `age`, `horsepower`, and `capacity`.

  - **StandardScaler** for `brand`, `model`, `transmission`, `int_col`, and `ext_col`.
 
### 4️⃣ Model Selection and Training 🤖

Several machine learning models were tested to identify the best-performing approach:

- 📊 **Linear Regression** (Baseline)

- 🌲 **Random Forest Regressor** (Ensemble Model)

- 🔥 **Gradient Boosting Regressor** (Boosted Trees)

- 🏹 **Support Vector Regression** (SVR) (Kernel-based regression)

- 🏆 **XGBoost Regressor** (Final Model - Best Performance)

- ⚡ **AdaBoost Regressor** (Boosting-based weak learner combination)

🎯 **Hyperparameter Tuning** 🔧

Fine-tuning was performed using `GridSearchCV` and `RandomizedSearchCV`, optimizing:

- Learning rate

- Number of estimators

- Maximum tree depth

- Minimum child weight for XGBoost

### 5️⃣ Model Evaluation 📊

Models were assessed using:

- 📉 **Root Mean Squared Error** (RMSE)

- 📏 **Mean Absolute Error** (MAE)

- 📊 **R² Score**

After extensive evaluation, `XGBoost Regressor` was chosen due to its lowest RMSE and highest R² score. 🏆

### 6️⃣ Feature Importance and Interpretability 🧐

To ensure model interpretability, I conducted:

- 🔍 **Feature Importance Analysis**: Identified `mileage`, `brand`, `model year`, and `fuel type` as key predictors.

- 🛠️ **SHAP Analysis: Applied SHAP** (SHapley Additive Explanations) for detailed interpretation.

### 7️⃣ Handling Outliers and Price Transformation 💰

- 📊 **Log Transformation**: Applied to price to reduce skewness.

- 🚀 **Capping Extreme Values**: Price values were capped at `log(13)` to prevent distortions.

## 🏆 Results

After rigorous experimentation, hyperparameter tuning, and robust preprocessing, I successfully ranked 8th out of 1,846 participants in the KaggleX Skill Assessment Challenge. The final score was 68,976.865, reflecting the model’s high accuracy and generalizability. 📊

This achievement highlights my expertise in handling complex datasets, optimizing machine learning pipelines, and leveraging self-supervised learning techniques for data imputation. 🚀

## 🚀 Running the Code
### 📋 Prerequisites
Ensure all dependencies are installed using:
```cmd
pip install -r requirements.txt
```

### 🏁 Execution Steps
**1️⃣ Clone this repository:**
```bash
git clone https://github.com/ayushgharat234/kagglex-skill-assessment-challenge.git
cd kagglex-car-price-prediction
```

**2️⃣ Run the Jupyter Notebook:**
```cmd
jupyter notebook kagglex-skill-assessment-challenge.ipynb
```

## 🔮 Future Enhancements

- 🤖 **Deep Learning Models (ANNs)**: Explore neural networks for better feature representation.

- 📊 **Advanced Feature Engineering**: Integrate external datasets (e.g., market trends, inflation rates).

- ⚡ **Stacked Ensemble Models**: Experiment with blending techniques.

- 🌍 **Model Deployment**: Develop a Flask or FastAPI web app for real-time predictions.

## 🎯 Conclusion

This project highlights my ability to:
✅ Design end-to-end ML pipelines for structured data.

✅ Implement advanced feature engineering techniques.

✅ Optimize models via hyperparameter tuning and ensemble learning.

✅ Apply SHAP analysis for model interpretability.

✅ Develop production-ready machine learning solutions.

For recruiters, this competition underscores my data science, machine learning, and problem-solving expertise. 🚀

---

📧 **Contact Me**: Connect via [LinkedIn](https://www.linkedin.com/in/ayush-gharat-3500a51a9/) or **email**: `ayushgharat234@gmail.com`. ✉️
