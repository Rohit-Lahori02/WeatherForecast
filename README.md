# Global Weather Data Analysis Project
Overview
This project analyzes the Global Weather Repository dataset to uncover trends, detect anomalies, and build forecasting models for weather parameters. The analysis encompasses data cleaning, exploratory data analysis (EDA), anomaly detection, forecasting with multiple models (including ensemble techniques), and unique analyses on air quality and geographical weather patterns.

**Project Objectives**
**Data Cleaning & Preprocessing:**

Remove outliers using the Interquartile Range (IQR) method.

Convert date columns to proper datetime objects.

Normalize key variables (temperature and precipitation).

**Exploratory Data Analysis (EDA):**

Analyze correlations among numeric variables with heatmaps.

Visualize time series trends for temperature and precipitation.

Examine the relationship between temperature and other weather parameters through scatter plots and boxplots.

**Anomaly Detection:**

Implement anomaly detection using the IsolationForest algorithm to identify unusual weather observations.

**Forecasting:**

Develop and compare multiple forecasting models including ARIMA, SARIMAX, and Random Forest.

Create an ensemble forecast by weighting individual models based on their performance.

**Unique Analyses:**

Explore the correlation between air quality indicators and weather parameters.

Analyze how weather conditions differ across major countries and continents.

**Methodology**
**Data Cleaning & Preprocessing:**

Loading Data: The dataset is loaded from GlobalWeatherRepository.csv.

Missing Values & Sorting: Missing values are identified, and the data is sorted by the last_updated timestamp.

Outlier Removal: Outliers are removed from key variables (e.g., air_quality_Carbon_Monoxide and wind_mph) using the IQR method.

Normalization: Temperature and precipitation are normalized using a MinMaxScaler, creating new columns (temp_c_scaled, precip_mm_scaled) for analysis.

**Exploratory Data Analysis (EDA):**

Correlation Analysis: A correlation matrix of numeric variables is computed and visualized using heatmaps to reveal relationships.

Time Series Analysis: For a selected country (e.g., the United States of America), time series plots are generated for temperature and precipitation.

Scatter & Boxplots: Scatter plots visualize relationships between temperature and precipitation, while boxplots highlight distribution and anomalies.

**Anomaly Detection:**

The IsolationForest algorithm is applied to features such as temperature, humidity, wind speed, and pressure to detect anomalies. Anomalous points are visualized to assess their impact.

Forecasting with Multiple Models:

**Model Building:**

ARIMA: An ARIMA model (order (5,1,0)) forecasts temperature based on historical data.

SARIMAX: A seasonal ARIMAX model (order (1,1,1), seasonal order (1,1,1,12)) accounts for seasonal effects.

Random Forest: Lag features are created, and a Random Forest Regressor is trained to forecast temperature.

Model Evaluation: Forecast performance is evaluated using Mean Absolute Error (MAE).

Ensemble Forecast: A weighted ensemble of the individual models is constructed to improve forecast accuracy.

**Unique Analyses:**

Air Quality Analysis:

Correlations between weather parameters and various air quality indicators are computed and visualized.

Geographical Analysis:

Average weather conditions are analyzed by major countries and continents to reveal regional differences.

**Results**
EDA Insights:

The correlation heatmap highlighted strong relationships, such as between gust and wind speed, and revealed how Temperature (°C) has a negative correlation with both humidity and pressure_mb.

Time series plots demonstrated seasonal trends in temperature and precipitation for the selected country.

Anomaly Detection:

IsolationForest identified a small percentage of observations as anomalies, helping to flag potential data issues or extreme weather events.

Forecasting Performance:

Individual forecasting models (ARIMA, SARIMAX, Random Forest) were evaluated using MAE. 
ARIMA MAE: 0.95
SARIMAX MAE: 1.25
Random Forest MAE: 1.92


The ensemble forecast, computed via weighted averaging based on MAE, improved overall forecast accuracy compared to individual models.
Weighted Ensemble MAE: 1.01

**Air Quality & Geographic Analyses:**

The heatmap between weather and air quality parameters provided insights into how weather conditions may influence pollution levels.

Bar charts revealed average weather patterns across major countries and continents, highlighting regional climatic differences.

