# Graphical User Interface (GUI)

This folder contains the Streamlit-based graphical user interface for the
Clinical Decision Support System.

## Purpose
The GUI allows clinical staff to:
- View patient status and deterioration risk
- Update patient vital signs in real time
- Automatically recalculate NEWS2 scores
- Receive an AI-optimized nurse visit sequence

The GUI uses a small demo patient database for clarity and interaction.

## Running the GUI
From the project root directory, run:

```bash
streamlit run gui/app.py
