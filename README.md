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
![MCP Trend](https://github.com/Sriyank-s/Power-Price-prediction/blob/main/mcp_trend.png)  

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



**Figure 3:** Forecast comparison across ARIMA, SARIMA, and LSTM.  
![Forecast Comparison](results/forecast_comparison.png)  

---

## Economic Load Dispatch (ELD) Using Genetic Algorithm

### Problem
Allocate power among generators to meet demand while minimizing cost.  

### Approach
- **Chromosome:** Generator outputs.  
- **Fitness Function:** Inverse of total cost.  
- **Operators:** Selection, crossover, mutation.  

**Example Input:**  
- Demand = 1200 MW  
- Generator cost functions + capacity limits  

**Example Output:**  
Optimal Allocation: {GenA: 500 MW, GenB: 400 MW, GenC: 300 MW}
Minimum Cost: 25,630.50




**Figure 4:** GA convergence curve (cost minimized across generations).  
![GA Convergence](results/ga_convergence.png)  

---

## Price Tagging Framework
1. Forecast MCP using ARIMA/SARIMA/LSTM.  
2. Apply GA for generation cost optimization.  
3. Combine both outputs to assign **dynamic price tags**.  

**Sample Output (Next 6 Hours):**
[52.1, 52.4, 52.7, 53.0, 52.8, 53.2]


**Figure 5:** Dynamic price tagging using forecasted MCP and GA optimization.  
![Price Tagging](results/price_tagging.png)  

---

## Results

- **ARIMA:** R² ≈ 0.77, RMSE ≈ 4.3 (baseline).  
- **SARIMA:** R² ≈ 0.80, RMSE ≈ 3.8 (better seasonal fit).  
- **LSTM:** R² ≈ 0.88, RMSE ≈ 2.9 (best performance).  
- **GA Optimization:** Reduced generation costs compared to naive allocation.  

**Figure 6:** Model performance comparison (ARIMA vs SARIMA vs LSTM).  
![Model Performance](results/model_performance.png)  

---

## Insights and Conclusions

### Key Insights
- LSTM captured nonlinear and long-term price dynamics most effectively.  
- GA provided cost-efficient generator allocation.  
- Integration ensured price tags were both **market-aligned** and **economically optimal**.  

### Key Takeaways
- ARIMA/SARIMA = strong interpretable baselines.  
- LSTM = superior forecast accuracy in volatile markets.  
- GA = effective solution for nonlinear optimization.  
- Combined approach improves **market competitiveness**.  

---

## Project Structure
├── data/ # Historical MCP and demand datasets
├── notebooks/ # ARIMA, SARIMA, and LSTM experiments
├── models/ # Trained forecasting models
├── ga_code/ # GA implementation for ELD
├── results/ # Forecast plots, GA outputs, price tags
└── README.md # Project documentation



---

## Final Thoughts
This project demonstrates how **time series forecasting** and **Genetic Algorithms** can be combined to solve real-world problems in deregulated electricity markets.  

The hybrid framework:  
- Improves price forecasting accuracy.  
- Minimizes generation cost.  
- Produces **dynamic price tags** that adapt to market and demand conditions.  

This integration of predictive analytics and optimization supports smarter bidding, lower costs, and better decision-making in modern power systems.  

