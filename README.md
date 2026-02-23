# AI-Based Early Academic Risk Prediction System Using Machine Learning

## 1) Project Overview
This project predicts three important student outcomes early in the semester:

- 🔴 **Dropout Risk** (binary or multi-class risk label)
- 🟡 **Backlog Probability** (chance of failing one or more subjects)
- 🟢 **Placement Readiness Score** (0–100 continuous score)

The objective is to detect at-risk students and provide actionable interventions to improve academic outcomes.

---

## 2) Problem Statement
Educational institutions often identify struggling students too late. By applying machine learning to academic and engagement data, this system aims to:

- Identify high-risk students early.
- Support faculty/counsellors with data-driven interventions.
- Improve retention, pass rate, and placement readiness.

---

## 3) Input Features
Suggested student-level features:

- Attendance percentage
- Internal assessment marks
- Assignment submission rate
- Previous semester GPA/CGPA
- Participation in extracurricular/co-curricular activities
- LMS login frequency and activity duration

Additional optional features:

- Lab performance
- Discipline records
- Financial aid/scholarship indicators
- Commute distance
- Psychometric/self-reported wellness signals (with consent)

---

## 4) Target Variables
The project supports multi-task prediction:

1. **Dropout Risk** → classification (e.g., Low/Medium/High or 0/1)
2. **Backlog Probability** → probabilistic classification (0–1)
3. **Placement Readiness** → regression score (0–100)

---

## 5) Proposed ML Pipeline

1. **Data Collection**
   - Student Information System (SIS)
   - LMS logs
   - Assessment records
2. **Data Preprocessing**
   - Missing value handling
   - Outlier treatment
   - Label encoding/one-hot encoding
   - Feature scaling
3. **Feature Engineering**
   - Trends (improving/declining marks)
   - Consistency metrics (weekly submission consistency)
   - Engagement ratios (active days / total days)
4. **Model Training**
   - Baselines: Logistic Regression, Random Forest
   - Advanced: XGBoost/LightGBM, CatBoost
   - Multi-output setup for joint prediction or separate models
5. **Evaluation**
   - Classification: Precision, Recall, F1, ROC-AUC
   - Regression: MAE, RMSE, R²
6. **Explainability**
   - SHAP values for feature-level interpretation
   - Global and local explanations for counselors
7. **Deployment**
   - REST API (FastAPI/Flask)
   - Dashboard for faculty and advisors

---

## 6) Intervention Engine (Action Suggestions)
Examples of recommendation rules:

- Low attendance + low marks → mandatory mentoring + attendance plan
- Low LMS engagement → weekly activity targets + nudges
- High backlog risk in specific subjects → subject-wise remedial sessions
- Low placement readiness → communication/coding aptitude training plan

---

## 7) Suggested Tech Stack

- **Language:** Python
- **Data:** Pandas, NumPy
- **Modeling:** scikit-learn, XGBoost/LightGBM
- **Explainability:** SHAP
- **API:** FastAPI
- **Dashboard:** Streamlit / React + backend API
- **Storage:** PostgreSQL / MySQL
- **MLOps (optional):** MLflow, Docker, GitHub Actions

---

## 8) Ethical & Privacy Considerations

- Obtain consent for student data use.
- Enforce role-based access and secure storage.
- Avoid sensitive bias (gender, caste, region, etc.) in model outputs.
- Keep predictions assistive—not punitive.
- Provide transparent explanations for every risk score.

---

## 9) Minimum Viable Product (MVP)

- Dataset ingestion and preprocessing pipeline
- Three prediction endpoints:
  - `/predict/dropout`
  - `/predict/backlog`
  - `/predict/placement-readiness`
- Basic faculty dashboard with:
  - Risk distribution
  - Student-level profile
  - Suggested interventions

---

## 10) Success Metrics

- Reduction in semester dropout rate
- Improvement in pass percentage and backlog reduction
- Improvement in placement test performance/readiness
- Intervention adoption rate by faculty/students

---

## 11) Future Enhancements

- Real-time risk updates from LMS streams
- Time-series forecasting for trajectory prediction
- LLM-based counselor assistant for personalized guidance
- Multilingual student nudges via email/WhatsApp/SMS
