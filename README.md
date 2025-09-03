# G-Syrup Production Forecasting  

This project builds a **time-series forecasting model** to predict the **monthly production of G-syrup** across 10 provinces using both production history and environmental factors.  

Grople syrup is derived from a fruit that takes months to grow and a few days to process into syrup. The dataset spans **January 2015 – December 2020** for production quantities, and includes related environmental datasets to help capture the effects of climate and vegetation on yield.  

---

## 🎯 Project Goal  

- Predict **monthly G-syrup production (tonnes)** for each province.  
- Incorporate **weather, soil, and vegetation features** into the forecasting model.  
- Explore advanced models such as **ARIMA, LSTM, GRU, and hybrid ML/DL methods** for improved accuracy.  

---

## 📂 Datasets  

### 1. **Production Quantity.csv**  
- **Columns**:  
  - `start_date`, `end_date`: Monthly time window (Jan 2015 – Dec 2020)  
  - `prod`: Production quantity (tonnes)  
  - `region_id`: Province identifier (10 regions)  

### 2. **Daily Precipitation.csv**  
- **Columns**:  
  - `start_date`, `end_date`: Daily window (Jan 1, 2014 – Mar 13, 2022)  
  - `precip`: Daily precipitation (mm)  
  - `region_id`: Province identifier  

### 3. **Daily Soil Moisture.csv**  
- **Columns**:  
  - `start_date`, `end_date`: Daily window (Jan 1, 2014 – Mar 6, 2022)  
  - `smos`: Soil Moisture at 5cm depth (Vol/Vol ratio)  
  - `region_id`: Province identifier  

### 4. **Daily Temperature.csv**  
- **Columns**:  
  - `start_date`, `end_date`: Daily window (Jan 1, 2014 – Mar 13, 2022)  
  - `temp`: Average daily temperature (°C)  
  - `region_id`: Province identifier  

### 5. **Eight Day NDVI.csv**  
- **Columns**:  
  - `start_date`, `end_date`: 8-day window (Dec 27, 2013 – Mar 13, 2022)  
  - `ndvi`: Normalized Difference Vegetation Index ([-1, 1])  
  - `region_id`: Province identifier  

---

## 🧭 Workflow  

### 1. **Data Preprocessing**  
- Aggregate daily/8-day datasets into **monthly values**.  
- Handle missing data via interpolation and smoothing.  
- Normalize and scale features for deep learning models.  

### 2. **Feature Engineering**  
- Climate indices: rolling averages, seasonal lag variables.  
- Vegetation indices (NDVI trends).  
- Temporal features: month, seasonality indicators.  

### 3. **Possible Modeling Approaches**  
- **Classical models**: ARIMA, SARIMA for baseline forecasting.  
- **Machine Learning models**: Random Forest, XGBoost.  
- **Deep Learning models**:  
  - LSTM and GRU for sequential learning.  
  - Hybrid models combining weather + vegetation + production time series.  

### 4. **Evaluation**  
- Metrics:  
  - RMSE (Root Mean Squared Error)  
  - MAE (Mean Absolute Error)  
  - MAPE (Mean Absolute Percentage Error)  
- Cross-validation across multiple provinces.  

---

## 📂 Repository Structure  

- `data/` – All datasets (CSV files)  
- `preprocessing/` – Scripts for cleaning and aggregating daily data  
- `notebooks/` – Jupyter notebooks for exploration and modeling  
- `models/` – Deep learning and statistical forecasting models  
- `results/` – Forecast outputs, error metrics, visualizations  

---

## 🚀 How to Run  

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/grople-syrup-forecasting.git
   cd grople-syrup-forecasting
