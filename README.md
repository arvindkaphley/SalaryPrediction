### Project Summary

This project analyzes and predicts software developer salaries based on survey data. The process involves data cleaning, feature engineering, model training, and prediction. Here's a detailed breakdown of the steps and processes involved:

#### Data Preprocessing

1. **Loading and Initial Cleaning:**
   - The survey data is loaded from a CSV file.
   - Columns of interest (`Country`, `EdLevel`, `YearsCodePro`, `Employment`, and `ConvertedCompYearly`) are selected.
   - The `ConvertedCompYearly` column is renamed to `Salary`.

2. **Handling Missing Values:**
   - Rows with null values in the `Salary` column are removed.
   - The dataset is filtered to include only those who are employed full-time.

3. **Category Shortening:**
   - A function, `shorten_categories`, is created to group countries with fewer than 400 respondents into an "Other" category.
   - The countries are mapped accordingly.

4. **Data Cleaning:**
   - Outliers in salary data are removed, retaining salaries between $10,000 and $250,000.
   - Non-essential categories (countries with low respondent counts) are excluded.

5. **Feature Engineering:**
   - Experience (`YearsCodePro`) is cleaned to convert string ranges to numerical values.
   - Education levels are simplified to categories: `Bachelor's degree`, `Master's degree`, `Post grad`, and `Less than a Bachelor's`.

#### Encoding Categorical Variables

- Label Encoding is applied to `Country` and `EdLevel`.

#### Model Training and Evaluation

1. **Linear Regression:**
   - A Linear Regression model is trained on the dataset.
   - Predictions are made, and the model’s performance is evaluated using Root Mean Squared Error (RMSE).

2. **Decision Tree Regressor:**
   - A Decision Tree Regressor model is trained and evaluated.
   - Hyperparameters are optimized using GridSearchCV to find the best model configuration.

3. **Random Forest Regressor:**
   - A Random Forest Regressor model is trained and evaluated.
   - The model’s performance is compared with previous models using RMSE.

#### Model Saving and Loading

- The final model, along with the label encoders for `Country` and `EdLevel`, are saved using `pickle`.
- The saved model and encoders are loaded to demonstrate prediction on new data.

#### Visualization

- Boxplots are created to visualize the distribution of salaries across different countries before and after removing outliers.

#### Prediction

- A prediction example is provided for an individual from India with a Master’s degree and 15 years of experience, showcasing the model's capability to predict salaries based on input features.

This comprehensive approach leverages various machine learning techniques to clean data, engineer features, train models, and make predictions, offering valuable insights into factors affecting software developer salaries globally.
