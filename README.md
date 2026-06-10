# Predictive Modeling for Special Care Baby Unit (SCBU) Admission

## 📌 Project Overview
This repository contains the machine learning pipeline and research developed for my **Bachelor’s Thesis in Biomedical Engineering** at the University of Padua. 

The goal of this project was to develop a robust clinical decision-support tool capable of estimating the probability of Special Care Baby Unit (SCBU) admissions based on maternal clinical history, demographic, and delivery-stage data. By leveraging a **Random Forest** framework, the model provides interpretable predictions to help hospitals optimize resource allocation and improve early neonatal risk stratification.

### Key Highlights:
* **Tech Stack:** Python, Scikit-Learn, Pandas, Matplotlib/Seaborn, Imbalanced-Learn (`imblearn`).
* **Core Algorithm:** Random Forest Classifier.
* **Clinical Focus:** Handling highly imbalanced medical data and prioritizing clinical sensitivity to minimize false negatives.

---

## 🔬 Methodology & Pipeline

Medical datasets are notoriously complex, requiring rigorous preprocessing to ensure clinical relevance. The pipeline is divided into two main Jupyter Notebooks:

### 1. Exploratory Data Analysis & Preprocessing
* **Data Cleaning:** Handling missing clinical values and dropping non-predictive features.
* **Feature Engineering:** Mapping categorical clinical text (e.g., Delivery Methods, Gestational Diabetes status, Sex) into binary machine-readable formats.
* **Correlation Analysis:** Evaluating the direct impact of maternal BMI, Ethnicity, and Gestational Diabetes on SCBU admission rates.

### 2. Handling Class Imbalance & Model Training
Because SCBU admissions represent a minority class relative to healthy births, standard accuracy metrics yield misleadingly high results while failing to catch at-risk neonates. To address this severe class imbalance, the project utilizes:
* **Resampling Techniques:** Leveraging `imblearn` to balance the class distribution without leaking information into the validation set.
* **Cost-Sensitive Learning:** Adjusting class weights within the Random Forest algorithm to penalize false negatives more heavily.
* **Hyperparameter Tuning:** Optimizing for **Sensitivity (Recall)** and **PR-AUC** rather than raw accuracy.

---

## 📁 Repository Structure

```text
SCBU-Admission-Prediction/
│
├── data/                      # Contains final processed clinical data and raw data
│   ├── GDM Dataset.csv
│   └── DataSet Final.csv
│
├── notebooks/                 # Core research and modeling pipeline
│   ├── 1_eda_and_preprocessing.ipynb
│   └── 2_model_training_evaluation.ipynb
│
├── reports/                   # Visual outputs (Correlation matrices, feature importance)
├── .gitignore                 
├── requirements.txt           # Frozen Python dependencies
└── README.md