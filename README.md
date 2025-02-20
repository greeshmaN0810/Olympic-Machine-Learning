# Olympic Medals Prediction Using Linear Regression

### Project Overview
This project aims to predict the number of Olympic medals a country will win based on historical data. The dataset includes information on participating teams, their athletes, average age, and previous medal counts. A linear regression model is built to identify key factors influencing medal counts and make predictions for future Olympic events.

### Data Preprocessing
- Loaded the dataset and selected relevant columns: `team`, `country`, `year`, `athletes`, `age`, `prev_medals`, and `medals`.
- Checked for correlations between predictors and the target (`medals`).
- Visualized relationships using:
  - Scatter plots (`sns.lmplot`) for `athletes` vs `medals` and `age` vs `medals`.
  - Histogram to observe the distribution of `medals`.
- Handled missing values by dropping rows with `NaN` values.

### Model Training & Evaluation
- **Data Splitting:**
  - Training set: Data before 2012.
  - Test set: Data from 2012 and beyond.
  - Maintained an **80:20 train-test split**.
- **Model:** Implemented **Linear Regression** using:
  - `athletes`
  - `prev_medals`
- **Prediction Adjustments:**
  - Ensured no negative predictions by setting values `< 0` to `0`.
  - Rounded predictions for better interpretability.
- **Performance Evaluation:**
  - Used **Mean Absolute Error (MAE)** for assessment.
  - Verified that the MAE was lower than the standard deviation of medals.

### Results & Insights
- The model works well for countries with **larger teams**.
- **Error Analysis by Team:**
  - Computed absolute errors and grouped them by team.
  - Examined the **error ratio** (absolute error / actual medals) to identify accuracy variations.
  - Visualized error distribution using histograms.
- **Key Insight:** Countries sending **more athletes** tend to have **more accurate predictions**.

### Conclusion
- **Strengths:**
  - The model provides reasonable predictions for larger teams.
  - Simple linear regression offers a **baseline approach**.
- **Limitations & Future Work:**
  - The model may not perform well for **small teams** or **countries with few medals**.
  - Additional features such as **GDP, training facilities, and sports funding** could improve accuracy.
  - Future iterations could explore **non-linear models** (e.g., Random Forest, XGBoost) for better predictions.
