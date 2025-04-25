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

### 2. **Turkey Gasoline Price Data (2021)**  
- **Source:** Enerji Piyasası Düzenleme Kurumu (EPDK)  
- **Report:** “Petrol ve LPG Piyasası Fiyatlandırma Raporu – Aralık 2021”  
- **Link:** [https://www.epdk.gov.tr](https://www.epdk.gov.tr)  
- **Accessed On:** April 25, 2025  
- **Details:** Monthly average fuel prices for 95-octane gasoline were extracted from official retail pricing breakdowns.  

---

## 📏 Data Preprocessing and Enrichment
- Public transport data was aggregated from **daily** counts into **monthly** total passenger counts.
- **Per capita ridership** was calculated by dividing monthly total passengers by Istanbul's estimated population for 2022 (~15,840,900).
- Gasoline price data was enriched by calculating the **monthly percent change** to capture sensitivity to price increases.

---

## 🛠️ Methodology

### 📥 1. Data Collection & Cleaning
- Downloaded datasets from verified public sources
- Removed null entries, filtered to overlapping date ranges
- Resampled and aligned time indices across both datasets

### 📊 2. Exploratory Data Analysis (EDA)
- Line plots to visualize long-term trends in fuel prices and ridership
- Correlation matrix heatmaps
- Scatter plots for direct visual relationship analysis

### 🧪 3. Hypothesis Testing
- **Null Hypothesis (H₀):** No significant relationship between gasoline price fluctuations and public transport usage.  
- **Alternative Hypothesis (Hₐ):** Gasoline price increases lead to higher public transport usage.

Applied:
- **Pearson Correlation Coefficient** for linear relationships
- **Spearman Rank Correlation** for monotonic relationships
  
---

## 🧪 Hypothesis Testing Results

- **Pearson correlation coefficient:** `r = 0.617`, **p-value = 0.0327`
- **Spearman correlation coefficient:** `r = 0.573`, **p-value = 0.0513`

**Interpretation:**
- For Pearson correlation, at a 5% significance level, we **reject the null hypothesis**: there is a significant positive linear relationship between gasoline prices and public transport usage.
- For Spearman correlation, the p-value slightly exceeds 0.05, suggesting weaker but still notable evidence for a monotonic relationship.

---

## 🔍 Findings
- Positive relationship between fuel price increases and public transportation ridership rates.
- **Metro** and **ferry** modes showed stronger responsiveness compared to buses.
- National holidays and COVID-19 lockdowns created visible anomalies (sharp dips).

---

## 📌 Limitations
- Weekly gasoline price data had to be resampled and aligned to monthly, possibly introducing minor noise.
---

## 🚀 Future Work
- Apply **ARIMA models** and/or **linear regression with lag features** to predict future public transport demand.
- Expand to cross-city analysis including **Ankara** and **Izmir**.
- Include external variables like **weather conditions**, **unemployment rates**, or **inflation indices** to build multivariable predictive models.
---
