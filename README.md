Ethereum ARIMA Forecasting Analysis
Project Overview
This project focuses on analyzing and forecasting the price of Ethereum (ETH) using time series analysis with an ARIMA model. The dataset, sourced from Kaggle, contains historical price data for Ethereum. The project performs exploratory data analysis, checks for stationarity, builds an ARIMA model, evaluates its performance, and generates a 30-day price forecast.
Objectives

Analyze historical Ethereum price trends.
Test for stationarity using the Augmented Dickey-Fuller (ADF) test.
Build and evaluate an ARIMA model for time series forecasting.
Generate and visualize a 30-day price forecast for Ethereum.

Dataset
The dataset used is the "Cryptocurrency Price History" from Kaggle, specifically the coin_Ethereum.csv file, which includes daily price data (Open, High, Low, Close, Volume) for Ethereum.
Methodology

Data Preprocessing:

Load the Ethereum price dataset.
Convert the Date column to datetime and set it as the index.
Sort the data by date to ensure chronological order.


Exploratory Data Analysis (EDA):

Visualize the closing price over time.
Calculate and plot a 24-hour rolling mean to identify trends.
Generate summary statistics for key columns (Open, High, Low, Close, Volume).


Stationarity Testing:

Perform the Augmented Dickey-Fuller (ADF) test on the closing price.
Apply differencing to make the series stationary if needed, and re-run the ADF test.
Plot Autocorrelation (ACF) and Partial Autocorrelation (PACF) to determine ARIMA parameters.


ARIMA Modeling:

Fit an ARIMA(1,1,1) model to the closing price data.
Generate in-sample predictions and evaluate model performance using RMSE and MAPE metrics.


Forecasting:

Forecast Ethereum prices for the next 30 days.
Visualize historical data alongside the forecast.



Tools and Libraries

Python: Programming language used for analysis.
Pandas: Data manipulation and analysis.
NumPy: Numerical computations.
Matplotlib & Seaborn: Data visualization.
Statsmodels: ARIMA modeling and stationarity testing.
Scikit-learn: Performance metrics (RMSE, MAPE).
Kaggle API: Dataset retrieval.
PMDARIMA: Optional for ARIMA parameter tuning (not used in the final model).

Installation

Clone the repository:
git clone https://github.com/your-username/ETH_ARIMA_Forecasting_Analysis.git
cd ETH_ARIMA_Forecasting_Analysis


Install required libraries:
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn kaggle pmdarima


Set up Kaggle API:

Obtain your kaggle.json file from Kaggle.
Place it in the ~/.kaggle/ directory:mkdir -p ~/.kaggle
cp kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json




Download the dataset:
kaggle datasets download -d sudalairajkumar/cryptocurrencypricehistory
unzip cryptocurrencypricehistory.zip



Usage

Ensure the coin_Ethereum.csv file is in the project directory.
Run the Python script (eth_arima_forecasting.py):python eth_arima_forecasting.py


The script will:
Load and preprocess the data.
Generate visualizations (closing price, rolling mean, ACF/PACF plots).
Perform stationarity tests and display results.
Fit the ARIMA model and print its summary.
Calculate and display RMSE and MAPE for in-sample predictions.
Generate and plot a 30-day forecast.



Results

Stationarity: The raw closing price series is non-stationary (ADF p-value > 0.05). After first differencing, the series becomes stationary (p-value < 0.05).
Model Performance: The ARIMA(1,1,1) model is evaluated using RMSE and MAPE, providing insights into prediction accuracy.
Forecast: A 30-day forecast is generated, showing the expected price trend for Ethereum.

Visualizations

Line plot of Ethereum's closing price over time.
Closing price with a 24-hour rolling mean.
ACF and PACF plots for ARIMA parameter selection.
Actual vs. predicted prices for in-sample validation.
Historical data with a 30-day forecast.

Limitations

The ARIMA model assumes linear relationships and may not capture complex patterns in cryptocurrency prices.
The forecast is based on historical data and does not account for external factors (e.g., market sentiment, regulatory changes).
The model uses fixed parameters (1,1,1); further tuning with pmdarima could improve performance.

Future Improvements

Experiment with other time series models (e.g., SARIMA, LSTM).
Incorporate exogenous variables (e.g., Bitcoin prices, market volatility).
Automate ARIMA parameter selection using pmdarima.
Extend the forecast horizon and validate with more recent data.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments

Dataset provided by Sudalai Rajkumar on Kaggle.
Built with Python and open-source libraries.

