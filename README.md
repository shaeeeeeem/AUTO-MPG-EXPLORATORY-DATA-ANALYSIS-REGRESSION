# Auto MPG — Exploratory Data Analysis & Regression Modeling

## Overview
This project explores vehicle fuel efficiency using the classic `auto-mpg.csv` dataset and builds regression models to predict a car's **Miles Per Gallon (`mpg`)** based on its mechanical and technical specifications. It includes end-to-end data cleaning, Exploratory Data Analysis (EDA), feature engineering, model training, and performance evaluation.

---

## Project Objectives
- Inspect and clean raw automotive records, including handling irregular missing value formats (such as `?` in `horsepower`).
- Perform Exploratory Data Analysis (EDA) to uncover relationships between vehicle weight, engine displacement, horsepower, and fuel economy.
- Preprocess categorical and numerical features for regression analysis.
- Train and evaluate regression models to accurately predict vehicle fuel efficiency (`mpg`).

---

## Dataset Description
The dataset contains technical specifications for various car models:

| Feature | Type | Description |
| :--- | :--- | :--- |
| `mpg` | Numeric | Fuel efficiency in Miles Per Gallon (target variable) |
| `cylinders` | Numeric / Discrete | Number of engine cylinders (e.g., 4, 6, 8) |
| `displacement` | Numeric | Engine displacement in cubic inches |
| `horsepower` | Numeric | Engine power in horsepower |
| `weight` | Numeric | Vehicle curb weight in pounds |
| `acceleration` | Numeric | Time to accelerate from 0 to 60 mph (in seconds) |
| `model year` | Numeric / Discrete | Year of manufacture (e.g., 70–82) |
| `origin` | Categorical | Region of origin (`1` = USA, `2` = Europe, `3` = Japan) |
| `car name` | Text | Make and model identifier (dropped during modeling) |

---

## Tech Stack & Libraries
- **Language:** Python
- **Data Manipulation:** `pandas`, `numpy`
- **Visualization:** `matplotlib`, `seaborn`
- **Machine Learning:** `scikit-learn`

---

## Workflow & Methodology

1. **Data Loading & Cleaning:**
   - Load `auto-mpg.csv` and inspect column data types.
   - Replace non-standard missing value markers (`?`) in `horsepower` with `NaN`, convert to numeric, and impute or drop missing records.
   - Drop high-cardinality text identifiers (`car name`) not suited for standard linear modeling.

2. **Exploratory Data Analysis (EDA):**
   - Analyze the distribution of the target variable (`mpg`) using histograms and KDE plots.
   - Examine relationships between continuous predictors (`weight`, `displacement`, `horsepower`) and `mpg` via scatter plots and pair plots.
   - Compare fuel economy across discrete categories (`cylinders`, `origin`, `model year`) using box plots.
   - Visualize multi-collinearity among engine specs using a correlation heatmap.

3. **Data Preprocessing:**
   - One-hot encode categorical variables (`origin`) with `drop_first=True`.
   - Split the dataset into training and testing subsets (e.g., 80/20 split).
   - Apply feature scaling (`StandardScaler` or `MinMaxScaler`) where required.

4. **Model Training & Evaluation:**
   - Train regression models (such as Linear Regression, Ridge/Lasso, or Polynomial Regression).
   - Evaluate model performance on unseen test data using:
     - **$R^2$ Score** (Coefficient of Determination)
     - **Mean Absolute Error (MAE)**
     - **Mean Squared Error (MSE) & Root Mean Squared Error (RMSE)**
   - Inspect residual plots to verify error distribution and model assumptions.

---

## Getting Started

### Prerequisites
Install the required dependencies:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
