# 🩸 Diabetes Prediction using Machine Learning (KNN)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green.svg)

## 📌 Project Overview
This project applies an end-to-end Machine Learning pipeline to predict whether a patient has diabetes based on diagnostic measurements. The primary model used is a **K-Nearest Neighbors (KNN) Classifier**, optimized through rigorous hyperparameter tuning and data preprocessing.

## 🗄️ The Dataset
The dataset includes medical predictor variables and one target variable (`Outcome`). 
* **Features:** Pregnancies, Glucose, Blood Pressure, Skin Thickness, Insulin, BMI, Diabetes Pedigree Function, Age.
* **Target:** `0` (Non-Diabetic) or `1` (Diabetic).
DS
## ⚙️ Methodology & Workflow

### 1. Data Cleaning & Imputation
A critical step in this project was handling hidden missing values. Biological metrics like `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, and `BMI` cannot physically be zero. 
* Invalid `0` values were replaced with `NaN`.
* Missing values were intelligently imputed using the **Mean** (for normally distributed data like Glucose/BloodPressure) and **Median** (for skewed data like BMI/Insulin).

### 2. Exploratory Data Analysis (EDA)
* Generated **Pair Plots** to visualize the distribution of classes across all feature combinations.
* Built a **Correlation Heatmap** to identify the most significant predictive features (e.g., the strong correlation between Glucose levels and the final Outcome).

### 3. Feature Scaling
Distance-based algorithms like KNN are highly sensitive to the magnitude of features. To ensure fair weighting, the dataset was standardized using `StandardScaler` to bring all features to a mean of 0 and a standard deviation of 1.

### 4. Modeling & Hyperparameter Tuning
* Split the data into Training and Testing sets (stratified to maintain class balance).
* Iterated through values of $K$ (from 1 to 14) to find the optimal number of neighbors.
* **Results:** The model achieved its highest testing accuracy of **~76.5%** at **$K=11$**.

## 🚀 How to Run the Project
1. Clone this repository.
2. Install the required dependencies: `pip install -r requirements.txt`
3. Open `diabetes_prediction.ipynb` in Jupyter Notebook or JupyterLab.
4. Run the cells sequentially to see the data processing and model evaluation in action!

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** NumPy, Pandas
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (KNeighborsClassifier, StandardScaler)DS
