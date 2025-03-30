# Hybrid Modeling of RF and FSO Signal Attenuation

A machine learning-based approach to predict signal attenuation in hybrid RF–FSO communication systems under varying weather conditions. This capstone project was developed as part of the Master of Data Science program at the University of Adelaide.

## 📌 Project Overview

Weather can significantly impact communication signals—FSO (Free Space Optics) is highly affected by fog and rain, while RF (Radio Frequency) suffers in heavy rainfall. This project builds predictive models to quantify and forecast RF and FSO signal attenuation using real-world weather data.

Key Goals:
- Predict RF (`RFL_Att`) and FSO (`FSO_Att`) attenuation from 27 environmental features.
- Evaluate **general models** vs. **weather-specific (SYNOP-based)** models.
- Apply **feature selection**, **data balancing**, and **hyperparameter tuning** for performance optimization.
- Analyze whether predicted RF attenuation can enhance FSO prediction.

---

## 🧠 Machine Learning Approach

- **Model Type**: Random Forest Regressors (with Out-of-Bag scoring)
- **Feature Selection**: Backward Elimination based on OOB importance
- **Model Types**:
  - General models trained on all weather data
  - Per-SYNOP models (trained individually for each weather condition code)
  - Hybrid FSO model using predicted RFL_Att as input
- **Evaluation Metrics**: RMSE, R² Score, OOB Score, Pearson Correlation, Mutual Information

---

## 🔧 Technologies Used

- Python 3.11
- scikit-learn
- pandas, numpy
- seaborn, matplotlib
- Jupyter Notebook

---

## 📊 Key Results

| Model                     | RMSE   | R² Score | OOB Score |
|--------------------------|--------|----------|-----------|
| General RF Model         | 0.734  | 0.944    | 0.935     |
| General FSO Model        | 0.956  | 0.966    | 0.966     |
| Hybrid FSO (with RF_Att) | 1.443  | 0.867    | 0.866     |

- **Per-SYNOP models** showed improved RMSE and R² for RF predictions.
- **FSO prediction** remained challenging due to higher environmental sensitivity.
- Correlation analysis revealed **low linear dependence** between RF and FSO signals.

---

## 📁 Repository Structure

