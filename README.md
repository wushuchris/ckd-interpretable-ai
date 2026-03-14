# Chronic Kidney Disease Prediction with Interpretable AI

Machine learning project for predicting **Chronic Kidney Disease (CKD)** using clinical laboratory measurements.  
The project demonstrates a full data science workflow including **data cleaning, exploratory analysis, predictive modeling, and explainable AI (SHAP)**.

The goal is to build a model that not only predicts CKD accurately but also **explains which medical features drive the predictions**, improving transparency in healthcare AI systems.

---

# Project Overview

Chronic Kidney Disease is a serious condition that affects kidney function over time. Early detection can help improve treatment outcomes and prevent disease progression.

This project uses clinical data to train machine learning models capable of predicting CKD based on patient laboratory results and health indicators.

The workflow includes:

- Data auditing and cleaning
- Exploratory data analysis
- Predictive modeling
- Model evaluation
- Explainable AI with SHAP

---

# Dataset

Dataset Source:  
https://www.kaggle.com/datasets/mansoordaku/ckdisease

The dataset contains clinical features commonly used to evaluate kidney function.

Examples include:

- Hemoglobin level
- Packed cell volume
- Specific gravity
- Blood glucose
- Blood urea
- Serum creatinine
- Hypertension status
- Diabetes status

Dataset summary:

| Metric | Value |
|------|------|
| Total samples | 200 |
| Features | 26 |
| Target variable | CKD diagnosis |

Target encoding:

| Value | Meaning |
|------|------|
| 1 | CKD |
| 0 | No CKD |

The raw dataset is **not stored in this repository** due to dataset licensing restrictions. Users can download it directly from Kaggle.

---

# Exploratory Data Analysis

Exploratory analysis revealed strong relationships between CKD and several clinical variables.

Key findings:

| Feature | Relationship with CKD |
|------|------|
| Hemoglobin | Lower values associated with CKD |
| Packed Cell Volume | Lower values associated with CKD |
| Specific Gravity | Lower urine density linked to CKD |
| GFR | Reduced filtration rate strongly linked to CKD |
| Hypertension | Higher prevalence among CKD patients |

These findings align with established medical knowledge regarding kidney disease progression.

---

# Machine Learning Models

Three models were trained and evaluated:

- Logistic Regression
- Random Forest
- Gradient Boosting

Models were trained using an **80/20 train-test split** with stratification to preserve class balance.

Missing values were handled using a **median imputation pipeline**.

---

# Model Performance

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|------|------|------|------|------|------|
| Logistic Regression | 0.975 | 1.00 | 0.962 | 0.980 | 1.00 |
| Random Forest | **1.00** | **1.00** | **1.00** | **1.00** | **1.00** |
| Gradient Boosting | 0.975 | 1.00 | 0.962 | 0.980 | 1.00 |

The Random Forest model achieved perfect classification on the test set, likely due to strong separability between CKD and non-CKD patients based on laboratory features.

---

# Model Explainability

To improve transparency, SHAP (SHapley Additive exPlanations) was used to analyze model behavior.

SHAP revealed the most influential features for predicting CKD:

1. Hemoglobin
2. Packed Cell Volume
3. Specific Gravity
4. Glomerular Filtration Rate
5. Albumin
6. Hypertension

These variables are clinically relevant indicators of kidney health.

Global SHAP visualization shows how features influence model predictions across the dataset.

Local SHAP explanations demonstrate how individual features influence predictions for specific patients.

This approach improves interpretability and aligns the model with medically meaningful relationships.

---

# Key Insights

- Hemoglobin and packed cell volume are the strongest predictors of CKD.
- Reduced kidney filtration rate significantly increases predicted CKD risk.
- Urine specific gravity provides additional signal about kidney function.
- Machine learning models can accurately identify CKD patterns in clinical data.

The agreement between **EDA results, model feature importance, and SHAP explanations** suggests the models are learning meaningful physiological relationships rather than noise.

---

# Technologies Used

Python libraries used:

- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- SHAP

---

# Future Improvements

Potential extensions for this project include:

- Cross-validation with larger datasets
- Hyperparameter optimization
- Clinical risk scoring system
- Model deployment using a lightweight API
- Integration with electronic health records

---

# Acknowledgements

This project was completed in collaboration with **Antonio Recalde**, whose contributions helped support the development, analysis, and evaluation of the CKD prediction models.

---

# Author

Christopher
Machine Learning Portfolio Project
