# 📌 DSA210 Term Project: Does Gas Price Affect Public Transport Usage? 🚉⛽

## 📍 Introduction
With fluctuating gas prices, many people consider alternative transportation methods, including public transport. This project aims to analyze the relationship between **gasoline prices and public transport usage**, using real-world data from Istanbul.

## 🎯 Motivation
Understanding how fuel prices impact public transport demand can help:  
- **City planners** optimize transit systems.  
- **Economists** analyze mobility trends.  
- **Governments** make informed policy decisions about subsidies and pricing.  

## 📊 Data Sources
1. **Public Transport Usage Data:**  
   - **Source:** İBB Open Data Portal ([data.ibb.gov.tr](https://data.ibb.gov.tr/en/group/ulasim-hizmetleri))  
   - **Includes:** Daily passenger counts for metro, tram, bus, and ferry.  

2. **Gas Prices in Istanbul:**  
   - **Source:** GlobalPetrolPrices - Turkey Gasoline Prices  
   - **Website:** [https://www.globalpetrolprices.com/Turkey/gasoline_prices/](https://www.globalpetrolprices.com/Turkey/gasoline_prices/)  
   - **Includes:** Weekly gasoline price data for Turkey, available from March 2015 onward.  

## 🛠️ Methodology
1. **Data Collection & Cleaning**  
   - Scrape or download gas price trends and daily public transport usage.  
   - Handle missing values and align timestamps.  

2. **Exploratory Data Analysis (EDA)**  
   - Analyze gas price trends and transport ridership patterns.  
   - Identify seasonal variations and anomalies.  

3. **Statistical Correlation & Hypothesis Testing**  
   - Use Pearson/Spearman correlation tests to quantify relationships.  
   - Check if significant gas price changes result in transport ridership changes.  

4. **Data Visualization**  
   - Time series plots for gas prices vs. ridership.  
   - Heatmaps to visualize correlations.  

## 📌 Expected Findings
- Is there a **strong correlation** between fuel price increases and rising public transport usage?  
- How does **seasonality** (winter vs. summer) affect this trend?  
- Does the impact vary across **different transport modes** (metro, bus, ferry)?  

## 🚀 Future Work
- Expand analysis to **different cities** for broader generalization.  
- Predict future public transport demand based on fuel price fluctuations.  

---
