# Predictive Model Based Power Price Tagging Under Deregulated Environment

## Project Details
- **Project Title:** Predictive Model Based Power Price Tagging Under Deregulated Environment  
- **Topic:** Time Series Forecasting and Optimization in Energy Markets  

---

## Project Overview
**Objective:**  
Develop a predictive framework that combines **time series forecasting** and **Genetic Algorithm optimization** to:  
1. Forecast electricity prices (Market Clearing Price – MCP).  
2. Optimize generation cost through Economic Load Dispatch (ELD).  
3. Integrate both results to generate **dynamic price tags**.  

This project addresses the challenge of fluctuating prices in deregulated markets by creating a hybrid solution that balances **market prediction** and **economic efficiency**.

---

## Dataset and Preprocessing
- **Data:** Historical MCP and demand values.  
- **Preprocessing Steps:**  
  - Removed missing/duplicate entries.  
  - Normalized and scaled the data.  
  - Split into training and testing sets.  

---

## Exploratory Data Analysis (EDA)

### Trend and Seasonality
- MCP showed clear **temporal trends** with demand cycles.  
- Daily and weekly seasonality patterns were observed.  
- Volatility spikes highlighted the need for robust forecasting.  

**Figure 1:** Historical Market Clearing Price (MCP) trends.  
![MCP Trend](results/mcp_trend.png)  

### Distribution Analysis
- MCP distribution showed concentration around certain ranges.  
- Peak hours had higher variability.  

**Figure 2:** Distribution of MCP values.  
![MCP Distribution](results/mcp_distribution.png)  

---

## Forecasting Models

### ARIMA
- Captures linear dependencies in time series.  
- Provided a baseline for MCP prediction.  

### SARIMA
- Extended ARIMA with seasonal components.  
- Better performance on cyclical price patterns.  

### LSTM
- Deep learning sequential model.  
- Captured nonlinear relationships and long-term memory.  
- Achieved the **best accuracy**.  

**Example Forecast Input:**  
Historical MCP data for the past 30 days.  

**Example Forecast Output (Next 6 Hours):**
[49.8, 50.1, 50.4, 51.0, 50.7, 50.9]
