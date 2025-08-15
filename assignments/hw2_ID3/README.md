# ID3 Decision Tree for Salary Prediction

## 📌 Overview

This project implements and evaluates the **ID3 Decision Tree Algorithm** to predict whether a person earns `>50K` or `<=50K` per year.
Dataset: **32,561 samples** × **13 demographic, educational, and occupational features**.

## ⚙️ Data Processing

* **Removed**: `fnlwgt`, `education-num` (redundant/irrelevant)
* **Missing values**: Replaced `"?"` with column mode
* **Discretization**: Continuous features bucketed into ranges
* **Encodings**:

  * One-Hot (too many features → impractical)
  * Label Encoding
  * Ordinal Encoding

## 📊 Class Imbalance Handling

* Dataset skewed toward `<=50K`
* **Upsampling** applied → balanced classes

## 🔍 Feature Analysis

* Correlation analysis identified top influencing features:

  * `relationship`, `marital-status`, `sex`, `age_group`, `capital_gain_group`

## 🧪 Experiments

| Method                    | Accuracy   | Precision  | Recall     | F1-Score   |
| ------------------------- | ---------- | ---------- | ---------- | ---------- |
| Label Encoding            | 0.8323     | 0.6634     | 0.5567     | 0.6054     |
| Ordinal Encoding          | 0.8323     | 0.6634     | 0.5567     | 0.6054     |
| High-Correlation Features | 0.8052     | 0.7772     | 0.2477     | 0.3757     |
| Random Features Subset    | 0.7958     | 0.5893     | 0.4562     | 0.5143     |
| **Balanced Data**         | **0.8722** | **0.8478** | **0.9197** | **0.8823** |

## 🏆 Key Findings

* **Balancing data** greatly boosts recall & F1-score.
* High-correlation feature selection improves precision but reduces recall.
* Label & ordinal encoding give similar results.
* **Best performance**: Balanced dataset + ID3.

## 🚀 Conclusion

Balancing imbalanced datasets is critical for classification accuracy.
**ID3 + Upsampling** achieved the best trade-off between accuracy and recall.


