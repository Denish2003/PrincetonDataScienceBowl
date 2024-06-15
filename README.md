# Princeton Data Science Bowl: Health Expenditure Prediction

## Project Overview

This project is part of the Princeton Data Science Bowl and aims to predict health expenditure as a percentage of GDP using various health-related indicators. The data processing and machine learning pipeline involve merging multiple datasets, training a neural network model, and evaluating its performance.

## Data Processing

The data processing script cleans and merges multiple datasets into a single Excel file, `merged_data.xlsx`. This file serves as the input for the training and testing phases.

### Steps

1. **Load Datasets**: Various Excel files containing data on air pollution deaths, immunization rates, infectious diseases deaths, life expectancy, smoking deaths, under-fifteen mortality, ozone pollution deaths, and healthcare expenditure are loaded.
2. **Rename Columns**: Columns are renamed for consistency and readability.
3. **Drop Irrelevant Columns**: The 'Code' column is dropped from each dataset.
4. **Filter Data**: The health expenditure data is filtered to include years from 2002 onwards.
5. **Merge Datasets**: All datasets are merged on 'Entity' and 'Year' columns to create a comprehensive dataset.
6. **Save Merged Data**: The final merged dataset is saved as `merged_data.xlsx`.

## Training

The training script utilizes the merged dataset to train a neural network model to predict healthcare expenditure.

### Steps

1. **Load and Clean Data**: The merged dataset is loaded and rows with missing values are dropped.
2. **Feature Selection**: Relevant features are selected for training.
3. **Split Data**: The data is split into training and validation sets.
4. **Standardize Data**: The features are standardized.
5. **Define Model**: A neural network model is defined using TensorFlow.
6. **Compile and Train Model**: The model is compiled with the Adam optimizer and trained on the data.
7. **Save Model**: The trained model is saved as `model.pkl`.

## Testing

The testing script evaluates the trained model on the validation set and identifies the top 10 countries with the highest predicted healthcare expenditure.

### Steps

1. **Load and Clean Data**: The merged dataset is loaded and rows with missing values are dropped.
2. **Feature Selection**: Relevant features are selected for evaluation.
3. **Split Data**: The data is split into training and validation sets.
4. **Standardize Data**: The features are standardized.
5. **Load Model**: The trained model is loaded.
6. **Make Predictions**: Predictions are made on the validation set.
7. **Evaluate Model**: The model's performance is evaluated using MSE, MAE, and R-squared metrics.
8. **Identify Top Countries**: The top 10 countries with the highest predicted healthcare expenditure are identified.

## Results

The model achieved the following evaluation metrics on the validation set:

- **Mean Squared Error (MSE)**: 3.4697
- **Mean Absolute Error (MAE)**: 1.2331
- **R-squared (R2)**: 0.5613

### Top 10 Countries with Highest Predicted Expenditure

1. United States
2. Nauru
3. Marshall Islands
4. Niue
5. Tuvalu
6. Sierra Leone
7. Fiji
8. France
9. Netherlands
10. Germany

## Usage

To reproduce the results:

1. **Data Processing**: Run the data processing script to generate `merged_data.xlsx`.
2. **Training**: Run the training script to train the model and save it as `model.pkl`.
3. **Testing**: Run the testing script to evaluate the model and identify the top countries with the highest predicted healthcare expenditure.
