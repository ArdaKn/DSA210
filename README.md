# 📌 DSA210 Term Project: Does Gas Price Affect Public Transport Usage? 🚉⛽

## 📍 Introduction
With fluctuating fuel prices, many urban residents reconsider their mode of transportation, shifting between private vehicles and public transport. This project investigates the relationship between **gasoline prices** and **public transport usage** in **Istanbul**, one of the world's most traffic-dense megacities. The analysis aims to provide actionable insights for **city planners**, **economists**, and **policy-makers** to better understand mobility trends and optimize infrastructure decisions.

---

## 🎯 Motivation
Fuel costs are a fundamental factor in transportation decisions. As prices increase, the use of public transportation may rise as a cost-saving measure. This behavioral shift is not just anecdotal—numerous studies (e.g., Litman, 2022; OECD Transport Reports) suggest strong economic influences on modal choice.

However, most research is conducted on national or international levels. This project offers a **localized Istanbul-based analysis** to fill the research gap and support data-driven urban policy. For example, if strong correlations are found, the city could proactively adjust transit capacities in response to fuel price volatility.

---

## 🗂️ Data Sources

### 1. **Public Transport Usage Data**  
- **Source:** İBB Open Data Portal  
- **Link:** [https://data.ibb.gov.tr/en/group/ulasim-hizmetleri](https://data.ibb.gov.tr/en/group/ulasim-hizmetleri)  
- **Content:** Daily passenger counts for metro, tram, bus, and ferry lines in Istanbul

**Turkey Gasoline Price Data (2021)**  
- **Source:** Enerji Piyasası Düzenleme Kurumu (EPDK)  
- **Report:** “Petrol ve LPG Piyasası Fiyatlandırma Raporu – Aralık 2021”  
- **Link:** https://www.epdk.gov.tr  
- **Accessed On:** April 25, 2025  
- **Details:** Monthly average fuel prices for 95-octane gasoline were extracted from official retail pricing breakdowns.  

### 📏 Granularity & Preprocessing
- Public transport data: **daily** resampled to **weekly**
- Gas prices: **weekly**
- Missing values removed, timestamps aligned

---

## 🛠️ Methodology

### 📥 1. Data Collection & Cleaning
- Downloaded datasets from verified public sources
- Removed null entries, filtered to overlapping date ranges
- Resampled and aligned time indices across both datasets

### 📊 2. Exploratory Data Analysis (EDA)
- Line plots to visualize long-term trends in fuel prices and ridership
- Seasonal decomposition to inspect monthly/yearly patterns
- Heatmaps for correlation between variables
- Summary statistics to detect anomalies and variability

### 🧪 3. Hypothesis Testing
- **Null Hypothesis (H₀):** No significant relationship between gasoline price fluctuations and public transport usage  
- **Alternative Hypothesis (Hₐ):** Gasoline price increases lead to higher public transport usage

Applied:
- Pearson Correlation Coefficient (linear)
- Spearman Rank Correlation (monotonic)

### 🖼️ 4. Data Visualization
- Time series plot: Gasoline prices vs. ridership over time
- Correlation heatmaps
- Scatter plots: Price vs. ridership by mode

---

## 🔍 Preliminary Findings (As of April 18)
- Pearson Correlation (gas price vs. total ridership): **r = +0.42**
- Stronger correlation observed during winter months (potential seasonal effect)
- Ferry and metro usage seem more sensitive to fuel price increases than buses
- Significant ridership dips during national holidays and lockdown periods identified as outliers

---

## 📌 Limitations
- Weekly price data had to be interpolated to daily — may introduce minor noise
- Potential confounders (e.g., weather, policy changes) not controlled yet
- The causality direction cannot be confirmed without further modeling

---

## 🚀 Future Work
- Apply **ARIMA** and/or **linear regression with lag features** to model temporal dependencies
- Extend analysis to **other Turkish cities** (e.g., Ankara, İzmir) for cross-city comparison
- Predict future demand using **machine learning models** (e.g., Random Forest Regressor)
- Incorporate additional variables like **weather** or **economic indices** to improve model quality

---

