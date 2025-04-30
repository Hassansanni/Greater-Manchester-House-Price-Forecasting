# Greater Manchester House-Price Forecasting 🏠📈

**Mini-Data-Science Project** across Easter 2025  
> I explored 20 years of UK house-price data to forecast Greater Manchester’s monthly average price—using seasonal ARIMAX and gradient boosting, plus rolling-origin backtesting against naïve and seasonal benchmarks.  

## 📖 Overview  
1. **Data**  
   - Source: UK ‘pp-complete.csv’ (ONS house-price paid data) & Bank of England Base Rate  
   - Period: 2005–2025, monthly averages for GM & its boroughs  
2. **Exploratory Analysis**  
   - Time series plot + 12-mo rolling average  
   - Boxplots by month & STL decomposition  
   - Year-over-year growth rates  
3. **Models**  
   - **Baseline**  
     - *Naïve* (next month = this month) → MAE ≈ £12 K  
     - *Seasonal* (next March = last March) → MAE ≈ £16 K  
   - **SARIMAX** with exogenous Bank Rate → hold-out MAE ≈ £22 K, no autocorrelation left (Ljung-Box p > 0.05)  
   - **HistGradientBoosting** → one-step MAE ≈ £27 K  
4. **Backtesting**  
   - Rolling-origin (1, 3, 6-mo)  
   - SARIMA outperformed both Prophet (not installed) and HGB for short horizons  
5. **Borough vs GM-wide**  
   - 12-mo ahead forecasts for each borough vs the GM-wide model  


## 🚀 Getting Started

### 1. Clone & install  
```bash
git clone https://github.com/<your-username>/gm-house-forecast.git
cd gm-house-forecast
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
