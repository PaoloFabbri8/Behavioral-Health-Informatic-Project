# Behavioral Health Informatics — Project Checklist

Dataset Link: https://physionet.org/content/parkinsons-disease-smartwatch/1.0.0/
---

## 1️⃣ Data Exploration and Preparation
**Goal:** Understand the data structure and quality before extracting features

- [ ] Load smartwatch data
- [ ] Load questionnaire data
- [ ] Check PD / non-PD distribution
- [ ] Basic cleaning: handle missing values
- [ ] Basic cleaning: correct data errors

---

## 2️⃣ Feature Engineering
**Goal:** Transform raw signals into values interpretable by the model

- [ ] Extract time-domain features: mean, variance, RMS, peak-to-peak (from sensors)
- [ ] Extract frequency-domain features: tremor power, dominant frequency
- [ ] Prepare questionnaire and demographic data
- [ ] Create final dataset X (features) and y (PD / non-PD)

---

## 3️⃣ Model Training and Validation
**Goal:** Build a robust predictive model and evaluate performance

- [ ] Split train/test (e.g. 80/20)
- [ ] Train Random Forest
- [ ] Basic parameter tuning: number of trees
- [ ] Basic parameter tuning: max depth
- [ ] Validate with accuracy
- [ ] Validate with precision
- [ ] Validate with recall
- [ ] Validate with F1-score

---

## 4️⃣ Feature Importance and Interpretation
**Goal:** Identify the most predictive digital biomarkers

- [ ] Compute `feature_importances_` from Random Forest
- [ ] Visualize feature ranking (bar plot)
- [ ] Visualize SHAP summary plot
- [ ] Interpret which signals or questionnaires are most relevant

---

## 5️⃣ Conclusions and Report
**Goal:** Clearly present the main findings of the project

- [ ] Summarize the main results
- [ ] Compare sensitivity / importance between sensors and questionnaires
- [ ] Prepare final presentation figures
- [ ] Prepare summary tables for presentation
- [ ] Write the final report


