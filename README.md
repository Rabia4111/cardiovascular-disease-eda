# ?? Cardiovascular Disease EDA

This repository holds an exploratory data analysis (EDA) of cardiovascular health dataset. The idea is to examine associations of biometric and lifestyle variables with the risk of cardiovascular disease.

---

## ?? Dataset Overview

The data consists of anonymised information about more than 68,000 patients and it has the following characteristics:

| Feature       | Description                                     |
|---------------|-------------------------------------------------|
| `age`         | Age in days (converted to years)                |
| `gender`      | 1 = Female, 2 = Male                            |
| `height`      | Height in cm                                    |
| `weight`      | Weight in kg                                    |
| `ap_hi`       | Systolic blood pressure                         |
| `ap_lo`       | Diastolic blood pressure                        |
| `cholesterol` | 1 = normal, 2 = above normal, 3 = well above    |
| `gluc`        | Glucose level (same scale as cholesterol)       |
| `smoke`       | 1 = Smoker, 0 = Non-smoker                      |
| `alco`        | 1 = Consumes alcohol, 0 = Doesn’t               |
| `active`      | 1 = Physically active, 0 = Inactive             |
| `cardio`      | Target variable: 1 = Has cardiovascular disease |

---

## ?? Data Cleaning

- Dropped redundant columns: `id` and `Unnamed: 0`
- Converted `age` from days to `age_years`
- Removed unrealistic entries (outliers) based on:
  - Height: 100–250 cm
  - Weight: 30–200 kg
  - Systolic BP (`ap_hi`): 50–250 mmHg
  - Diastolic BP (`ap_lo`): 30–200 mmHg

---

## ?? Exploratory Data Analysis (EDA)

### 1. ?? **Univariate Analysis: Numerical Features**

Histograms and KDE curves of:
- **Height** and **Weight**: Right-skewed distributions
- **Systolic (ap_hi)** and **Diastolic (ap_lo) BP**: Multimodal due to recording practices
- **Age in years**: Majority between 45 and 60 years

### 2. ?? **Univariate Analysis: Categorical Features**

Plot counts of:
- `gender`, `cholesterol`, `gluc`, `smoke`, `alco`, `active`, `cardio`
- Class imbalance is minor in `cardio`, with ~55% showing cardiovascular disease

### 3. ?? **Bivariate Analysis: Numeric Features vs. Cardio**

Boxplots comparing:
- **Cardio (target)** against continuous variables:
  - Blood pressure (`ap_hi`, `ap_lo`)
  - Age, weight, height
- Findings:
  - Cardiovascular patients tend to have higher **age**, **weight**, and **blood pressure**

### 4. ?? **Correlation Matrix**

A heatmap of all variable relationships:
- Strongest correlation: `ap_hi` vs `ap_lo` (**+0.70**)
- Target `cardio` moderately correlated with:
  - `ap_hi`: **+0.43**
  - `age_years`: **+0.24**
  - `weight`: **+0.18**
  - `cholesterol`: **+0.22**

![Correlation Matrix](relative/path/to/your/correlation_heatmap.png)

---

## ?? Repository Structure

```bash
cardiovascular-disease-eda/
??? dataset/
?   ??? health_data.csv
??? cleaned_health_data.csv
??? Cardio_EDA.ipynb
??? README.md