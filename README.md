# Supervised Learning Models for Classification & Regression: Predicting Import-Export Dynamics

## Description
This project demonstrates the application of supervised learning models for both classification and regression tasks. The primary focus is on predicting import-export dynamics using various machine learning techniques. The notebook includes data preprocessing, feature engineering, model building, and evaluation steps.

## Features
- Implementation of statistical techniques (e.g., coefficient of variation, confidence intervals).
- Application of popular supervised learning models.
- Use of visualization tools to explore data and evaluate models.

## Libraries Used
The following libraries are utilized in the project:

- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computations
- `matplotlib.pyplot` - Data visualization
- `seaborn` - Statistical data visualization
- `sklearn` - Machine learning algorithms and utilities
- `statsmodels` - Statistical modeling and hypothesis testing
- `lazypredict` - Quick modeling and baseline comparison
- `scipy` - Statistical and clustering tools
- `time` - Timing utility
- `warnings` - Warnings management

## Key Functions
- `coefficient_of_variation(data)`: Calculates the coefficient of variation for the given data.
- `confidence_interval(data, confidence=0.95)`: Computes the confidence interval for the provided data.
- `categorical_correlation_matrix(df, columns, method='spearman')`: Computes a correlation matrix for categorical variables using a specified method.
- `get_model_run_stats(model, X_train, y_train, X_test)`: Extracts performance metrics for a given model.

## Installation
To run this project, install the required Python libraries. You can use the following command:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels lazypredict
```

## Usage
1. Clone the repository and navigate to the project directory.
2. Open the Jupyter notebook file (`MLM_Project_043.ipynb`).
3. Run the cells sequentially to preprocess the data, train models, and evaluate results.

## Author
- Shefali Dhingra
- Ashish Michael Chauhan

## Acknowledgments
This project uses open-source libraries and draws inspiration from machine learning best practices and statistical analysis techniques.

---
Feel free to customize this README further to include dataset details, specific model results, or any additional context for your project.
