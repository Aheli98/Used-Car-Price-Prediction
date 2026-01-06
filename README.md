# Used Car Price Prediction & Trust Score Analysis

This project analyzes and predicts used car prices using a dataset of US dealer listings. It applies data cleaning, feature engineering, regression modeling, and trust score evaluation to provide insights into price drivers and model reliability.

## Contents

- Data Loading & Cleaning
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Regression Modeling
- Trust Score Calculation
- Model Evaluation & Visualization
- Price Trend Forecasting

## How to Run
Clone the repository:
`git clone https://github.com/Aheli98/Used-Car-Prediction.git`

## Code Exploration

1. Place `us-dealers-used.csv` in the working directory.
2. Open and run `UsedcarPrediction_Final.ipynb` in Jupyter Notebook or VS Code.
3. Follow the notebook cells sequentially for data analysis, modeling, and visualization.

## Dataset

- **Source:** `us-dealers-used.csv`
- **Features:** Car make, model, year, price, miles, engine size, body type, fuel type, transmission, drivetrain, and more.

## Workflow

### 1. Data Preparation

- Load dataset and inspect for missing values.
- Drop unnecessary columns (`id`, `stock_no`, `seller_name`, `street`).
- Filter for cars manufactured between 2013 and 2022.
- Handle missing values and convert datatypes.

### 2. Feature Engineering

- **Log Transformations:** Reduce skewness in price and miles.
- **Outlier Flags:** Identify outliers using IQR for price and miles.
- **Vehicle Age:** Calculate age from year.
- **Miles per Year:** Estimate usage intensity.
- **Segment:** Group body types into market segments.
- **Fuel Category:** Simplify fuel types.

### 3. Exploratory Data Analysis

- Summary statistics and distribution plots.
- Boxplots for numeric features.
- Correlation heatmaps.
- Bar plots for listings and mean mileage by year.

### 4. Modeling

- **Train/Test Split:** 80% training, 20% validation.
- **Model 1:** Predict log(price) using log(miles), vehicle age, engine size, make, segment, fuel category, transmission, drivetrain.
- **Model 2:** Predict log(price) using vehicle age, miles per year, engine size, engine block, make, segment, fuel category, transmission.
- **Evaluation:** RMSE, R-squared, adjusted R-squared.

### 5. Trust Score Calculation

- Calculate residuals and percentage deviation.
- Compute segment-wise standard deviation of residuals.
- Create a trust flag for predictions within 2 standard deviations.
- Fit a logistic regression to predict trust flag.
- Evaluate trust model accuracy.

### 6. Visualization

- Actual vs. predicted price scatter plots.
- Trust score distribution.
- Price deviation by trust flag.
- Predicted vs. actual price colored by trust score.

### 7. Price Trend Forecasting

- Median price by year.
- Holt’s linear trend model for forecasting future prices.

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels

## Results

- Regression models provide insights into key price drivers.
- Trust scores help assess prediction reliability.
- Price trend forecasting offers future market estimates.

## License

This project is licensed under the MIT License. 
