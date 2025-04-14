
# 🎵 Spotify Subscription Churn Prediction

This project aims to build a machine learning model that predicts whether a Spotify user is likely to churn (cancel their subscription) based on simulated user data including demographics, engagement, and subscription details.

---

## 📌 Objective

To identify patterns in user behavior that signal potential churn and help Spotify proactively retain users using data-driven insights.

---

## 🧾 Dataset Overview
 
- **Target Column:** `Churn` (Yes/No)  
- **Features:** Age, Device, Country, Subscription Plan, Payment Method, Monthly Active Days, Songs Streamed, Failed Payments, etc.  
- A derived binary target `Churn_Binary` (1 = churned, 0 = not churned) was used for modeling.

---

## 🧹 Data Cleaning

- Standardized column names and label formats  
- Replaced missing values using mode or placeholder ("Unknown")  
- Removed rows with excessive nulls and fixed negative values  
- Capped outliers and created derived columns

---

## 🔬 Feature Engineering

- Derived features:
  - `Engagement_Score = Monthly_Active_Days × Avg_Session_Duration_Min`  
  - `Activity_Ratio = Num_Songs_Streamed / Subscription_Length`  
- One-hot encoded categorical variables  
- Feature selection based on Random Forest importance

---

## 📈 Models Used

- **Logistic Regression**  
- **Random Forest Classifier** (base and tuned with GridSearchCV)  

Both were evaluated on Accuracy, Precision, Recall, and F1 Score.

---

## 🔍 Model Performance Summary

| Model                    | Accuracy | Precision | Recall | F1 Score |
|-------------------------|----------|-----------|--------|----------|
| Logistic Regression     | 0.418    | 0.418     | 1.000  | 0.590    |
| Random Forest (Tuned)   | 0.514    | 0.408     | 0.358  | 0.381    |
| Random Forest (Improved)| 0.513    | 0.401     | 0.301  | 0.344    |

---

## ✅ Final Recommendation

While Logistic Regression achieves perfect recall, it is not suitable for deployment due to low precision and poor real-world usability.  
**The tuned Random Forest model is recommended for deployment** because of its balance across key evaluation metrics.

---

## 🚀 Deployment Suggestion

The model can be deployed as:
- A **REST API** using Flask or FastAPI  
- A **batch scoring script** for integration with CRM or dashboards  
- An interactive tool using Streamlit for internal retention teams

---

## 📁 Files Included

- `cleaned_spotify_churn.csv` — Final dataset
- `Spotify_Churn_Project_Presentation.pptx` — Project slide deck
- `Spotify_Model_Metrics_Summary.docx` — Evaluation document
- `Spotify_Churn_Full_Project_Report.docx` — Detailed project write-up
- `spotify_churn_rf_improved_visuals.ipynb` — Final modeling notebook

---

## 👩‍💻 Author

**Bless(Harmandeep)**  
Capstone project for Springboard Data Science Bootcamp  
