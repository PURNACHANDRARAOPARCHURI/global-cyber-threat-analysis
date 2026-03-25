# Global Cybersecurity Threat Analysis (2015-2024)

## Project Overview
This project involves the analysis of a dataset containing global cybersecurity threats from 2015 to 2024. The primary goal is to explore trends, identify key attack types, and build a predictive model to classify attack types based on various features.

## Data Source
The data is sourced from `Global_Cybersecurity_Threats_2015-2024.csv`, which includes information such as country, year, attack type, target industry, financial loss, number of affected users, attack source, security vulnerability type, defense mechanism used, and incident resolution time.

## Data Cleaning and Preprocessing
- **Handling Missing Values**: Missing values (represented by empty strings, spaces, 'N/A', 'na', 'null', '-', '--') were replaced with `np.nan`.
- **Duplicate Removal**: Duplicate rows were dropped to ensure data integrity.
- **Critical Column Dropping**: Rows with missing values in 'Country', 'Attack Type', or 'Year' were removed.
- **Numerical Column Imputation**: Zeroes in numerical columns were treated as NaNs and then imputed with the median of their respective columns.
- **Categorical Column Imputation**: Missing values in categorical columns were imputed with the mode of their respective columns.
- **Data Type Conversion**: The 'Year' column was converted to integer type for consistency.
- **Feature Engineering for Modeling**: Categorical features like 'Country' and 'Attack Type' were encoded using `LabelEncoder` for machine learning.

## Exploratory Data Analysis (EDA)
- **Yearly Attack Trends**: Visualized the total number of cybersecurity attacks over time (2015-2024) using a line plot.
- **Attack Type Distribution**: A pie chart illustrates the distribution of different cybersecurity attack types.
- **Geographical Distribution**: A bar chart shows the total cybersecurity threats by country, with countries colored based on incident count.
- **Financial Loss Over Time**: A line plot displays the average financial loss due to cybersecurity incidents over the years.
- **Correlation Analysis**: A heatmap of numerical features was generated to understand relationships between quantitative variables.
- **Density Plots**: KDE plots were used to visualize attack trends over years for each attack type.

## Statistical Analysis & Distributions
- **Normal Distribution**: Fitted a normal distribution to the 'Incidents' column.
- **Poisson Distribution**: Illustrated a Poisson distribution, typically used for modeling event occurrences over time.
- **F-distribution**: Displayed the PDF of an F-distribution.
- **Correlation**: Calculated the correlation between 'Incidents' and a randomly generated 'Severity' column.

## Machine Learning Models
- **Data Splitting**: The data was split into training and testing sets (75% train, 25% test).
- **Feature Scaling**: Numerical features were scaled using `StandardScaler`.
- **Random Forest Classifier**: A Random Forest model was trained to predict 'Attack Type'.
    - **Accuracy**: 15.2%
    - **Classification Report**: Provided detailed precision, recall, and f1-score for each attack type.
    - **Confusion Matrix**: Visualized the performance of the Random Forest model.
    - **Feature Importance**: Identified the most important features in predicting attack types.
- **Logistic Regression**: A Logistic Regression model was also trained.
    - **Accuracy**: 14.27%
    - **Classification Report**: Provided detailed precision, recall, and f1-score for each attack type.
- **Sample Prediction**: Demonstrated how to make a prediction for a sample row using the trained Random Forest model.

## Conclusion
While the current models show limited accuracy in predicting attack types, the exploratory analysis provides valuable insights into global cybersecurity trends, common attack vectors, and their geographical distribution. Further work could involve more advanced feature engineering, trying different machine learning algorithms, or collecting more granular data to improve prediction accuracy.
