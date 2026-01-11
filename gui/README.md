# Graphical User Interface (GUI)

This folder contains the **Streamlit-based graphical user interface** for the
Clinical Decision Support System.

The GUI provides an interactive dashboard that allows nurses or clinical staff
to monitor patients, assess risk, and receive AI-supported visit prioritization
recommendations.

---

## 📌 Purpose of the GUI

The GUI enables users to:

- View patient vital signs and demographic information
- Monitor patient severity using the NEWS2 score
- Predict 12-hour clinical deterioration risk using a trained ML model
- Update patient vital signs in real time
- Automatically recalculate NEWS2, risk scores, and visit priorities
- Receive an AI-optimized nurse visit sequence based on urgency and distance

The GUI uses a **small demo patient database** to clearly demonstrate system
behavior and interaction.

---

## 📂 Files in This Folder

- `app.py`  
  Streamlit application implementing the GUI and decision-support logic.

- `patients_db.csv`  
  Demo patient database (5 representative patients) used for interaction
  and visualization in the GUI.

- `rf_deterioration_model.pkl` *(generated locally)*  
  Trained Random Forest model used for risk prediction.

- `feature_columns.pkl` *(generated locally)*  
  List of feature columns required by the trained model.

> ⚠️ The `.pkl` files are **not included in the GitHub repository** due to
> file size limitations.

---

## ⚙️ Prerequisites

Before running the GUI, make sure you have:

- Python 3.8 or higher
- All required Python libraries installed

Install dependencies from the project root using:

pip install -r requirements.txt

## Generating and Using Model Files (`.pkl`)

The graphical user interface requires trained machine learning model files
to perform deterioration risk prediction.

### Step 1: Generate the model files
From the project root directory, run the training script:

```bash
python model_training/train_model.py

gui/
├── app.py
├── patients_db.csv
├── rf_deterioration_model.pkl
└── feature_columns.pkl

