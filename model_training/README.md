# Model Training

This folder contains the Jupyter Notebook used to train and evaluate
the machine learning models for patient deterioration prediction.

## Contents
- `train_model.ipynb`: Notebook for data preprocessing, model training,
  and evaluation.

## Dataset

The training dataset is **not included in the GitHub repository**
due to file size limitations.

To run the training notebook:
1. Download the **Hospital Clinical Deterioration Dataset** from Kaggle.
2. Place the dataset file (`hospital_deterioration_ml_ready.csv`)
   in this `model_training/` folder.

## How to Train the Model

1. Open `train_model.ipynb` using Jupyter Notebook or JupyterLab.
2. Run **all cells in order**.

Running the notebook will:
- Load the dataset
- Train Random Forest and XGBoost models
- Evaluate model performance
- Save the trained Random Forest model and feature list as `.pkl` files

## Model Output

After running all cells, the following files will be generated locally:
- `rf_deterioration_model.pkl`
- `feature_columns.pkl`

These files are required by the GUI and are not included in GitHub.
# Model Training

This folder contains the Jupyter Notebook used to train and evaluate
the machine learning models for patient deterioration prediction.

## Contents
- `train_model.ipynb`: Notebook for data preprocessing, model training,
  and evaluation.

## Dataset

The training dataset is **not included in the GitHub repository**
due to file size limitations.

To run the training notebook:
1. Download the **Hospital Clinical Deterioration Dataset** from Kaggle.
2. Place the dataset file (`hospital_deterioration_ml_ready.csv`)
   in this `model_training/` folder.

## How to Train the Model

1. Open `train_model.ipynb` using Jupyter Notebook or JupyterLab.
2. Run **all cells in order**.

Running the notebook will:
- Load the dataset
- Train Random Forest and XGBoost models
- Evaluate model performance
- Save the trained Random Forest model and feature list as `.pkl` files

## Model Output

After running all cells, the following files will be generated locally:
- `rf_deterioration_model.pkl`
- `feature_columns.pkl`

These files are required by the GUI and are not included in GitHub.

