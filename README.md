# 🔥 Algerian Forest Fire Prediction

A Machine Learning project for predicting the **Fire Weather Index (FWI)** using meteorological and fire-weather data from the Algerian Forest Fires dataset.

## 📌 Project Overview

Forest fires are influenced by various weather and environmental conditions such as temperature, humidity, wind speed, rainfall, and moisture levels.

In this project, different Machine Learning regression models are trained to predict the **Fire Weather Index (FWI)**.

The project covers the complete workflow:

```text
Raw Dataset
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Feature Selection
     ↓
Feature Scaling
     ↓
Train-Test Split
     ↓
Model Training
     ↓
Model Evaluation
```

## 🎯 Objective

The main objective of this project is to predict **FWI (Fire Weather Index)** using meteorological and fire-related features.

This is a:

**Supervised Learning → Regression Problem**

because FWI is a continuous numerical value.

---

## 📊 Dataset

The project uses the **Algerian Forest Fires Dataset**, which contains weather and fire-related observations from two regions of Algeria.

### Features

| Feature     | Description             |
| ----------- | ----------------------- |
| Temperature | Temperature             |
| RH          | Relative Humidity       |
| Ws          | Wind Speed              |
| Rain        | Rainfall                |
| FFMC        | Fine Fuel Moisture Code |
| DMC         | Duff Moisture Code      |
| DC          | Drought Code            |
| ISI         | Initial Spread Index    |
| BUI         | Buildup Index           |
| FWI         | Fire Weather Index      |
| Classes     | Fire / Not Fire         |
| Region      | Region identifier       |

---

## 📁 Project Structure

```text
algerian-forest-fire-prediction/
│
├── data/
│   ├── Algerian_forest_fires_dataset_UPDATE.csv
│   └── Algerian_forest_fires_cleaned_dataset.csv
│
├── notebooks/
│   ├── data_cleaning_and_eda.ipynb
│   └── model_training.ipynb
│
├── README.md
└── requirements.txt
```

### `data/`

Contains the original and cleaned datasets.

### `notebooks/`

Contains the notebooks used for data cleaning, EDA, feature preparation, and model training.

### `README.md`

Contains project documentation.

### `requirements.txt`

Contains the Python libraries required to run the project.

---

# 🧹 Data Cleaning

The original dataset contains some formatting and data-quality issues.

The following steps were performed:

* Loaded the dataset
* Checked missing values
* Removed invalid rows
* Added the `Region` feature
* Removed extra spaces from column names
* Converted columns to appropriate data types
* Encoded the `Classes` feature
* Created a cleaned dataset

After cleaning, the dataset contains **243 observations**.

---

# 📈 Exploratory Data Analysis

EDA was performed to understand the data and relationships between the variables.

The analysis includes:

* Missing-value analysis
* Feature distributions
* Fire vs. Not Fire distribution
* Correlation analysis
* Correlation heatmap
* Box plots
* Monthly fire analysis
* Region-wise analysis

### Class Distribution

```text
Fire       → 137 observations
Not Fire   → 106 observations
```

---

# 🛠️ Feature Preparation

The target variable is:

```text
FWI
```

The following features were removed before model training:

```text
day
month
year
```

The `Classes` feature was encoded as:

```text
not fire → 0
fire     → 1
```

---

# ✂️ Train-Test Split

The dataset was divided into:

```text
75% → Training Data
25% → Testing Data
```

using `train_test_split()` with:

```text
random_state = 42
```

This resulted in:

```text
Training samples → 182
Testing samples  → 61
```

---

# 🔗 Feature Selection

Correlation analysis was performed to identify highly correlated features.

A correlation threshold of **0.85** was used to identify highly correlated features and reduce multicollinearity.

The number of features was reduced from:

```text
11 → 9 features
```

---

# ⚖️ Feature Scaling

`StandardScaler` from Scikit-learn was used to standardize the features.

The scaler was fitted only on the training data and then applied to the testing data to avoid data leakage.

---

# 🤖 Machine Learning Models

The following regression models were trained:

* Linear Regression
* Ridge Regression
* RidgeCV
* Lasso Regression
* LassoCV
* ElasticNet
* ElasticNetCV

---

# 📊 Model Evaluation

The models were evaluated using two metrics.

### MAE — Mean Absolute Error

MAE measures the average absolute difference between the actual and predicted FWI values.

**Lower MAE indicates better performance.**

### R² Score

R² measures how well the model explains the variation in FWI.

**Higher R² indicates better performance.**

---

# 🏆 Results

| Model                 |        MAE |   R² Score |
| --------------------- | ---------: | ---------: |
| **Linear Regression** | **0.5468** | **0.9848** |
| Ridge Regression      |     0.5642 |     0.9843 |
| RidgeCV               |     0.5642 |     0.9843 |
| LassoCV               |     0.6200 |     0.9821 |
| ElasticNetCV          |     0.6576 |     0.9814 |
| Lasso Regression      |     1.1332 |     0.9492 |
| ElasticNet            |     1.8822 |     0.8753 |

## 🥇 Best Model

Based on the current test-set results, **Linear Regression** performed the best.

```text
MAE ≈ 0.5468
R²  ≈ 0.9848
```

The model explains approximately **98.48% of the variation in the test-set FWI values**.

---

# 🧰 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

# ⚙️ Installation

Clone the repository:

```bash
git clone <your-github-repository-url>
```

Navigate to the project directory:

```bash
cd algerian-forest-fire-prediction
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

---

# ▶️ How to Run

### Step 1 — Data Cleaning and EDA

Open:

```text
notebooks/data_cleaning_and_eda.ipynb
```

Run the notebook from beginning to end.

This notebook performs:

* Data cleaning
* Data preprocessing
* Exploratory data analysis
* Data visualization

It generates the cleaned dataset:

```text
data/Algerian_forest_fires_cleaned_dataset.csv
```

### Step 2 — Model Training

Open:

```text
notebooks/model_training.ipynb
```

Run the notebook from beginning to end.

This notebook performs:

* Feature preparation
* Train-test splitting
* Correlation analysis
* Feature selection
* Feature scaling
* Model training
* Model evaluation
* Model comparison

---

# 🚀 Future Improvements

Possible improvements for this project include:

* Try Random Forest Regression
* Try Gradient Boosting
* Try XGBoost
* Perform more extensive hyperparameter tuning
* Use K-Fold Cross Validation
* Save the trained model
* Build a Streamlit prediction application
* Create a simple web interface for FWI prediction

---

# 👨‍💻 Author

**Richa Mathur**

Machine Learning Project — Algerian Forest Fire Prediction
