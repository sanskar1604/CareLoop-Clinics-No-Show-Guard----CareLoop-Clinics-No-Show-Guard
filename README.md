# CareLoop Clinics – No\-Show Guard

## Repository Link

https://github.com/sanskar1604/CareLoop-Clinics-No-Show-Guard----CareLoop-Clinics-No-Show-Guard.git

---

## Project Summary

The project analyses appointment attendance data and predicts no\-show risk for CareLoop clinics.

Key results:

- Raw appointment records: **1,020**
- Clean appointment records: **990**
- No\-shows: **218 (22.0%)**
- Logistic Regression ROC\-AUC: **~0.79**
- Chosen risk threshold: **0.35**
- High\-risk appointments flagged in test set: **~49**

---

## Model Recommendation

The recommended model is **Logistic Regression** with a decision threshold of **0.35**.

The model achieved approximately **0.79 ROC\-AUC**, which was the strongest performance among the evaluated methods. Lowering the threshold from 0.50 to 0.35 increased recall substantially while maintaining acceptable precision. Since missed no\-show appointments directly waste available clinic capacity, identifying more potential no\-shows is valuable even if some additional patients are flagged unnecessarily.

The analysis also showed that appointments with longer lead times and prior no\-show history were associated with greater no\-show risk. Follow\-up note analysis indicated that appointments classified as **forgot\_or\_no\_reminder** were linked to cases where reminders were not sent.

---

## Follow\-Up Note Findings

- Total analysed notes: **10**
- Notes classified as **forgot\_or\_no\_reminder**: **2**
- Both of these appointments had **reminder\_sent = No**
- Appointments with **reminder\_sent = No** in the note sample: **5 of 10**

---

## Limitations

1. The follow\-up note sample contains only ten notes and may not represent all clinic no\-show reasons.
2. Data cleaning was completed before the train/test split, which may slightly influence performance estimates.
3. The dataset is observational, so model relationships should not be interpreted as proof of causation.

---

## Files Included

- appointments\_clean.csv
- clinics\_enriched.csv
- load\_data.sql
- test\_risk\_scores.csv
- notes\_analysed.csv
- notes\_appointments\_merged.csv
- Capstone notebook / Python script
- README.md

