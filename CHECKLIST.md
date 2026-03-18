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




This dataset contains simultaneous two-handed smartwatch records of active assessments designed by neurologists to trigger tremor characteristics. Assessment steps were performed consecutively in the order they are listed above (Table 1). At the start of every recording, the smartwatches gave a vibration notification. Therefore, we recommend to cut out approximately the first 0.5 seconds per time series.
One drawback of the dataset is the imbalanced class distribution. For the application and evaluation of machine learning, we therefore recommend using class-balancing mechanics and to measure performance in terms of balanced accuracy. Although the dataset is balanced in terms of age distribution, there are still demographic differences in the study data. Since the cohort consists mainly of routine patient visits and concomitant persons, gender distribution is influenced by prevalence, which is known to be higher in men for PD. To account for this imbalance for e.g. machine learning evaluation, we propose the extraction of a stratified subset that further is matched by gender.
We used the pre-processed data for machine learning, see our git repository [5] that holds all relevant code. To ensure comparability of machine learning algorithms trained on the dataset, we provide recommended splits for training and test sets (via 5-fold cross-validation).