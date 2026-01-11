# 🏥 Clinical Decision Support System  
### AI-Based Patient Deterioration Prediction & Nurse Visit Prioritization

---

## 📌 Project Overview

This project implements an **AI-powered clinical decision support system** designed to assist hospital staff in identifying high-risk patients and optimizing nurse visit schedules.

The system combines:
- **Machine Learning** for short-term patient deterioration prediction
- **Clinical rules (NEWS2)** for real-time severity assessment
- **Search-based planning (Greedy A*)** for efficient nurse visit prioritization

The goal is to improve **patient safety**, **resource utilization**, and **workflow efficiency**, while keeping humans fully in control of clinical decisions.

---

## 👥 Group Members & Roles

| Name | Role |
|-----|------|
| *Your Name* | Machine Learning, Model Training |
| *Member Name* | Dataset Preparation & Analysis |
| *Member Name* | Planning Algorithm (Greedy A*) |
| *Member Name* | GUI Development (Streamlit) |
| *Member Name* | Documentation & Evaluation |

*(Update this table with your actual group members and responsibilities.)*

---

## 🧠 AI Approach Summary

### 1. Machine Learning (Risk Prediction)
- **Task:** Binary classification  
- **Target:** Patient deterioration within the next 12 hours  
- **Model used:** Random Forest (final model)  
- **Comparison model:** XGBoost  

Random Forest was selected for deployment due to:
- Stable and reliable probability estimates
- Robustness to noise and class imbalance
- Suitability for real-time decision support

The model outputs **probabilistic risk scores**, which are used for patient prioritization rather than only binary decisions.

---

### 2. Clinical Safety Layer (NEWS2)
- NEWS2 (National Early Warning Score 2) is a **clinically validated scoring system**
- Reflects the patient’s **current physiological condition**
- Complements ML predictions of **future deterioration**
- Improves interpretability and trust for clinical staff

---

### 3. Planning & Optimization (Greedy A*)
- A **Greedy A*-style planning algorithm** is used
- Computes an optimized nurse visit sequence
- Cost function combines:
  - Travel time between wards
  - Medical urgency (ML risk + patient age)

This approach enables **fast, dynamic replanning**, making it suitable for real hospital environments.

---

## 🖥️ Graphical User Interface (GUI)

The GUI is built using **Streamlit** and allows:
- Viewing patient status and risk levels
- Editing vital signs in real time
- Automatic recalculation of:
  - NEWS2 scores
  - ML-based deterioration risk
  - Optimized nurse visit sequence

The GUI uses a **small demo patient database** for clarity and interaction.  
In a real deployment, it would be connected to live hospital systems.

---

## 📂 Project Structure

```text
.
├── model_training/
│   ├── train_model.py
│   ├── hospital_deterioration_ml_ready.csv
│
├── gui/
│   ├── app.py
│   ├── patients_db.csv
│   ├── rf_deterioration_model.pkl
│   ├── feature_columns.pkl
│
├── README.md
└── requirements.txt
