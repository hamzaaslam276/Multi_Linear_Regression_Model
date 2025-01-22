# Hiring Salary Prediction

This repository demonstrates a Linear Regression model implemented in Python to predict employee salaries based on experience, test scores, and interview scores. The project showcases data preprocessing, handling missing values, and building predictive models using Scikit-learn.

## Table of Contents
1. [Overview](#overview)
2. [Dataset](#dataset)
3. [Features](#features)
4. [Libraries Used](#libraries-used)
5. [Model Workflow](#model-workflow)
6. [Results](#results)

---

## Overview
The goal of this project is to predict employee salaries using a machine learning approach. The dataset includes employee attributes like experience, test scores, and interview performance, which are used to train a Linear Regression model for accurate salary prediction.

## Dataset
The dataset (`hiring.csv`) contains the following columns:

- **experience**: Candidate's years of experience (e.g., "five", "two")
- **test_score(out of 10)**: Test score achieved by the candidate
- **interview_score(out of 10)**: Score received during the interview
- **salary($)**: Actual salary of the candidate (target variable)

### Sample Data:
| experience | test_score(out of 10) | interview_score(out of 10) | salary($) |
|------------|-----------------------|----------------------------|-----------|
| NaN        | 8.0                   | 9                          | 50000     |
| five       | 6.0                   | 7                          | 60000     |
| two        | 10.0                  | 10                         | 65000     |
| seven      | 9.0                   | 6                          | 70000     |
| NaN        | 8.0                   | 6                          | 45000     |

## Features
The model uses the following features for prediction:
1. **Experience**: Converted from text (e.g., "five") to numeric values using the `word2number` library.
2. **Test Score**: Missing values filled with the mean test score.
3. **Interview Score**: Directly used from the dataset.

## Libraries Used
- **NumPy**: For numerical operations.
- **Pandas**: For data manipulation and preprocessing.
- **Matplotlib**: For visualizing data (if required).
- **Scikit-learn**: For building the Linear Regression model.
- **Word2Number**: For converting words to numeric values in the "experience" column.

## Model Workflow
1. **Data Preprocessing**:
    - Handle missing values in the "experience" column by replacing `NaN` with "zero" and converting words to numbers.
    - Replace missing values in "test_score(out of 10)" with the mean test score.

2. **Feature Selection**:
    - Use `experience`, `test_score(out of 10)`, and `interview_score(out of 10)` as input features.
    - Use `salary($)` as the target variable.

3. **Model Training**:
    - Fit a `LinearRegression` model using Scikit-learn.

4. **Prediction**:
    - Predict salaries for new candidate profiles.

### Example Predictions:
- Candidate with 6 years of experience, a test score of 8, and an interview score of 7:
  ```python
  reg.predict([[6, 8, 7]])
  # Output: [65329.12]
  ```

- Candidate with 12 years of experience, a test score of 10, and an interview score of 10:
  ```python
  reg.predict([[12, 10, 10]])
  # Output: [93747.80]
  ```

## Results
The model predicts salaries accurately based on the given features, allowing hiring managers to estimate compensation based on candidate profiles.
