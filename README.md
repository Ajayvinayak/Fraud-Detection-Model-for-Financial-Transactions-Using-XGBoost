# 💳 Fraud Detection with XGBoost

This project focuses on detecting fraudulent financial transactions using Machine Learning. It was developed using a real-world dataset of 471MB provided by Accredian for internship selection. The objective was to build and evaluate models that can reliably identify fraud in highly imbalanced transaction data.

---

## 📁 Dataset Description

- **Size**: 471MB
- **Source**: Provided by Accredian for internship shortlisting.
- **Records**: 6.3 million+ transaction-level entries.
- **Features**: Includes `step`, `amount`, `oldbalanceOrg`, `newbalanceOrig`, `oldbalanceDest`, `newbalanceDest`, and `type` (transaction type).
- **Target**: `isFraud` – a binary flag indicating fraudulent transactions.

No missing values were found in the dataset. One duplicate row was removed during data cleaning. All variables contributed meaningfully to the model.

---

## ⚙️ Models Used

### ✅ Model A: Baseline XGBoost

- Used default threshold (0.5).
- SMOTE applied to address class imbalance.
- 5-Fold Stratified Cross Validation.
- Evaluation Metrics:
  - **Accuracy**: 99.48%
  - **Recall**: 98.92%
  - **Precision**: 19.47%
  - **ROC AUC**: 0.9990

### ✅ Model B: Threshold-Tuned XGBoost

- Same setup as Model A, but evaluated at thresholds: 0.5, 0.4, 0.3, 0.2.
- Helped understand how threshold tuning affects sensitivity vs specificity.
- At threshold = 0.2:
  - **Accuracy**: 99.07%
  - **Recall**: 99.43%
  - **Precision**: 12.10%
  - **ROC AUC**: 0.9990

---

## 🥇 Conclusion

While Model B offers flexible fraud detection using thresholds, **Model A** is selected as the best model due to its higher overall precision with excellent recall and AUC. It ensures fewer false positives while still capturing most fraudulent transactions.

---

## 📌 Key Findings

- Transaction types like `TRANSFER` and `CASH_OUT` are strong indicators of fraud.
- Imbalance handling with SMOTE is critical.
- Threshold tuning can increase sensitivity but may reduce precision.

---

## 🚀 Future Recommendations

- Deploy the model in real-time fraud detection pipelines.
- Continuously monitor drift in transaction behavior.
- Implement anomaly detection and MFA for suspicious users.

---

## 📬 Author

**Ajay Vinayak Y**  
Final Year CSE – Big Data Analytics  
SRM Institute of Science and Technology  
Email: ajayvinayak19@gmail.com  
