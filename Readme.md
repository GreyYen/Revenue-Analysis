# Revenue Analysis, Modeling and Forecasting of IT Companies

## Overview

This project focuses on analyzing, modeling, and forecasting the **quarterly revenue** of major IT companies using historical financial data. The workflow includes data collection from financial reports, exploratory data analysis (EDA), feature engineering, and predictive modeling using linear regression.

The goal is to **estimate future revenue trends** and **generate a structured report** comparing actual and predicted values.

## Dataset Description

The dataset consists of quarterly financial data for the following IT companies:

* Accenture
* Cognizant
* HCLTech
* Infosys
* TCS
* Tech Mahindra
* Wipro

### Data Sources

Data has been manually collected from **official quarterly financial reports** of each company.

### Combined Dataset

All company data is consolidated into:

    data/companies_revenue_data.csv

### Key Features

* `report_id`: Unique identifier (company + fiscal year + quarter)
* `company`: Company name
* `category`: Company classification/group
* `fiscal_year`: Financial year
* `quarter`: Fiscal quarter
* `revenue`: Quarterly revenue
* `target_revenue`: Next quarter revenue (prediction target)
* `op_margin`: Operating margin
* `headcount`: Number of employees

### Additional engineered features:
Lag features (previous quarter revenue)
Growth metrics (QoQ, YoY)


## Project Structure

```
Revenue Analysis/
│
├── companies/
│   ├── accenture.csv
│   ├── cognizant.csv
│   ├── hcltech.csv
│   ├── infosys.csv
│   ├── tcs.csv
│   ├── techmahindra.csv
│   └── wipro.csv
│
├── data/
│   ├── categories.json
│   └── companies_revenue_data.csv
│
├── Inference Plots.ipynb
├── Model Evaluation.ipynb
├── Model Training.ipynb
├── report.csv
└── .gitignore
```

## Exploratory Data Analysis (EDA)

EDA was performed to understand trends, patterns, and relationships in the data.

### Key Analysis Performed:

* Revenue trends across companies and quarters
* Comparison of operating margins
* Headcount vs revenue relationship
* Growth trend visualization (QoQ and YoY)
* Distribution analysis of revenue and margins

### Insights:

* Strong correlation between headcount and revenue for service-based firms
* Seasonal and cyclical patterns in quarterly revenue
* Variation in growth rates across company categories

## Feature Engineering

To improve model performance, several features were engineered:

* Lag Features
    - Previous quarter revenue (`lag_1`)
    - Previous year same quarter revenue (`lag_4`)

* Growth Features
    - Quarter-over-Quarter Growth (`QoQ`)
    - Year-over-Year Growth (`YoY`)

* Derived Features
    - Revenue trends
    - Revenue ranges
    - Category-based segmentation

## Forecasting and Report Generation

Predictions are stored in:

    report.csv

Report Includes:
* Company name
* Fiscal year & quarter
* Predicted revenue
* Revenue range (confidence interval)
* QoQ growth
* YoY growth

This report serves as a forecasting output for business insights and decision-making.

## Inference and Visualization

    Inference Plots.ipynb

Includes:

* Predicted vs actual revenue plots
* Trend visualization
* Company-wise forecasting comparison

## Conclusion

This project demonstrates an end-to-end pipeline for financial data analysis and forecasting. It combines domain understanding, feature engineering, and machine learning to generate actionable insights for revenue prediction.