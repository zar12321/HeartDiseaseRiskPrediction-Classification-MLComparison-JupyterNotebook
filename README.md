# Heart Disease Risk Prediction Using Machine Learning

## Project Overview

This project aims to predict the risk of heart disease based on patient clinical information using several machine learning classification algorithms.

Heart disease remains one of the leading causes of death worldwide. Early identification of high-risk patients can help healthcare professionals provide faster interventions and improve patient outcomes.

The project compares multiple machine learning models to determine the most effective algorithm for predicting significant coronary artery narrowing.

---

## Business Understanding

### Background

Heart disease is one of the leading causes of death worldwide. One important indicator in heart disease diagnosis is the level of blood vessel narrowing.

However, diagnosis often requires additional medical examinations that may be costly and time-consuming. Therefore, a data-driven approach is needed to assist in predicting heart disease risk at an earlier stage using available patient information.

### Objectives

* Develop a classification model to predict the target variabel `num` --> diagnosis of heart disease.
* Compare several machine learning algorithms:

  * Logistic Regression
  * Decision Tree
  * Random Forest
  * Support Vector Machine (SVM)
  * K-Nearest Neighbors (KNN)
* Determine the best-performing model based on evaluation metrics.

### Business Objectives

* Assist healthcare professionals in early patient screening.
* Identify high-risk patients more quickly.
* Support data-driven clinical decision making.

### Benefits

#### For Healthcare Professionals

* Early heart disease detection.
* Reduced diagnosis delays.
* Better patient prioritization.

#### For Patients

* Earlier risk awareness.
* Increased prevention opportunities.

---

## Dataset Information

The dataset contains patient clinical and medical examination information.

### Target Variable

| Value | Description                  |
| ----- | ---------------------------- |
| 0     | Blood vessel narrowing < 50% |
| 1     | Blood vessel narrowing > 50% |

This problem is formulated as a **Binary Classification** task.

### Dataset Characteristics

* Total Records: 294
* Total Features: 13
* Target Variable: `num`

Main features include:

* age
* sex
* cp
* trestbps
* chol
* fbs
* restecg
* thalach
* exang
* oldpeak
* slope
* ca
* thal

---

## Data Preparation

The following preprocessing steps were performed:

* Data type correction
* Missing value handling
* Feature encoding using One-Hot Encoding
* Feature scaling for distance-based algorithms
* Train-test split

---

## Machine Learning Models

The following algorithms were evaluated:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier
4. Support Vector Machine (SVM)
5. K-Nearest Neighbors (KNN)

Hyperparameter tuning was performed using:

* GridSearchCV
* 5-Fold Cross Validation

Optimization metric:

* Recall Score

Recall was prioritized because failing to identify a truly sick patient (False Negative) can have serious consequences.

---

## Evaluation Metrics

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Classification Report

---

## Results

### Best Model

**Logistic Regression** achieved the best performance based on Recall.

Best Hyperparameters:

```python
C = 0.1
Penalty = 'l2'
Solver = 'lbfgs'
```

Key findings:

* Recall ≈ 76.19% during model comparison.
* Classification Report showed Recall ≈ 92% on the test dataset.
* The model successfully identified most high-risk patients.

---

## Feature Importance Analysis

Based on Logistic Regression coefficients:

### Positive Risk Contributors

* **oldpeak** showed the strongest positive contribution toward heart disease risk.

### Negative Contributors

* **cp_2 (atypical angina)** reduced the probability of belonging to the high-risk class compared to the reference category.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## Project Structure

```text
├── HeartDiseaseRiskPrediction.ipynb
├── data.csv
├── README.md
└── requirements.txt
```

---

## Conclusion

Among the evaluated classification algorithms, Logistic Regression provided the best balance of predictive performance and interpretability.

The model can be utilized as an initial screening tool to assist healthcare professionals in identifying patients with a higher risk of significant coronary artery narrowing.
