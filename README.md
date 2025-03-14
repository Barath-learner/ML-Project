
# Crime Rate Prediction Using Linear Regression

## Introduction

This project aims to predict crime rates in standard metropolitan areas using a linear regression model.  The dataset used is the "Standard Metropolitan Areas Dataset," which contains various socio-economic features.  The target variable is `crime_rate`, and the model attempts to establish a predictive relationship between the features and the crime rate.

## Dataset Description

The dataset comprises 99 entries with the following features:

*   **land_area:** Land area in square miles (integer).
*   **percent_city:** Percentage of the population living in urban areas (float).
*   **percent_senior:** Percentage of the population that is senior citizens (float).
*   **physicians:** Number of physicians (integer).
*   **hospital_beds:** Number of hospital beds (integer).
*   **graduates:** Percentage of high school graduates (float).
*   **work_force:** Size of the workforce in thousands (float).
*   **income:** Median income in dollars (integer).
*   **region:** Region code (integer).

The target variable is:

*   **crime_rate:** Crime rate per 100,000 people (float).
## Data Preprocessing

*   **Missing Values:** The dataset was inspected for missing values using `data.isna().sum()`, and no missing values were found.
*   **Data Types:** All features are numerical (integer or float), as confirmed by `data.info()`.  Therefore, no categorical encoding was necessary.
*   **Feature and Target Separation:** The features (`x`) were separated from the target variable (`y = crime_rate`) using Pandas column selection.

## Model Selection

Linear regression was chosen as the modeling technique due to its simplicity and interpretability.  It serves as a good baseline for regression tasks and allows us to explore potential linear relationships between the socio-economic features and the crime rate.

## Model Training and Evaluation

### Methodology

1.  **Data Splitting:** The dataset was divided into training and testing sets using `train_test_split` from Scikit-learn.  80% of the data was allocated for training (`x_train`, `y_train`), and 20% for testing (`x_test`, `y_test`).
2.  **Model Initialization:** A `LinearRegression` model was instantiated from Scikit-learn.
3.  **Model Training:** The model was trained on the training set using the `fit` method.  This allows the model to learn the coefficients for the linear relationship.
4.  **Prediction:** Predictions (`y_hat`) were generated for the test set using the `predict` method.

### Evaluation Metrics

*   **R² Score on Test Set:** The model's performance on the test set was evaluated using the R² score (`r2_score`).  This metric measures the proportion of variance in the dependent variable (crime rate) that is explained by the model.  The calculated R² score was approximately 0.285, indicating that the model explains about 28.5% of the variance in the test set's crime rates.
*   **Model Score on Entire Dataset:** The model's score on the full dataset (`x`, `y`) was computed using the `score` method.  This yielded a value of approximately 0.502, suggesting that the model explains about 50.2% of the variance when evaluated on all the data.

### Interpretation

*   The R² score of 0.285 on the test set indicates limited predictive power.  The linear regression model captures only a modest portion of the variability in crime rates.
*   The higher score of 0.502 on the entire dataset may suggest some overfitting or a better fit to the training data (which is included in the full dataset).  It's important to prioritize the test set score for a more realistic assessment of the model's generalization ability.


## Conclusion
The linear regression model provides some predictive capability for crime rates based on the socio-economic features in the dataset. However, the R² score of 0.285 on the test set suggests that the model's performance is suboptimal, capturing less than a third of the variance in crime rates. The higher score of 0.502 on the entire dataset indicates moderate explanatory power but highlights potential limitations in generalizing to unseen data (overfitting). These results suggest that a simple linear model may not fully capture the complexities influencing crime rates. Further investigation with more complex models or feature engineering might be beneficial.
