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

---

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.8+
PySpark 3.5+
Java 8+
Tableau Public (free) or Tableau Desktop
Git

#Installation
#1.Clone the repository
git clone https://github.com/yourusername/BRFSS-Depression-Prediction-ML-Tableau.git
cd BRFSS-Depression-Prediction-ML-Tableau

#2. Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

#3. Install dependencies
pip install -r requirements.txt

#4. Download the dataset
#  -Download the dataset from this link👇
# https://data.cdc.gov/Behavioral-Risk-Factors/Behavioral-Risk-Factor-Surveillance-System-BRFSS-P/dttw-5yxu/about_data

#5. Run the preprocessing pipeline
python src/data_loader.py
python src/preprocessor.py

#6. Train the models
python src/models.py

#7.Export data for Tableau
python src/tableau_export.py

#8. Open Tableau dashboards
#  -Install Tableau Public (free) from tableau.com
#  -Open .twbx files in dashboards/ folder
#  -Connect to CSV files in data/processed/ folder
```

## 📊 Results Summary

```python
# Quick model comparison
models = {
    'Random Forest': {'accuracy': 0.8695, 'time': 15.1},
    'GBT': {'accuracy': 0.8674, 'time': 68.0},
    'Decision Tree': {'accuracy': 0.8655, 'time': 2.3},
    'Logistic Regression': {'accuracy': 0.7401, 'time': 3.1}
}

best_model = max(models, key=lambda x: models[x]['accuracy'])
fastest_model = min(models, key=lambda x: models[x]['time'])

print(f"🏆 Best Accuracy: {best_model} ({models[best_model]['accuracy']*100:.1f}%)")
print(f"⚡ Fastest: {fastest_model} ({models[fastest_model]['time']}s)")
```
### Output:
```pyton
🏆 Best Accuracy: Random Forest (86.9%)
⚡ Fastest: Decision Tree (2.3s)
```

---

## 🔑 Key Insights

### 1. 📊 Sample Size is the Dominant Predictor (49% importance)
Survey reliability and statistical power drive depression prediction more than any demographic factor. Groups with larger sample sizes provide more accurate estimates, making this the single most important feature across all models.

### 2. 🎯 Critical Risk Groups Identified
- **Women:** 28.9% prevalence (🔴 Critical)
- **Adults 18-34:** 28.6% average prevalence (🔴 Critical)
- **Black and Other races:** 24-25% prevalence (🟠 High)
- **Immediate intervention required** for these populations

### 3. ⚡ Decision Tree Offers Best Accuracy/Speed Trade-off
- **Accuracy:** 86.55% (only 0.4% less than Random Forest)
- **Training Time:** 2.3 seconds (6.5x faster than Random Forest)
- **Ideal for production deployment** with strict latency requirements

### 4. 💰 Linear Scaling Enables Accurate Budget Planning
- **1M records:** 82 minutes processing | $13.80 compute cost
- **10M records:** 13.7 hours processing | $138.00 compute cost
- Predictable linear scaling means **costs are controllable** for enterprise deployment

### 5. 🌳 Tree-Based Methods Outperform Linear Models by 12-13%
- **Random Forest:** 86.95% accuracy
- **Logistic Regression:** 74.01% accuracy
- Confirms **non-linear relationships** in health data that linear models cannot capture

---

## 📊 Tableau Dashboards

Tableau file is included in the `Tableau/` folder:

---

### Dashboard 1: Data Quality & Pipeline Monitoring

**Purpose:** Monitor data pipeline health and quality metrics

**Target Audience:** Data engineers, data scientists

**Key Visuals:** Data quality gauges, pipeline timeline, demographic distribution

---

### Dashboard 2: Model Performance & Feature Importance

**Purpose:** Compare model performance and understand feature impact

**Target Audience:** Data scientists, ML engineers

**Key Visuals:** Model accuracy comparison, training time analysis, feature importance heatmap

---

### Dashboard 3: Business Insights & Recommendations

**Purpose:** Translate model findings into actionable insights

**Target Audience:** Public health officials, policymakers

**Key Visuals:** Prevalence treemap, risk group bar chart, recommendation cards

---

### Dashboard 4: Scalability & Cost Analysis

**Purpose:** Analyze computational costs and scalability

**Target Audience:** IT managers, DevOps engineers, budget planners

**Key Visuals:** Resource usage timeline, cost breakdown, scalability projections

---

### Interactive Story

A narrative story guides viewers through all four dashboards in sequence:

- **Story 1:** Data Quality — "Clean, balanced dataset ready for analysis"
- **Story 2:** Model Performance — "87% accuracy achieved with ensemble methods"
- **Story 3:** Business Insights — "Target interventions by demographic group"
- **Story 4:** Scalability — "Linear scaling, cost-effective deployment"

**Tableau Public Link:** [View Interactive Dashboards](https://public.tableau.com/app/profile/abhi.thumar/viz/BRFSSDepressionAnalysisAbhiThumar/BRFSSDepressionAnalysis-CompleteStory)

---

## 📈 Future Work

### Short-term (3-6 months)
- [ ] Add geographic analysis (state/county level)
- [ ] Implement temporal trends across multiple survey years
- [ ] Add SHAP explanations for model interpretability

### Medium-term (6-12 months)
- [ ] Deploy API for real-time depression risk screening
- [ ] Create interactive public dashboard for community use
- [ ] Integrate with electronic health records for validation

### Long-term (12-24 months)
- [ ] Explore causal inference methods to identify critical risk factors
- [ ] Develop fairness metrics to ensure equitable predictions
- [ ] Implement automated retraining pipeline with new data

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **PySpark 3.5+** | Big data processing (2.99M records) |
| **Python 3.8+** | Core programming language |
| **Pandas/NumPy** | Data manipulation and analysis |
| **Scikit-learn** | Machine learning models and evaluation |
| **Matplotlib/Seaborn** | Static visualizations |
| **Tableau Public** | Interactive dashboards |
| **Google Colab** | Development environment |
| **Git/GitHub** | Version control and collaboration |
