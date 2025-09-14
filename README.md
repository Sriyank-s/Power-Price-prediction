Predictive Model Based Power Price Tagging Under Deregulated Environment
Introduction

In deregulated power markets, electricity prices fluctuate significantly due to dynamic supply and demand. Anticipating the Market Clearing Price (MCP) is crucial for efficient bidding, cost management, and reliable power distribution.

This project presents an individual implementation that combines time series forecasting and Genetic Algorithm (GA) optimization to:

Predict short-term electricity prices (MCP).

Optimize Economic Load Dispatch (ELD) to minimize generation costs.

Integrate forecasting and optimization to generate dynamic price tags.

The goal is to design a hybrid approach that not only predicts future prices but also ensures economic efficiency in generation planning.

Core Components
1. Time Series Forecasting

ARIMA Model: Baseline method capturing linear dependencies in MCP.

SARIMA Model: Extended ARIMA with seasonal components.

LSTM Neural Network: Deep learning approach to capture nonlinearities and long-term patterns.

Example Input:
Historical hourly MCP values for 30 days.

Example Output (Next 6 Hours Forecast):

[49.8, 50.1, 50.4, 51.0, 50.7, 50.9]


Sample Visualization:


2. Economic Load Dispatch Using Genetic Algorithm

Formulated the ELD problem to allocate generation among units while minimizing cost.

GA applied to evolve candidate solutions with selection, crossover, and mutation.

Outputs an optimal allocation schedule and the associated minimum cost.

Example Input:

Demand: 1200 MW

Generator cost functions and capacity constraints

Example Output:

Optimal Allocation: {GenA: 500 MW, GenB: 400 MW, GenC: 300 MW}
Minimum Cost: 25,630.50


Sample Visualization:


3. Price Tagging Framework

Combines MCP forecasts with optimized generation costs.

Produces dynamic electricity price tags for each time slot.

Ensures tagged prices reflect both market dynamics and economic efficiency.

Sample Output (Next 6 Hours Price Tags):

[52.1, 52.4, 52.7, 53.0, 52.8, 53.2]

Technologies Used

Python (forecasting + GA implementation)

MATLAB (alternative GA validation)

Libraries:

pandas, numpy – Data handling

statsmodels, pmdarima – ARIMA/SARIMA

tensorflow/keras – LSTM

Custom GA code – ELD optimization

matplotlib, seaborn – Visualization

Results

ARIMA: R² ≈ 0.77 (baseline).

SARIMA: Improved accuracy by modeling seasonality.

LSTM: Best performance, capturing nonlinear patterns.

Genetic Algorithm: Reduced generation cost significantly with optimized allocation.

Combined Framework: Provided robust and adaptive price tagging, supporting more effective bidding in deregulated markets.

Sample Visualization (All Models):


Project Structure
├── data/                 # Datasets (MCP, demand, generator cost curves)
├── notebooks/            # ARIMA, SARIMA, and LSTM experiments
├── models/               # Saved trained models
├── ga_code/              # Genetic Algorithm implementation
├── results/              # Forecast plots, GA outputs, price tags
└── README.md             # Project documentation

Conclusion

This project demonstrates how time series forecasting combined with Genetic Algorithm optimization can effectively tackle challenges in deregulated electricity markets.

Forecasting enables accurate price anticipation.

GA ensures generation is cost-efficient.

Integration delivers dynamic price tags aligned with both market and economic realities.

This hybrid framework enhances competitiveness, reduces costs, and improves market decisions for electricity producers and consumers.
