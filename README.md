# NYC Taxi Trip Analysis

This project is intended for Artificial Intelligence & Basic Data Science course's final project.

## Project Objectives | Business Questions

- **Objectives**:
  - Perform data preprocessing and cleaning to ensure data quality.
  - Conduct exploratory data analysis (EDA) to identify patterns in taxi service usage.
  - Develop machine learning models for classification (predicting payment methods) and regression (estimating trip distances).
  - Apply clustering to segment taxi trips for service optimization.
  - Evaluate model performance and report actionable insights.

- **Business Questions**:
  - What are the characteristics and patterns of taxi trips in NYC?
  - How can we predict the payment method a customer will choose?
  - How can we estimate trip distances before a trip starts?
  - How can we segment taxi trips to optimize services?

## Summary of Insights

- **Data Overview**: The dataset, comprising 21 columns and 800,000 rows, compares yellow taxis and Uber, focusing on fares, trip distances, and payment methods. No duplicate rows were found, and columns with over 50% missing values were evaluated for removal.
- **Exploratory Data Analysis**:
  - Trip distance and fare amount strongly correlate with total trip fare (Pearson correlation: 0.79 and 0.94, respectively).
  - No significant relationship exists between passenger count and trip distance.
  - Peak taxi usage occurs at 6:00 PM, aligning with rush hour, with Zone ID 74 (likely a business hub or airport) having the most pickups.
  - Longer trips (over 25 miles) tend to receive higher tips, while short trips (0-5 miles) often have low or no tips.
  - Average trip distance peaks at 5:00 AM (over 8 miles), likely due to airport transfers or out-of-town travel.
- **Machine Learning Models**:
  - **Payment Type Classification**: CatBoost with hyperparameter tuning achieved the best performance (accuracy: 0.9326, F1-score: 0.9373), outperforming Logistic Regression, Random Forest, and XGBoost.
  - **Trip Distance Regression**: XGBoost with hyperparameter tuning performed best (R-squared: 0.965, MAE: 0.342), demonstrating strong predictive capability for trip distances.
- **Clustering Analysis**:
  - KMeans clustering (k=2) yielded the highest Silhouette Score (0.664), identifying two trip segments:
    - **Urban Hopper**: Recreational users traveling outside peak hours (average distance: 2.83 miles, 9.64% tip rate, $2.98 extra charges), likely for leisure activities.
    - **Rush Hour Commuter**: Professional workers traveling during peak hours (average distance: 2.72 miles, 11.54% tip rate, $3.31 extra charges).
  - Hierarchical clustering (complete and average linkage, k=3) provided additional insights into trip characteristics based on extra charges, trip distance, and peak hour activity.
- **Key Takeaways**:
  - Trip distance and fare amount are primary drivers of total fare, while time of day and location significantly influence trip patterns.
  - Advanced tree-based models like CatBoost and XGBoost excel in predicting payment types and trip distances.
  - Clustering reveals distinct user segments, enabling targeted service optimization for recreational and professional users.