# Graphical User Interface (GUI)

This folder contains the Streamlit-based graphical user interface for the
Clinical Decision Support System.

## Purpose
The GUI allows clinical staff to:
- Monitor patient vital signs and NEWS2 scores
- Predict 12-hour deterioration risk using machine learning
- Update patient data in real time
- Receive an AI-optimized nurse visit sequence

The GUI uses a **small demo patient database** for interaction.

## Files in This Folder
- `app.py`: Streamlit application
- `patients_db.csv`: Small demo patient database (included)

## Running the GUI

### Step 1: Install dependencies
From the project root directory:
```bash
pip install -r requirements.txt
