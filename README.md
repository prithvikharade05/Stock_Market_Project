# Stock Portfolio Management & Prediction System

A comprehensive Django-based web application for stock portfolio management, sector analysis, and price prediction using machine learning and deep learning models.

![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)
![Django](https://img.shields.io/badge/Django-5.2+-green.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15+-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📊 Features

### 1. Bank Sector Analysis
- Real-time data for major Indian NSE banks
- Current price, daily high/low, market cap, P/E ratio
- 1-year price range with discount percentage
- Detailed stock information with interactive charts

### 2. Portfolio Management
- Create and manage multiple stock portfolios
- Add/remove stocks with purchase details
- Real-time portfolio valuation
- **K-Means Clustering** - Group stocks by similar characteristics
- **PCA Visualization** - 2D visualization of portfolio clusters

### 3. Stock Price Prediction

#### a) Regression-Based Prediction
- **Linear Regression** - Predict next-day prices
- **Logistic Regression** - Predict price direction (up/down)
- Features: RSI, Moving Averages, Volatility, Lag Returns

#### b) ARIMA Time Series Forecasting
- Auto-selection of optimal ARIMA parameters (p, d, q)
- Stationarity testing using Augmented Dickey-Fuller test
- Walk-forward forecasting with volatility-based predictions
- Supports both crypto (BTC-USD) and Indian stocks

#### c) CNN+LSTM Deep Learning
- Hybrid Convolutional + LSTM neural network
- 60-day lookback window for predictions
- Model evaluation with MAE, RMSE, R² metrics
- Multi-day price forecasting

### 4. Live Market Data
- Real-time NIFTY 50 ticker prices
- Daily change percentage
- JSON API endpoints for integration

### 5. Technical Analysis
- **RSI (Relative Strength Index)** - 14-day momentum indicator
- **Moving Averages** - 30-day and 50-day MA
- **P/E Ratio** - Price to earnings valuation
- **Quarterly Financials** - Revenue, profit, EPS data
- **Returns Calculation** - 1W, 1M, 3M, 6M, YTD, 1Y, 3Y, 5Y

## 🛠️ Tech Stack

### Backend
- **Django 5.2** - Web framework
- **Python 3.11+** - Programming language
- **SQLite** - Database

### Data & ML
- **yfinance** - Yahoo Finance data fetching
- **pandas** - Data manipulation
- **numpy** - Numerical computing
- **scikit-learn** - ML algorithms (K-Means, Linear/Logistic Regression, PCA)
- **statsmodels** - ARIMA time series
- **TensorFlow/Keras** - Deep Learning (CNN+LSTM)

### Frontend
- **HTML5/CSS3** - Responsive UI
- **JavaScript** - Interactive charts
- **Chart.js** - Data visualization

## 📁 Project Structure

```
stock/
├── portfolio_project/          # Django project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── portfolio/                  # Main Django app
│   ├── models.py              # Database models
│   ├── views.py               # View controllers
│   ├── urls.py                # URL routing
│   ├── ml_engine.py           # K-Means clustering & PCA
│   ├── arima_engine.py         # ARIMA forecasting
│   ├── cnn_lstm_model.py       # Deep learning prediction
│   ├── regression_engine.py    # Linear/Logistic regression
│   ├── templates/             # HTML templates
│   │   └── portfolio/
│   │       ├── home.html
│   │       ├── bank_sector.html
│   │       ├── bank_detail.html
│   │       ├── portfolio_list.html
│   │       ├── portfolio_detail.html
│   │       ├── stock_prediction.html
│   │       ├── arima_prediction.html
│   │       └── cnn_lstm_prediction.html
│   ├── static/                # Static files
│   │   ├── css/style.css
│   │   └── js/main.js
│   └── data_cache/            # Cached market data
├── requirements.txt           # Python dependencies
├── manage.py                  # Django management script
└── README.md                  # This file
```

## 🚀 Installation

### Prerequisites
- Python 3.11 or higher
- pip package manager

### Step 1: Clone the Repository
```bash
git clone <repository-url>
cd stock
```

### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Run Migrations
```bash
cd portfolio_project
python manage.py migrate
```

### Step 5: Start the Server
```bash
# Using run.bat (Windows)
run.bat

# Or manually
python manage.py runserver
```

### Step 6: Access the Application
Open your browser and navigate to:
```
http://127.0.0.1:8000
```

## 📖 Usage Guide

### Bank Sector Analysis
1. Navigate to **Banks** from the homepage
2. View all major Indian bank stocks with real-time prices
3. Click on any bank to see detailed analysis:
   - Historical price charts
   - Technical indicators (RSI, Moving Averages)
   - P/E ratio over time
   - Quarterly revenue and profit
   - Returns for multiple time periods

### Portfolio Management
1. Go to **Portfolio** section
2. Create a new portfolio with a name
3. Add stocks with:
   - Stock symbol (e.g., HDFCBANK, RELIANCE)
   - Stock name
   - Quantity
   - Purchase price
4. View portfolio value and individual stock performance
5. Use **Cluster** feature to group similar stocks

### Stock Prediction
1. Navigate to **Stock Prediction**
2. Enter stock symbol (e.g., RELIANCE, TCS, HDFCBANK)
3. Choose model type:
   - **Linear** - Predicts next-day price
   - **Logistic** - Predicts price direction probability
4. View historical prices and predictions chart

### ARIMA Forecasting
1. Go to **ARIMA Prediction**
2. Enter stock symbol (Indian stocks) or BTC-USD for cryptocurrency
3. View:
   - Historical price data
   - 7-day forecast
   - Model order (p, d, q)
   - Stationarity test results

### CNN+LSTM Deep Learning
1. Navigate to **CNN+LSTM Prediction**
2. Enter stock symbol
3. View:
   - Historical price chart
   - 5-day predictions
   - Model accuracy metrics (MAE, RMSE, R²)

## 📈 Supported Stocks

### Indian Stock Market All Stocks

### Indian Banks (NSE)
- HDFC Bank, ICICI Bank, State Bank of India
- Axis Bank, Kotak Mahindra Bank, IndusInd Bank
- Bank of Baroda, Punjab National Bank
- IDFC First Bank, Federal Bank

### Major NSE Stocks
- RELIANCE, TCS, INFY, HINDUNILVR, ITC
- BAJFINANCE, MARUTI, M&M, SUNPHARMA
- TATASTEEL, LT, WIPRO, and more...

### Cryptocurrency
- BTC-USD (Bitcoin)

## 🧠 Machine Learning Models

### K-Means Clustering
- Features: P/E Ratio, Discount from 1Y High, Returns (1M, 3M, 6M)
- Scaler: StandardScaler
- Visualization: PCA for 2D projection

### ARIMA
- Parameter Selection: Auto (AIC-based grid search)
- Differencing: Auto (ADF stationarity test)
- Forecasting: Walk-forward method

### CNN+LSTM
- Architecture: Conv1D(64) → MaxPool → LSTM(100) → Dense(50) → Dense(1)
- Lookback: 60 days
- Training: 20 epochs, batch size 32

### Linear/Logistic Regression
- Features: Lag returns, MA20, MA50, Volatility, RSI
- Validation: TimeSeriesSplit (5-fold)

**Built with ❤️ By Prithviraj Kharade**

