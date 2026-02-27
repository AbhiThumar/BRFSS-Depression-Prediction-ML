# BRFSS Depression Prediction & Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![PySpark](https://img.shields.io/badge/PySpark-3.5+-orange.svg)
![Tableau](https://img.shields.io/badge/Tableau-Public-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📋 Project Overview

This project develops a complete machine learning pipeline for depression prediction using the CDC BRFSS (Behavioral Risk Factor Surveillance System) dataset, combined with interactive Tableau dashboards for stakeholder engagement. Four classification models were evaluated, achieving >86.5% accuracy with ensemble methods.

**Key Achievements:**
- ✅ Processed **2.99M+** survey records
- ✅ Filtered **33,833** depression-related records
- ✅ Achieved **86.95% accuracy** with Random Forest
- ✅ Created **4 interactive Tableau dashboards**
- ✅ Identified critical risk groups for targeted intervention

---

## 📊 Dataset

- **Source:** CDC BRFSS (Behavioral Risk Factor Surveillance System)
- **Years:** 2011-2024
- **Total Records:** 2,996,473
- **Depression Records:** 33,833
- **Features:** Demographic categories, groups, sample sizes, prevalence rates
- **Target:** Depression status (Yes/No)

---

## 🧠 Models Implemented

| Model | Accuracy | Training Time | Key Strength |
|-------|----------|---------------|--------------|
| **Random Forest** | **86.95%** | 15.1s | 🏆 Best overall accuracy |
| **GBT** | 86.74% | 68.0s | Strong alternative |
| **Decision Tree** | 86.55% | **2.3s** | ⚡ Fastest, interpretable |
| **Logistic Regression** | 74.01% | 3.1s | Baseline comparison |

### Feature Importance (Average Across Models):
- **sample_size:** 49% (Dominant predictor)
- **category_idx:** 30% (Demographic category)
- **group_idx:** 21% (Specific demographic group)

---

## 📈 Key Findings

### Risk Stratification by Demographics:

| Risk Level | Prevalence | Groups |
|------------|------------|--------|
| 🔴 **Critical** | >28% | Female (28.9%), 18-24 (28.5%), 25-34 (28.7%) |
| 🟠 **High** | 24-28% | Black (24.5%), Other races (25.2%) |
| 🟡 **Moderate** | 20-24% | Hispanic (23.6%), White (21.8%) |
| 🟢 **Low** | <20% | 45-54, 55-64, 65+ |

### Scalability Projections:
| Dataset Size | Time | Cost* |
|--------------|------|-------|
| Current (33k) | 166s | $0.46 |
| 100k records | 8.2min | $1.38 |
| 1M records | 82min | $13.80 |
| 10M records | 13.7hr | $138.00 |

*\*Based on $0.10/GB-hour cloud compute pricing*

---

## 🎯 Recommendations

### For Public Health Officials:
1. **Immediate:** School/university programs for ages 18-34
2. **Short-term:** Workplace mental health for women
3. **Medium-term:** Community outreach for minority populations

### For Data Science Teams:
1. Use **Random Forest** for maximum accuracy
2. Use **Decision Tree** for rapid prototyping
3. **Avoid GBT** (68s training with no accuracy gain)

---

## 📊 Tableau Dashboards

Four interactive dashboards are included:

| Dashboard | Purpose | Target Audience |
|-----------|---------|-----------------|
| **D1: Data Quality** | Pipeline monitoring | Data engineers |
| **D2: Model Performance** | Model comparison | Data scientists |
| **D3: Business Insights** | Risk stratification | Public health officials |
| **D4: Scalability** | Cost projections | IT managers |

**Tableau Public Link:** [Your Tableau Public URL]

---

## 🛠️ Technologies Used

- **PySpark** - Big data processing (2.99M records)
- **Python 3.8+** - Core programming
- **Scikit-learn** - Machine learning models
- **Pandas/NumPy** - Data manipulation
- **Matplotlib/Seaborn** - Visualizations
- **Tableau Public** - Interactive dashboards
- **Google Colab** - Development environment

---

## 📁 Repository Structure

- **📂 data/**
  - **📂 raw/** - Raw data (not included due to size)
    - `download_instructions.txt`
  - **📂 processed/** - Cleaned CSV files for Tableau
    - `data_quality.csv`
    - `demographics.csv`
    - `confusion_matrix.csv`
    - `model_performance.csv`
    - `feature_importance.csv`
    - `resource_usage.csv`
    - `model_comparison.csv`
    - `demographic_summary.csv`
    - `accuracy_targets.csv`
    - `time_efficiency.csv`

- **📂 notebooks/**
  - `BRFSS_Depression_Analysis.ipynb`

- **📂 dashboards/**
  - `BRFSS_Depression_Report.twb`

- **📂 reports/**
  - `7006SCN_Machine_Learning_and_Big_Data_BRFSS_Depression_Prediction_&_Analysis.pdf`

- **📄 requirements.txt**
- **📄 README.md**
- **📄 LICENSE**
- **📄 .gitignore**
- **📄 setup.py**
