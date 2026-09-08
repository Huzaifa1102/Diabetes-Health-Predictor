# Diabetes Health Predictor — Multi-Layer Perceptron (MLP)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Machine Learning](https://img.shields.io/badge/Machine--Learning-MLP-orange)
![WandB](https://img.shields.io/badge/Weights_%26_Biases-Logged-yellow?logo=weightsandbiases)
![License](https://img.shields.io/badge/license-MIT-blue)

**Author:** MUDASSAR MUHAMMAD Huzaifa  
**Context:** Developed during Semester Exchange at CESI (Strasbourg, France).

---

## 📌 Project Overview

Diabetes is one of the most prevalent chronic health conditions globally. Early detection and risk factor analysis allow for preventative lifestyle changes and clinical intervention. This project builds an optimized **Multi-Layer Perceptron (MLP)** binary classification pipeline to predict diabetes probability based on the **CDC Behavioral Risk Factor Surveillance System (BRFSS 2015)** dataset (253,680 records across 22 health indicators).

---

## 📊 Dataset & Health Indicators

- **Diabetes_binary**: `0` = No Diabetes / Prediabetes, `1` = Diagnosed Diabetes
- **Risk Indicators**: High Blood Pressure (`HighBP`), High Cholesterol (`HighChol`), BMI (`BMI`), Smoking (`Smoker`), Stroke History (`Stroke`), Heart Disease (`HeartDiseaseorAttack`), Physical Activity (`PhysActivity`), Fruit Consumption (`Fruits`), Age, Income, Education.

---

## 🔬 Methodology & Key Achievements

- **Class Imbalance Optimization**: Solved severe class imbalance (86% vs 14%) using class weighting over SMOTE to maximize clinical recall.
- **Experimentation**: 10 distinct experiments logged via Weights & Biases (W&B).
- **Optimal Model**: Dropout + Class Weighted MLP with an adjusted decision threshold of `0.35`.
- **ROC AUC**: Achieved an **AUC of 0.811** and boosted Recall from `0.12` to `0.786`.
- **Explainability**: SHAP (SHapley Additive exPlanations) values identified General Health, BMI, Age, High BP, and High Cholesterol as key risk factors.
- **Eco-Tracking**: Model training tracked an energy footprint of only `0.000142 kg CO2`.

---

## ⚙️ Quick Start

```bash
# Clone repository
git clone https://github.com/Huzaifa1102/Diabetes-Health-Predictor.git
cd Diabetes-Health-Predictor

# Install dependencies
pip install -r requirements.txt

# Run main model training pipeline
python main.py
```