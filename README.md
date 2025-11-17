# Customer Churn Prediction Using Machine Learning

Predicting telecom customer churn using advanced data preprocessing, feature engineering, and multiple ML models. This project builds an end-to-end pipeline with EDA, encoding, SMOTENC balancing, model comparison, and business-impact insights.

---

## 📌 Project Overview
Customer churn directly affects recurring revenue, customer lifetime value, and retention costs. This project identifies customers likely to churn and provides insights that help businesses make proactive decisions.

The goal is to build a robust ML pipeline that predicts churn accurately and highlights the factors driving customer attrition.

---

## 📂 Dataset
**Source:** Telco Customer Churn Dataset  
**Target Variable:** `Churn` (encoded as 1 = churned, 0 = stayed)

The dataset includes:
- Customer demographics  
- Services subscribed  
- Internet, phone, security services  
- Account information  
- Charges & Tenure details  

---

## 🧹 Data Preprocessing
- Converted `TotalCharges` → numeric  
- Removed unnecessary columns like `customerID`  
- Identified numerical & categorical columns  
- Encoded `Churn` into binary  
- Checked for duplicates & null values  
- Normalized and encoded features via `ColumnTransformer`

---

## 📊 Exploratory Data Analysis (EDA)
Explored churn distribution across:
- Gender, SeniorCitizen, Partner, Dependents  
- Internet/Phone services  
- Contract type & payment method  
- Monthly Charges & Tenure  

Interactive visualizations using **Plotly**.

---

## ⚙️ Feature Engineering
Created meaningful features:
- **TotalServicesSubscribed** → total additional services opted  
- **SeniorNoTechSupport** → seniors without support  
- **TenureGroup** → tenure bucketization (0–12, 13–24, etc.)

Mapped categorical options (“Yes”, “No”, “No internet service”) into binary/ordinal form.

---

## 🏗️ Encoding & Scaling
Using **ColumnTransformer**:
- `StandardScaler` for numerical columns  
- `OneHotEncoder` for multi-category columns  
- `OrdinalEncoder` for binary columns  

---

## ⚖️ Handling Class Imbalance
Used **SMOTENC** to oversample minority class while respecting categorical features.

---

## 🤖 ML Models Used
Built pipelines combining:
- Preprocessor  
- SMOTENC  
- Model classifier  

Models evaluated:
- Random Forest  
- Decision Tree  
- SVM  
- Logistic Regression  
- XGBoost  
- CatBoost  
- LightGBM  

---

## 🧪 Model Evaluation Metrics
Measured:
- Accuracy  
- Precision  
- Recall  
- F1 Score  
- AUC-ROC  

Created ROC curves and classification reports for each model.

---

## 📈 Business Metrics & Impact

**Why churn prediction matters for business:**
- Reduces customer acquisition cost (CAC)
- Increases customer lifetime value (CLV)
- Improves retention and revenue stability
- Helps target high-risk customers with personalized offers

**Business KPIs measured or derived:**
- **Churn Rate (%)** – % of customers leaving  
- **Retention Rate (%)** – customers staying  
- **Average Revenue Per User (ARPU)** – used with MonthlyCharges  
- **Customer Lifetime Value (CLV)** approximation using tenure  
- **High-Risk Segments** identified:
  - Month-to-month customers
  - Customers with high MonthlyCharges
  - Users without TechSupport/OnlineSecurity
  - Customers in first 12 months (0–12 tenure group)

**Impact**
- Helps marketing and service teams create targeted retention campaigns  
- Reduces churn through proactive intervention  
- Prioritizes customers with highest revenue impact  

---

## 🏁 Results Summary
Models achieved strong performance, with **LightGBM, CatBoost, and RandomForest** showing highest stability and AUC-ROC.  
Feature importance revealed:
- Contract type (Month-to-Month highest churn)
- Tenure
- MonthlyCharges  
- TechSupport & OnlineSecurity  
as major churn drivers.

---

## 🧠 Key Learnings
- Handling categorical-heavy datasets with SMOTENC  
- Importance of engineered features in churn  
- Proper model evaluation beyond accuracy  
- Value of ROC-AUC and recall for churn problems  
- Benefits of automated pipelines  

---

## 🚀 Future Improvements
- Add SHAP for explainability  
- Deploy model via FastAPI / Streamlit  
- Use Optuna for advanced hyperparameter tuning  
- Build retention recommendation system  

---

## 🗂️ Tech Stack
- Python  
- Pandas, NumPy  
- Plotly, Seaborn, Matplotlib  
- Scikit-learn  
- SMOTENC (Imbalanced-learn)  
- XGBoost, CatBoost, LightGBM  
- Jupyter Notebook  

---


