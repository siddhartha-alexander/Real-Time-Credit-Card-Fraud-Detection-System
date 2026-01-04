# Credit Card Fraud Detection System

## Overview

This project focuses on building a machine learning–based **Credit Card Fraud Detection System** using real-world transactional data. The primary challenge addressed in this project is **extreme class imbalance**, where fraudulent transactions represent a very small fraction of total transactions.

The goal of the project is not just high accuracy, but **effective fraud detection**, with special emphasis on minimizing **false negatives**, as missed frauds directly result in financial loss.

---

## Problem Statement

Credit card fraud detection is a classic imbalanced classification problem where:

* Legitimate transactions vastly outnumber fraudulent ones
* Traditional accuracy-based evaluation is misleading
* Business impact depends heavily on recall and precision

This project aims to:

* Compare multiple machine learning models
* Select the most suitable model based on business-driven metrics
* Justify model choice using practical reasoning

---

## Dataset

* **Type:** Credit card transaction data
* **Size:** ~2,48,000+ transactions
* **Target Variable:**

  * `0` → Legitimate transaction
  * `1` → Fraudulent transaction
* **Features:**

  * Anonymized features (V1–V28) obtained using PCA for privacy
  * Transaction-related features such as Amount and Time

> Note: Due to confidentiality reasons, original feature meanings are not disclosed.

---

## Challenges Addressed

* Extreme class imbalance
* High cost of false negatives (missed frauds)
* Model bias toward majority class
* Misleading accuracy metrics

---

## Models Implemented

The following models were trained and evaluated using the same dataset and evaluation strategy:

1. **Logistic Regression**
2. **Random Forest Classifier**
3. **XGBoost Classifier**

Hyperparameter tuning was performed using **RandomizedSearchCV** where applicable.

---

## Evaluation Metrics

Given the imbalanced nature of the data, model performance was evaluated using:

* **Precision**
* **Recall**
* **F1-Score**

Accuracy was intentionally not used as the primary metric.

---

## Model Performance Comparison

| Model               | Precision | Recall | F1-Score |
| ------------------- | --------- | ------ | -------- |
| Logistic Regression | 0.797     | 0.728  | 0.761    |
| Random Forest       | 0.797     | 0.728  | 0.761    |
| XGBoost             | 0.618     | 0.778  | 0.689    |

---

## Final Model Selection

Although Logistic Regression and Random Forest achieved higher F1-scores, **XGBoost demonstrated the highest recall**, meaning it was able to detect a larger proportion of fraudulent transactions.

In real-world fraud detection systems:

* **False negatives** are far more costly than false positives
* Flagging extra transactions is acceptable if fraud capture improves

Therefore, **XGBoost was selected as the final model**, prioritizing fraud detection effectiveness over overall metric balance.

---

## Key Learnings

* Accuracy is not a reliable metric for imbalanced datasets
* Model selection should align with business impact
* High recall is critical in fraud detection
* Metric-driven decision-making leads to better real-world systems

---

## Tools & Technologies

* Python
* Pandas, NumPy
* Scikit-learn
* XGBoost
* Matplotlib, Seaborn
* Google Colab

---

## Conclusion

This project demonstrates an end-to-end machine learning workflow for fraud detection, from data understanding to model selection and evaluation. The final solution reflects a **practical, business-oriented approach**, making it suitable for real-world deployment scenarios and resume presentation.

---

## Author

**Damala Siddhartha Alexander**

---

## Future Improvements

* Precision–Recall AUC analysis
* Cost-sensitive learning
* Real-time streaming simulation
* Model deployment using APIs
