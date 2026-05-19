### README.md

```markdown
# Credit Card Fraud Detection

A Machine Learning pipeline designed to handle extreme class imbalance in financial transaction logging datasets.
This repository implements data pre-processing, robust evaluation techniques, class rebalancing frameworks (Down-sampling and SMOTE Over-sampling),
diagnostic visualizations, and a dynamic serialization system for production deployment. All analysis, modeling, and visualizations are self-contained
within the interactive notebook environment.

## Execution Flow Architecture

This architecture represents a complete, mathematically robust prototype for handling imbalanced classification.
Here is a baseline of its programmatic readiness:

[ Raw Credit Card CSV Data ]
           │
           ▼
[ Data Splitting & Validation ] ──► (Guards against single-class truncations)
           │
           ▼
[ Training Set Fit: StandardScaler ] ──► (Prevents evaluation data leakage)
           │
      ┌────┴────────────────────────┐
      ▼                             ▼
[ Experiment 1: Under-sampling ]  [ Experiment 2: SMOTE Over-sampling ]
      │                             │
      ▼                             ▼
[ Logistic Regression Fit ]       [ Logistic Regression Fit ]
      │                             │
      └────┬────────────────────────┘
           │
           ▼
[ Inline Notebook Visualizations ] ──► (Confusion Matrix, ROC, Precision-Recall)
           │
           ▼
[ Dynamic ROC-AUC Selection Engine ]
           │
           ▼
[ Production Artifact: *.joblib ] ──► (Contains Model + Exact Fit Scaler)



## Performance & Metric Profiles
Because credit card fraud is highly rare (~0.17% of total records), the traditional accuracy metric is highly deceptive. This project assesses performance using:

1. Precision-Recall (PR) Curve Area: Tracks classifier efficiency across specific fraud targets.

2. Confusion Matrices: Explicitly profiles False Negatives (untracked fraud) vs. False Positives (customer friction).

3. Feature Importance (Beta Coefficients): Inspects model coefficients to determine exactly which hidden sub-components (V1-V28 variables) influence fraud predictions the most.

## Production Deployment Usage
The pipeline saves a combined joblib object ensuring that live production data undergoes the exact same feature scaling steps as the training data before reaching the model.


## 🛠️ Installation & Setup

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/your-username/credit-card-fraud-detection.git](https://github.com/your-username/credit-card-fraud-detection.git)
   cd credit-card-fraud-detection
