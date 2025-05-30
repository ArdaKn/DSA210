# DSA210 Term Project: Does Gas Price Affect Public Transport Usage?

---

## 1. Introduction

With fluctuating fuel prices, many urban residents reconsider their mode of transportation, shifting between private vehicles and public transport. This project investigates the relationship between **gasoline prices** and **public transport usage** in **Istanbul**, one of the world's most traffic-dense megacities.

The analysis aims to provide actionable insights for **city planners**, **economists**, and **policy-makers** to better understand mobility trends and optimize infrastructure decisions.

---

## 2. Motivation

Fuel costs are a fundamental factor in transportation decisions. As prices increase, the use of public transportation may rise as a cost-saving measure. This behavioral shift is not just anecdotal—numerous studies (e.g., Litman, 2022; OECD Transport Reports) suggest strong economic influences on modal choice.

However, most research is conducted on national or international levels. This project offers a **localized Istanbul-based analysis** to fill the research gap and support data-driven urban policy. For example, if strong correlations are found, the city could proactively adjust transit capacities in response to fuel price volatility.

---

## 3. Data Sources

### 1. **Public Transport Usage Data**  
- **Source:** İBB Open Data Portal  
- **Link:** [İBB Public Transport Usage Dataset](https://data.ibb.gov.tr/dataset/ibb-toplu-tasima-donemsel-yolculuk-sayilari)  
- **Content:** Daily passenger counts for metro, tram, bus, and ferry lines in Istanbul

### 2. **Turkey Gasoline Price Data (2021)**  
- **Source:** Enerji Piyasası Düzenleme Kurumu (EPDK)  
- **Report:** “Petrol ve LPG Piyasası Fiyatlandırma Raporu – Aralık 2021”  
- **Link:** [EPDK Fuel Price Reports](https://www.epdk.gov.tr/Detay/Icerik/3-100/petrol)  
- **Accessed On:** April 25, 2025  
- **Details:** Monthly average fuel prices for 95-octane gasoline were extracted from official retail pricing breakdowns.

### 3. **Weather Data (2022)**  
- **Source:** Visual Crossing  
- **Link:** [Visual Crossing Weather History – Istanbul](https://www.visualcrossing.com/weather-history/İstanbul)  
- **Content:** Monthly average temperature and total precipitation

---

## 4. Data Preprocessing and Enrichment

- Public transport data was aggregated from **daily** counts into **monthly** total passenger counts.
- **Per capita ridership** was calculated by dividing monthly total passengers by Istanbul's estimated population for 2022 (~15,840,900).
- Gasoline price data was enriched by calculating the **monthly percent change** to capture sensitivity to price increases.

---

## 5. Exploratory Data Analysis (EDA)

- Line plots to visualize long-term trends in fuel prices and ridership
- Correlation matrix heatmaps
- Scatter plots for direct visual relationship analysis

---

## 6. Additional Variable: Weather Impact

### Why Include Weather?

Weather conditions can significantly affect daily transport behavior. For instance:
- **Hot or extremely cold months** may reduce walking and encourage public transport use.
- **Heavy rainfall** increases reliance on covered or underground transit (e.g., metro, tram), reducing bike or pedestrian activity.
- Urban planners often use **weather-based demand forecasting** to optimize operations and scheduling.

By enriching the dataset with **monthly average temperature** and **total precipitation**, this project explores whether **climatic factors influence ridership trends**, independently or in conjunction with fuel price fluctuations.

### Weather Data Integration

- The dataset was merged using the `"month"` column as a key across all sources (gasoline prices, ridership, and weather).
- Two new variables were introduced:
  - `avg_temp` — Monthly average temperature (°C)
  - `total_precip` — Monthly total precipitation (mm)
- Correlations were computed between ridership and weather variables to understand behavioral effects.

### Preliminary Weather Insights

| Variable         | Correlation with Ridership | Interpretation                                 |
|------------------|----------------------------|-------------------------------------------------|
| Average Temp     | Negative                   | Warmer months showed slightly lower ridership   |
| Total Precip     | Positive                   | Rainy months increased public transport use     |

These insights suggest weather plays a **secondary but noteworthy role** in shaping transportation behavior. Including weather data enhances the model's realism and opens new directions for multivariable forecasting.

---

## 7. Hypothesis Testing

- **Null Hypothesis (H₀):** No significant relationship between gasoline price fluctuations and public transport usage.  
- **Alternative Hypothesis (Hₐ):** Gasoline price increases lead to higher public transport usage.

Tests Applied:
- **Pearson Correlation Coefficient** for linear relationships
- **Spearman Rank Correlation** for monotonic relationships

### Hypothesis Testing Results

- **Pearson correlation coefficient:** `r = 0.617`, **p-value = 0.0327**  
- **Spearman correlation coefficient:** `r = 0.573`, **p-value = 0.0513**

**Interpretation:**
- For Pearson correlation, at a 5% significance level, we **reject the null hypothesis**: there is a significant positive linear relationship between gasoline prices and public transport usage.
- For Spearman correlation, the p-value slightly exceeds 0.05, suggesting weaker but still notable evidence for a monotonic relationship.

---

## 8. Machine Learning Model Results

To quantify the predictive power of external factors, a **linear regression model** was trained using:

- **Gas Price (TRY)**
- **Average Temperature (°C)**
- **Total Precipitation (mm)**

as independent variables to predict **per capita ridership**.

The model achieved an **R² score of 0.628**, indicating that approximately **63% of the variation in public transport ridership** can be explained by these three features.

- The **gas price coefficient was positive** (`+0.234`), supporting the hypothesis that higher fuel prices lead to increased public transport usage.
- **Temperature** (`-0.019`) and **precipitation** (`-0.243`) both showed small to moderate **negative effects**, potentially reflecting reduced ridership during hotter or rainier months.

Although the dataset size was limited to 12 monthly observations, the results provide a promising foundation for future multivariate modeling and time-series forecasting using a broader dataset.

---

## 9. Findings

- Positive relationship between fuel price increases and public transportation ridership rates.
- **Metro** and **ferry** modes showed stronger responsiveness compared to buses.
- National holidays and COVID-19 lockdowns created visible anomalies (sharp dips).

---

## 10. AI Usage Disclosure

Limited AI assistance (ChatGPT 4.0) was used to refine sentence clarity and formatting in this README. No code, data analysis, or results were generated by AI. All analysis, modeling, and interpretation were completed independently by the student.
---

