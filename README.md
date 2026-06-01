# 🛢️ Sprint 12 Project — OilyGiant Oil Well Development Analysis (Linear Regression & Bootstrapping)

---

## 🧠 Project Overview

In this project, I worked as a Data Scientist for **OilyGiant**, an oil extraction company seeking to identify the most profitable region for developing **200 new oil wells**.

Using geological exploration data from three different regions, the objective was to build predictive models capable of estimating oil reserves in new wells and determining which region would generate the highest expected profit while maintaining an acceptable level of financial risk.

Following project requirements, **Linear Regression** was the only machine learning algorithm used for prediction. Profitability and risk assessments were performed using **Bootstrap simulation techniques**.

---

## 🎯 Project Objectives

* Load and prepare geological exploration data from three regions.
* Train and evaluate a Linear Regression model for each region.
* Predict oil reserve volumes for new wells.
* Identify the top 200 wells with the highest predicted reserves.
* Calculate expected profits for each region.
* Estimate financial risks using bootstrapping.
* Select the region with:

  * The highest average profit.
  * A risk of loss below 2.5%.

---

## 📁 Dataset Description

Three datasets were provided:

* `geo_data_0.csv`
* `geo_data_1.csv`
* `geo_data_2.csv`

Each dataset contains geological information from a different region.

### Features

| Column  | Description                            |
| ------- | -------------------------------------- |
| id      | Unique oil well identifier             |
| f0      | Geological feature                     |
| f1      | Geological feature                     |
| f2      | Geological feature                     |
| product | Oil reserves volume (thousand barrels) |

### Target Variable

| Column  | Description                            |
| ------- | -------------------------------------- |
| product | Oil reserves volume (thousand barrels) |

---

## 🧩 Project Workflow

### Step 1 — Data Preparation

* Loaded the three regional datasets.
* Checked data structure and quality.
* Verified missing values and duplicates.
* Prepared features and target variables.
* Ensured data consistency across regions.

---

### Step 2 — Model Training and Validation

For each region:

* Split data into:

  * 75% Training Set
  * 25% Validation Set

* Trained a **Linear Regression** model.

* Generated predictions for the validation dataset.

* Calculated:

  * Mean predicted reserves
  * Root Mean Squared Error (RMSE)

* Compared predictive performance across regions.

---

### Step 3 — Business Analysis

Project assumptions:

| Parameter                    | Value        |
| ---------------------------- | ------------ |
| Wells evaluated              | 500          |
| Wells selected               | 200          |
| Development budget           | $100,000,000 |
| Revenue per barrel           | $4.50        |
| Revenue per thousand barrels | $4,500       |

To avoid losses:

* Each selected well must produce approximately **111.1 thousand barrels** on average.

The average reserve volume in each region was compared against this break-even threshold.

---

### Step 4 — Profit Calculation

A profit calculation function was developed to:

1. Select the 200 wells with the highest predicted reserves.
2. Calculate total oil production.
3. Estimate total revenue.
4. Subtract development costs.
5. Compute expected profit.

Profitability was evaluated independently for all three regions.

---

### Step 5 — Risk Assessment Using Bootstrapping

To evaluate uncertainty and financial risk:

* Applied Bootstrap sampling.
* Generated 1,000 bootstrap samples per region.
* Calculated profit distributions.
* Estimated:

  * Average profit
  * 95% Confidence Interval
  * Probability of losses

---

### Step 6 — Region Selection

Regions were compared using:

* Expected profit
* Confidence interval
* Risk of loss

Selection criteria:

✅ Risk of loss below 2.5%

✅ Highest average profit among qualifying regions

The final recommendation was based on balancing profitability and financial risk.

---

## 📊 Evaluation Metrics

### RMSE (Root Mean Squared Error)

Used to measure prediction accuracy of the Linear Regression model.

Lower RMSE values indicate more accurate reserve volume predictions.

### Average Profit

Measures expected profitability for the selected wells.

### Risk of Loss

Calculated as:

```python
Probability(Profit < 0)
```

Only regions with a risk below 2.5% were considered viable.

### 95% Confidence Interval

Provides a range of expected profits based on bootstrap simulations.

---

## 💡 Business Insights

This project demonstrates how predictive modeling can support high-investment decisions in the energy sector.

Key benefits include:

* Reducing exploration risk.
* Improving capital allocation.
* Identifying the most profitable drilling locations.
* Quantifying uncertainty before committing investment.

The combination of machine learning predictions and bootstrapping allows decision-makers to evaluate both expected returns and downside risk.

---

## 🧰 Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Linear Regression
* Bootstrap Sampling
* Jupyter Notebook

---

## 📚 Machine Learning Concepts Applied

* Supervised Learning
* Regression Analysis
* Linear Regression
* Train/Test Split
* Model Evaluation
* RMSE Analysis
* Business Case Modeling
* Bootstrap Resampling
* Confidence Intervals
* Risk Assessment

---

## 👤 Author

**Jonathan Peña**
