# Credit Scoring with Business Metrics

## 🏦 Project Overview
This project builds a **Credit Scoring Model** using the **German Credit Risk dataset**.  
The goal is to help financial institutions decide whether to approve or reject loan applications by balancing:  

- **Business Metrics**: Default Rate (DPD), Acceptance Rate, Profitability, Loss Rate  
- **ML Metrics**: ROC-AUC, Confusion Matrix, ROC Curve  
- **Model Explainability**: Feature Importances / Coefficients  

The project demonstrates **data science + business integration**, making it portfolio-ready for real-world applications.

---

## 🎯 Business Problem
Financial institutions need to balance:  
- Approving more customers (**growth**)  
- Avoiding bad loans (**risk management**)  
- Ensuring profitability (**sustainable lending**)  

Traditional accuracy metrics are not enough.  
We calculate **business KPIs** at different probability thresholds:  
- **Acceptance Rate** – % of customers approved  
- **Default Rate (DPD)** – % of accepted customers who default  
- **Profitability** – earnings from good loans minus losses from defaults  
- **Loss Rate** – share of disbursed loans lost to defaults  

---

## 📊 Dataset
**German Credit Dataset** (UCI Repository / Kaggle)  
- **1,000 customers** applying for credit  
- Features: Credit history, loan amount, duration, personal status, savings, employment duration, etc.  
- Target:  
  - `1 = Good credit` (loan repaid)  
  - `0 = Bad credit` (defaulted)  

---

## 🔧 Methodology
1. **Exploratory Data Analysis (EDA)**  
   - Distribution of loan amounts, durations, purpose  
   - Correlation heatmap for categorical features  

2. **Feature Engineering**  
   - Domain-inspired features:  
     - Debt-to-Income Ratio  
     - Loan Size Buckets (small, medium, large)  
     - Employment Stability Score  
   - One-hot encoding for categorical variables  

3. **Modeling**  
   - Models tested: Logistic Regression, Decision Tree, Random Forest  
   - Hyperparameter tuning with GridSearchCV (scoring = ROC-AUC)  
   - Class imbalance handled with `class_weight`  

4. **Model Selection**  
   - Best model chosen automatically by validation ROC-AUC  

5. **Evaluation**  
   - **ML Metrics**: ROC Curve, Confusion Matrix, AUC  
   - **Business Metrics**: Acceptance Rate, Default Rate, Profitability, Loss Rate  
   - **Threshold Optimization** curve to show trade-offs  

6. **Explainability**  
   - Logistic Regression → coefficients  
   - Tree-based models → feature importance plots  

---

## 📈 Results

### ✅ Best Model
- **Random Forest** with ROC-AUC = **0.81**  

### 📊 Business Metrics at Best Threshold (0.60 example)
- Acceptance Rate: **45%**  
- Default Rate: **8%**  
- Profitability: **63000 (simulated)**  
- Loss Rate: **17%**  

### 🔎 Feature Importance (Top Drivers)
- Account Status  
- Loan per Month  
- Duration  
- Debt-to-Employment  
- Credit Amount  

---

## 📉 Visualizations
- ROC Curve with AUC  
- Confusion Matrix at best threshold  
- Threshold optimization curve (Profit, Default, Acceptance)  
- Feature Importance plot  

---

## 🚀 How to Run

```bash
# Clone repo
git clone https://github.com/yourusername/credit-scoring-business-metrics.git
cd credit-scoring-business-metrics

# Install dependencies
pip install -r requirements.txt

# Run notebook
jupyter notebook credit_scoring.ipynb
