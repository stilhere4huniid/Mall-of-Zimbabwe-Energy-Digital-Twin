# 🇿🇼 Mall of Zimbabwe: Predictive Energy Digital Twin

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Model](https://img.shields.io/badge/AI-XGBoost-orange)

> **Strategic Feasibility Study:** Predicting the operational energy future of the 90,000m² Mall of Zimbabwe before construction begins in 2026.

## 🏙️ Executive Summary
WestProp Holdings is developing the Mall of Zimbabwe, a $100M+ "Smart City" asset in Harare. To secure anchor tenants and optimize Capital Expenditure (CapEx), we built a **Digital Twin** to simulate the mall's energy consumption, costs, and grid resilience.

**The Result:** We identified **$1.66 Million** in annual savings by integrating a 4MW Solar Microgrid and AI-driven HVAC controls into the pre-construction blueprints.

## 📊 Key Results
| Metric | Baseline (Standard Build) | Optimized (Smart Build) | Impact |
| :--- | :--- | :--- | :--- |
| **Annual Demand** | 26.6 GWh | 14.5 GWh | **-45%** |
| **Annual Bill** | $3.7 Million | $2.0 Million | **$1.66M Saved** |
| **Grid Reliance** | 94% (High Risk) | 60% (Resilient) | **Energy Security** |

## 🧠 The AI Model Showdown
We benchmarked three forecasting approaches to validate our financial projections.

* **🏆 XGBoost (Winner):** 97.9% Accuracy (MAPE: 2.07%). Handling ZESA load shedding patterns best.
* **❌ LSTM (Deep Learning):** 94.6% Accuracy. Slower to adapt to sudden grid outages.
* **❌ SARIMA (Statistical):** 88.2% Accuracy. Good for seasonality but failed to capture holiday-specific spikes.
* **❌ Prophet (Baseline):** 69.0% Accuracy. Failed to capture complex operational hours.

## 📂 Project Structure
├── Data/                   # Raw & Calibrated Simulation Data
├── Visualizations/         # EDA & Model Performance Charts
├── Deliverables/           # Client-Facing Reports
│   ├── Mall_of_Zimbabwe_Strategic_Brief.pdf  (Executive Memo)
│   └── strategic_energy_dashboard.html       (Interactive Dashboard)
└── Project_Notebook.ipynb  # Full Source Code

## ⚡ Quick Start
To reproduce the results or run the simulation on your local machine, follow these steps:

# 1. Clone the Repository

git clone [https://github.com/stilhere4huniid/Mall-of-Zimbabwe-Energy-Digital-Twin.git](https://github.com/stilhere4huniid/Mall-of-Zimbabwe-Energy-Digital-Twin.git)
cd Mall-of-Zimbabwe-Energy-Digital-Twin

# 2. Install Dependencies Ensure you have Python 3.8+ installed. Then install the required libraries:
pip install -r requirements.txt

# 3. Run the Simulation Launch the Jupyter Notebook to explore the code, re-train the models, and generate new forecasts:
jupyter notebook Project_Notebook.ipynb
> Note: The raw data is included in the Data/ folder, so the simulation will run immediately without external downloads.

## 🛠️ Tech Stack
Simulation: Python, NumPy (Physics-based diurnal cycles)

Machine Learning: XGBoost, TensorFlow (Keras), Scikit-Learn

Reporting: Plotly (Dashboards), FPDF (PDF Generation)

---
## ⚠️ Disclaimer & Tribute
This project is an independent **Data Science/Data Analytica Portfolio Simulation** created for educational purposes.

* **The Inspiration:** I am not affiliated with **WestProp Holdings**, but as a Zimbabwean Data Scientist/Data Analyst, I am incredibly excited about their vision for the **Mall of Zimbabwe**. With construction set to begin in **2026**, this project is my personal tribute to what promises to be a landmark development for Harare and the region.
* **The "Why":** I built this Digital Twin to showcase how modern AI can support ambitious infrastructure projects, simulating the "Smart City" potential of the mall before the first brick is laid.
* **Data Sources/Transparency:** The data used in this project is **100% synthetic**. It was generated using physics-based simulation algorithms (Python/NumPy) calibrated to industry standards for a 90,000m² regional shopping center. It does **not** contain actual proprietary data from WestProp or their partners.
