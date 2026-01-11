# Clinical Decision Support System  
---

## Project Overview

This project implements an **AI-powered clinical decision support system** designed to assist hospital staff in identifying high-risk patients and optimizing nurse visit schedules.

The system combines:
- **Machine Learning** for short-term patient deterioration prediction
- **Clinical rules (NEWS2)** for real-time severity assessment
- **Search-based planning (Greedy A*)** for efficient nurse visit prioritization

The goal is to improve **patient safety**, **resource utilization**, and **workflow efficiency**, while keeping humans fully in control of clinical decisions.

---

## Group Members & Roles

| Name    | Role |
|---------|------|
| **Belina** | System Architecture, Random Forest, NEWS2 Logic, Greedy A* Planning |
| **Elisona** | XGBoost Modeling, Model Comparison & Selection |
| **Evelina** | Model Evaluation, Results Interpretation|

#### All members contributed to Streamlit GUI and Documentation 
---
## Dataset Source

The training dataset used in this project is the **Hospital Clinical Deterioration Dataset**
obtained from **Kaggle**.

Due to file size limitations, the dataset is not included in this repository and must be
downloaded manually before running the training notebook.
---

## AI Approach Summary

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

## Graphical User Interface (GUI)

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

## Project Structure

```text
.
├── model_training/
│   ├── train_model.ipynb
│   
├── gui/
│   ├── app.py
│   ├── patients_db.csv
|
├── README.md
└── requirements.txt
```
## How to Run the Project (Step-by-Step)

This section explains how to download, set up, and run the Clinical Decision
Support System locally.

---

### Step 1: Clone the GitHub Repository

Open a terminal and clone the project repository using:

```bash
git clone https://github.com/bdurmishi23/TermProject.git

```
## Step 2: Navigate to the Project Folder

Move into the project root directory:
```bash
cd TermProject
```
The project root directory contains:
- requirements.txt
- model_training/
- gui/
- README.md

Usually it will be saved to C:\Users\User\TermProject

## Step 3: Install Dependencies

Install all required Python libraries by running:
```bash
pip install -r requirements.txt
```
This installs the dependencies needed for both model training and the GUI.

## Step 4: Download the Dataset
The training dataset is not included in the repository due to file size limitations.
1. Download the Hospital Clinical Deterioration Dataset from this link: https://drive.google.com/file/d/1O3vETFRNkBsz1Kkaa7AIEyVs_2hPSUBt/view?usp=sharing
2. Place the dataset file (hospital_deterioration_ml_ready.csv)
inside the model_training/ folder.

## Prerequisite 
Environment Requirements
This project was developed and tested using:
- **Python version:** 3.13

To avoid dependency and kernel mismatch issues, it is strongly recommended to
use **Python 3.13** when running the training notebook and the GUI.

## Step 5: Train the Machine Learning Model
Open the notebook:
```bash
model_training/train_model.ipynb
```
Run all cells in order.
Running the notebook will:
- Preprocess the dataset
- Train Random Forest and XGBoost models
- Evaluate model performance
- Generate the following files locally:
- rf_deterioration_model.pkl
- feature_columns.pkl

## Step 6: Move Model Files to the GUI Folder

After training is completed, copy the generated files:
- rf_deterioration_model.pkl
- feature_columns.pkl
into the gui/ folder so they are located next to app.py.

### Step 7: Run the Graphical User Interface (GUI)

After the model files have been generated and saved into the `gui/` folder,
the Streamlit application can be started as follows:

1. Open the project folder in **File Explorer**.
2. Navigate to the `gui/` folder.
3. **Right-click** inside the `gui/` folder and select **“Open in Terminal”**
   (or **“Open in Command Prompt” / “Open PowerShell window here”** on Windows).
4. In the opened terminal, run:

```bash
python -m streamlit run app.py
```
The application will open in the web browser and display the patient monitoring
dashboard, deterioration risk predictions, and optimized nurse visit sequence.
