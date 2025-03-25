

# **PowerCo Customer Data Analysis - Jupyter Notebook**

## **Introduction**

Welcome to the PowerCo Customer Data Analysis notebook! This notebook aims to analyze and gain insights from customer and pricing data provided by PowerCo, a gas and electricity utility company. The analysis will focus on understanding key features of the dataset, identifying patterns, and investigating factors influencing customer churn. 

By the end of this analysis, the goal is to build an understanding of how different features (e.g., consumption, pricing, contract terms) relate to customer behavior and churn, helping PowerCo improve customer retention strategies.

This project is structured as follows:
1. **Data Overview**: An introduction to the provided datasets and their key features.
2. **Data Preprocessing**: Steps to prepare and clean the data for analysis.
3. **Exploratory Data Analysis (EDA)**: Descriptive statistics, visualizations, and insights into the data.
4. **Churn Analysis**: Investigating factors that influence customer churn.
5. **Next Steps**: Recommendations based on the analysis.

---

## **1. Data Overview**

PowerCo has shared three key datasets for analysis:

### **Client Data (`client_data.csv`)**
This dataset contains detailed information about PowerCo's customers, including:
- **Usage Data**: Electricity and gas consumption data (both historical and forecasted).
- **Contract Details**: Information regarding contract activation, end dates, and renewals.
- **Pricing**: Forecasted energy and power pricing for peak, off-peak, and mid-peak periods.
- **Margins**: Gross and net margins associated with electricity and power subscriptions.
- **Customer Behavior**: Whether the customer has churned over the next 3 months.

Key columns include:
- **id**: Unique identifier for each client.
- **cons_12m**: Total electricity consumption for the past 12 months.
- **forecast_cons_12m**: Forecasted electricity consumption for the next 12 months.
- **churn**: Indicator of whether the customer has churned (1) or not (0).
- **margin_gross_pow_ele**: Gross margin from electricity subscriptions.
- **date_activ**, **date_end**: Dates indicating when the contract was activated and ended.

### **Pricing Data (`price_data.csv`)**
This dataset provides pricing information for energy and power, split into off-peak, peak, and mid-peak periods. The dataset includes:
- **id**: Unique identifier for each client.
- **price_date**: The reference date of the pricing.
- **price_off_peak_var**, **price_peak_var**, **price_mid_peak_var**: Variable prices for energy during different periods.
- **price_off_peak_fix**, **price_peak_fix**, **price_mid_peak_fix**: Fixed prices for power during different periods.

### **Data Description Document (`Data Description.pdf`)**
This document provides detailed explanations for each column in both datasets. It will be an essential reference throughout the analysis to understand the context of the data, especially for hashed or anonymized columns.

---

## **2. Data Preprocessing**

Before diving into the analysis, we need to perform some preprocessing steps:
1. **Loading the Data**: We will load both `client_data.csv` and `price_data.csv` into Pandas DataFrames.
2. **Inspecting Data Types**: We'll check the data types of each column to ensure they are appropriate for analysis. Some columns might need conversion (e.g., date columns).
3. **Handling Missing Data**: We’ll identify any missing values in the dataset and decide how to handle them (e.g., by filling them with appropriate values or dropping rows/columns).
4. **Date Processing**: Date columns like `date_activ`, `date_end`, and `date_modif_prod` will be converted into Python `datetime` objects for easier manipulation.
5. **Data Normalization**: Some numeric columns might need to be normalized or standardized, especially if used for modeling later.

---

## **3. Exploratory Data Analysis (EDA)**

EDA will help us understand the distribution and relationship of different variables within the datasets.

- **Basic Descriptive Statistics**: We'll generate summary statistics like mean, median, standard deviation, min, max, etc., for numeric columns.
- **Missing Value Check**: We'll look for any missing or anomalous data and handle it accordingly.
- **Visualizations**:
  - **Histograms**: To visualize the distribution of continuous features (e.g., electricity consumption, margins).
  - **Boxplots**: To detect outliers and understand the spread of data for key features.
  - **Correlation Matrix**: To see how numerical features relate to each other, especially with regard to churn.
- **Churn Analysis**: We’ll focus on the `churn` column to identify any patterns or factors that may contribute to customer churn. For example, we will explore whether customers with higher consumption or specific pricing plans are more likely to churn.

---

## **4. Churn Analysis**

The churn column indicates whether the customer has churned. Our objective here is to:
1. **Analyze the Relationship Between Churn and Other Features**:
   - Does higher consumption (electricity or gas) correlate with a higher likelihood of churn?
   - Are customers with specific pricing plans (e.g., high peak pricing) more likely to churn?
   - Does customer tenure (based on `num_years_antig`) have an impact on churn?
2. **Visualize Churn Patterns**:
   - We will create visualizations that compare churn across different features (e.g., a bar chart showing churn rates by `activity_new` or `channel_sales`).

---

## **5. Next Steps**

After completing the exploratory analysis, the next steps could involve:
1. **Predictive Modeling**: We may build a predictive model (e.g., logistic regression, decision trees) to predict customer churn based on the features.
2. **Pricing Strategy Recommendations**: Based on the analysis, we can provide recommendations for PowerCo on how to adjust pricing to reduce churn, focusing on customers most sensitive to pricing changes.
3. **Further Data Collection**: We may explore the potential for acquiring more granular data (e.g., customer service interactions, complaint data) to improve our models.

---

## **Conclusion**

This notebook serves as the initial step in understanding and analyzing the PowerCo customer and pricing data. By conducting thorough exploratory data analysis, we will uncover insights that will inform recommendations for improving customer retention and optimizing pricing strategies. As a Junior Data Scientist at BCG, this analysis will help you develop essential data science skills, including data cleaning, analysis, visualization, and communicating findings.

