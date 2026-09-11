# IDRA Capstone Project

## Optimizing Supply Chain Logistics: Inventory Management and Demand Forecasting

This project is a data science capstone focused on analyzing supply chain data and building a machine learning model to predict **Units Sold**. The notebook follows a complete workflow from dataset understanding and cleaning through feature engineering, exploratory data analysis, preprocessing, model training, and evaluation.

## Project Overview

The analysis uses a supply chain dataset containing information related to SKUs, warehouses, suppliers, regions, inventory levels, pricing, promotions, lead times, reorder points, order quantities, and demand forecasts.

The main objective is to use these variables to model and forecast product demand, represented by the `Units_Sold` target variable.

## Workflow

The notebook includes the following stages:

1. **Dataset Loading**
   - Loads `P_3_supply_chain_dataset1.csv` using Pandas.
   - Displays the initial dataset.

2. **Dataset Understanding**
   - Checks dataset shape and structure.
   - Generates descriptive statistics.
   - Identifies missing values.
   - Counts duplicate records.

3. **Data Cleaning**
   - Converts the `Date` column to datetime format.
   - Removes duplicate rows.
   - Checks missing values and unique values in `Stockout_Flag`.

4. **Feature Engineering and Preprocessing**
   - Creates `Month`, `DayOfWeek`, and `Quarter` from the date.
   - Creates `Inventory_Gap`, `Price_Margin`, and `Markup_Ratio`.
   - Separates the target (`Units_Sold`) from the predictor variables.
   - Identifies categorical and numerical features.

5. **Exploratory Data Analysis**
   - Analyzes `Units_Sold` by region.
   - Compares average demand by promotion status.
   - Examines correlations with the target variable.
   - Visualizes the distribution of units sold.
   - Visualizes average units sold by promotion status.

6. **Machine Learning**
   - Uses a chronological train/test split with dates up to `2024-10-18` for training and later dates for testing.
   - Applies `StandardScaler` to numerical features.
   - Applies `OneHotEncoder` to categorical features.
   - Uses a `ColumnTransformer` and `Pipeline` to combine preprocessing and modeling.
   - Trains a **Ridge Regression** model.

7. **Model Evaluation**
   - Evaluates training and testing performance using:
     - MAE
     - MSE
     - RMSE
     - R²

8. **Output**
   - Saves the cleaned/preprocessed dataset as:
     `Sharma_Pratyush_Capstone_Cleaned_Preprocessed.csv`

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook / Google Colab

## Project Structure

```text
.
├── Sharma_Pratyush_Capstone_Notebook(1).ipynb
├── P_3_supply_chain_dataset1.csv
├── Sharma_Pratyush_Capstone_Cleaned_Preprocessed.csv
├── requirements.txt
├── .gitignore
└── README.md
```

## How to Run

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Using Jupyter Notebook:

```bash
jupyter notebook
```

Or upload/open the `.ipynb` file in Google Colab.

### 4. Run the notebook

Run the cells from top to bottom. Make sure `P_3_supply_chain_dataset1.csv` is available in the same working directory as the notebook.

## Model

The project uses **Ridge Regression** with `alpha=1.0`.

A preprocessing pipeline is used so that:
- Numerical features are standardized.
- Categorical features are one-hot encoded.
- Unknown categories in the test data are handled safely.
- The preprocessing steps are fitted as part of the training pipeline.

## Evaluation Metrics

The model is evaluated using:

- **MAE (Mean Absolute Error):** Average absolute prediction error.
- **MSE (Mean Squared Error):** Average squared prediction error.
- **RMSE (Root Mean Squared Error):** Square root of MSE, expressed in the target's units.
- **R² (R-squared):** Measures how much variation in the target is explained by the model.

## Output Dataset

After successful execution, the notebook creates:

```text
Sharma_Pratyush_Capstone_Cleaned_Preprocessed.csv
```

## Author

**Pratyush Sharma**

IDRA Capstone Project
