# 📐 Technical Methodology

## 1. Data Simulation Engine (The Digital Twin)
Since the Mall of Zimbabwe is in the pre-construction phase (breaking ground 2026), historical data does not exist. We engineered a **Physics-Based Digital Twin** to simulate hourly energy demand based on:

* **Mall Specifications:** 90,000m² GLA (Gross Leasable Area).
* **Diurnal Cycles:** Cosine-wave temperature injection to simulate Harare's specific climate (hot afternoons, cool mornings).
* **Occupancy Modeling:** Stochastic foot traffic patterns (Weekend peaks vs. Weekday lulls).
* **Grid Instability:** A 6% probability injection of ZESA load shedding events, triggering diesel generator usage.

## 2. Machine Learning Strategy
We framed this as a **Time-Series Regression** problem.
* **Target Variable:** `total_energy_kwh`
* **Features:** Lag features (1h, 24h), Rolling Means (3h), Cyclical Time Encodings (Sin/Cos of Hour/Month), and Interaction Terms (Occupancy × Temp).

### Model Selection
We benchmarked three distinct architectures:
1.  **Prophet:** Failed to capture complex, non-linear grid failures.
2.  **SARIMA (Seasonal ARIMA):** Effective at capturing the weekly seasonality (Weekend vs. Weekday). However, it struggled with the random "shock" events caused by load shedding (generator switch-overs), leading to higher error rates during outages.
3.  **LSTM (Deep Learning):** High accuracy, but computationally expensive and slower to react to sharp "shocks" (power outages).
4.  **XGBoost:** Selected as the **Production Model**. It offered the best balance of speed and accuracy (MAPE: 2.07%) and handled tabular features (like "Is_Holiday") better than the neural network.

## 3. Financial Optimization Logic
* **Tariff Assumptions:** Commercial rate of $0.14/kWh (Blended Grid/Diesel cost).
* **Solar Yield:** Modeled on 4MW capacity @ 5.5 peak sun-hours/day (Harare average).
* **ROI Calculation:** CapEx / Annual Savings = Payback Period (Years).

## 4. Data Validity & Benchmarking
To ensure this simulation represents a realistic "Feasibility Level" study, the synthetic data was calibrated against rigorous industry standards:

* **Benchmark Alignment:** The model was tuned to achieve an Energy Intensity (EUI) of **~288 kWh/m²/year**, aligning with MSCI and Green Building Council benchmarks for regional shopping centers in Southern Africa.
* **Physics Compliance:** The simulation enforces thermodynamic constraints (e.g., HVAC load increases non-linearly with `temperature²`), ensuring the data behaves like a real physical asset.
* **Contextual Integrity:** Specific local variables, such as **Harare's specific cooling degree days** and **ZESA grid failure rates (6%)**, were injected to ensure the data is contextually accurate for Zimbabwe, rather than generic US/EU data.

**Conclusion:** While synthetic, this data serves as a **Class 4 Feasibility Estimate**, suitable for strategic decision-making and CapEx prioritization.

---
## 📬 Contact the Author
If you have questions about this simulation or want to discuss Smart City energy strategies:

* **Email:** stillhere4hunnid@gmail.com
* **LinkedIn:** www.linkedin.com/in/adonis-chiruka-70b265323
* **GitHub:** [https://github.com/stilhere4huniid](https://github.com/stilhere4huniid)

> *Open to Data Science & Strategic Analyst collaborations.*
