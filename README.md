### README.md

```markdown
# Credit Card Fraud Detection

A Machine Learning pipeline designed to handle extreme class imbalance in financial transaction logging datasets.
This repository implements data pre-processing, robust evaluation techniques, class rebalancing frameworks (Down-sampling and SMOTE Over-sampling),
diagnostic visualizations, and a dynamic serialization system for production deployment. All analysis, modeling, and visualizations are self-contained
within the interactive notebook environment.

## 📋 Project Sufficiency Assessment

This architecture represents a complete, mathematically robust prototype for handling imbalanced classification.
Here is a baseline assessment of its programmatic readiness:

| Phase | Architecture Component | Sufficiency Status | Notes / Edge Cases Addressed |
| :--- | :--- | :--- | :--- |
| **Phase 1** | **Data Loading & Check** | **Sufficient** | Added runtime validation for missing labels (`NaN`) and target data constraints. |
| **Phase 2** | **Data Splitting** | **Sufficient** | Enforces **Stratified Splitting** to ensure minority representations exist in train/test splits. Employs a non-stratified fallback mechanism. |
| **Phase 3** | **Feature Scaling** | **Excellent** | Avoids **Data Leakage** by fitting the `StandardScaler` strictly on the training partition and transforming the test partition. |
| **Phase 4** | **Under-sampling** | **Sufficient** | Extracts majority elements matching minority lengths. Guarded against 0-minority data crashes. |
| **Phase 5** | **Over-sampling** | **Excellent** | Implements Synthetic Minority Over-sampling Technique (**SMOTE**) with dynamic `k_neighbors` scaling. |
| **Phase 6** | **Diagnostics & Visuals**| **Outstanding**| Includes complete evaluation profiles directly inline: Confusion Matrices, ROC Curves, Precision-Recall (PR) Curves, and Model Feature Importance plots. |
| **Phase 7** | **Deployment Pipeline** | **Production-Ready**| Automatically parses test metrics, identifies the mathematically superior classifier, and serializes a compound dictionary containing both the **Model** object and the associated **Scaler** parameters. |

---

## 🛠️ Installation & Setup

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/your-username/credit-card-fraud-detection.git](https://github.com/your-username/credit-card-fraud-detection.git)
   cd credit-card-fraud-detection
