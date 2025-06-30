# DataScience_DmartSales

This project looks at and predicts sales for D-Mart stores using the BigMart 2013 dataset. The goal is to create a machine learning model that can predict the sales of a specific product at a particular outlet, based on several features related to the product and outlet.

## Problem Statement:

BigMart has gathered sales data for 1559 products across 10 outlets in different cities. Each product and store has various attributes. The task is to build a regression model that predicts the `Item_Outlet_Sales` for each product-store combination.

## Dataset:
- `train.csv`: Contains training data with features and the target variable `Item_Outlet_Sales`
- `test.csv`: Contains similar features without the target; used for predictions

Key Features:
- Item_Identifier, Item_Weight, Item_Fat_Content, Item_Visibility, Item_Type, Item_MRP
- Outlet_Identifier, Outlet_Establishment_Year, Outlet_Size, Outlet_Location_Type, Outlet_Type

Target Variable:
- Item_Outlet_Sales

## Preprocessing and Feature Engineering:

- Missing values in `Item_Weight` were filled with the mean; missing values in `Outlet_Size` were filled with the mode
- Zero values in `Item_Visibility` were replaced with the mean of the column
- A new categorical feature, `Item_Type_Combined`, was created based on `Item_Identifier` prefixes
- A numerical feature, `Outlet_Years`, was created to show years since establishment
- Label Encoding was applied to categorical variables like `Item_Fat_Content`, `Outlet_Type`, `Outlet_Size`, and others
- Train and test datasets were combined during preprocessing to ensure consistent transformations

## Model:

- Random Forest Regressor from Scikit-learn
- The model was trained on all available features except identifiers
- Predictions were made on the test dataset and saved to `submission.csv`

## Tools and Libraries used:

- Python
- Google Colab
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn

## How to Run:

1. Upload the `train.csv` and `test.csv` files to Google Colab
2. Run the cells to perform preprocessing, model training, and prediction
3. Predictions will be saved and downloaded as `submission.csv`

## Project Status:

Data preprocessing, feature engineering, and model training are complete. Predictions have been generated using the Random Forest Regressor. Future improvements could include model tuning, adding more regressors, and visual exploratory data analysis.
