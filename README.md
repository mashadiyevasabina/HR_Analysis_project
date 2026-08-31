# Employee Attrition & Retention Data Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/19J8xOLWsp99pwCMj9JToe0mijZ7bbH2X)

## Project Overview
This project investigates employee turnover (`Attrition`) using data analytics and quantitative methods. The goal is to identify key drivers behind employee departure, evaluate the relationship between work conditions, career growth, and employee satisfaction, and deliver actionable insights for HR management to improve retention strategies.

---

## Key Performance Indicators (KPIs)
* **Compensation & Financials:** `Monthly Income`, `Hourly Rate`
* **Employee Satisfaction:** `Job Satisfaction`, `Work-Life Balance`, `Work Environment Satisfaction`
* **Workload & Attendance:** `Project Count`, `Average Hours Worked Per Week`, `Absenteeism`
* **Career Development & Tenure:** `Years at Company`, `Years in Current Role`, `Years Since Last Promotion`
* **Statistical Testing:** `Chi-Square Test` (Department vs. Attrition), `Correlation Matrix`

---

## Data Overview & Exploratory Data Analysis
The dataset contains employee demographic, performance, and organizational data. Below is a summary of key metrics across the dataset:

| Feature Category | Feature Name | Description | Data Type |
| :--- | :--- | :--- | :--- |
| **Target Variable** | `attrition` | Employee churn status (True/False or Yes/No) | Categorical / Boolean |
| **Demographics & Role**| `age`, `department`, `job_level` | Basic employee attributes and hierarchy | Numerical / Categorical |
| **Compensation** | `monthly_income`, `hourly_rate` | Earnings and compensation metrics | Numerical |
| **Tenure** | `years_at_company`, `years_in_current_role` | Length of service and role duration | Numerical |
| **Satisfaction** | `job_satisfaction`, `work_life_balance` | Rating scales (1–5) measuring satisfaction | Numerical / Ordinal |

---

## Data Preprocessing & Cleaning
To ensure data integrity prior to statistical analysis, the following cleaning steps were executed in Python:

* **Type Casting & Encoding:** Converted categorical target values (`Yes`/`No` or `True`/`False`) into binary numeric format ($1$ and $0$) to allow correlation calculations.
* **Missing Value Handling:** Verified complete cases across numerical feature columns (`monthly_income`, `years_at_company`, `job_satisfaction`).
* **Feature Selection:** Separated categorical variables for non-parametric tests (e.g., `department`) from continuous metrics for parametric/correlation analysis.

---

## Key Exploratory Analyses & Findings



**1. Career Tenure & Promotion Metrics**
* **Years at Company:** Departing employees average **14.98 years** compared to **14.92 years** for retained staff.
* **Years in Current Role:** Departing employees average **7.49 years** versus **7.44 years** for retained staff.
* **Years Since Last Promotion:** Average time since last promotion is virtually identical between groups (**~4.46 years**).
* *Insight:* Extended duration in the same role without progression acts as a subtle contributor to career stagnation and potential attrition.

**2. Statistical Hypothesis Testing (Department vs. Attrition)**
* **Chi-Square Test of Independence:**
  * $\chi^2 \text{ Statistic} = 1.9323$
  * $p\text{-value} = 0.7482$
* *Insight:* Since $p \ge 0.05$, there is no statistically significant association between an employee's department and their likelihood of leaving the company.

**3. Correlation Matrix & Feature Interdependence**
* Linear correlation coefficients ($r$) between continuous features and `attrition` range between **-0.01 and 0.02**.
* *Insight:* No single metric linearly drives turnover in isolation; attrition is influenced by a combination of soft factors (workload, balance, and culture).

---
<img width="1015" height="521" alt="Screenshot 2026-08-31 171744" src="https://github.com/user-attachments/assets/626e8e1a-0870-4716-8d00-0a9e63a37814" />



## Business Recommendations
1. **Career Mobility & Internal Rotation:** Implement structured career paths and internal rotation programs for employees spent $7+$ years in the same role to prevent career stagnation.
2. **Work-Life Balance Initiatives:** Offer flexible working options and remote/hybrid arrangements to address burnout among employees reporting moderate balance scores.
3. **Targeted Workplace Culture Improvements:** Enhance team dynamics and manager-employee feedback loops to improve overall environment satisfaction.
4. **Qualitative Exit Interviews:** Implement structured, anonymous exit surveys to uncover qualitative nuances not fully captured by raw numerical metrics.
5. **Talent Retention Plans:** Develop Individual Development Plans (IDPs) for key talent to maintain high engagement and long-term organizational loyalty.

---

## Tech Stack & Tools
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Seaborn, Matplotlib
* **Statistical Analysis:** SciPy (`scipy.stats.chi2_contingency`)
