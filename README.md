# explainable-fetal-health-classification
Explainable stacked ensemble machine learning framework for multiclass fetal health classification using CTG data, SMOTE, and SHAP-based interpretability.

# Explainable Stacked Ensemble Machine Learning for Multiclass Fetal Health Classification

## Overview

Cardiotocography (CTG) is widely used for intrapartum fetal monitoring, but manual interpretation is often subjective and prone to inter-observer variability.

This research proposes an explainable stacked ensemble machine learning framework for multiclass fetal health classification using CTG data. The framework combines multiple machine learning models with explainable AI techniques to improve predictive performance while maintaining clinical interpretability.

The study focuses on classifying fetal health into:

- Normal
- Suspect
- Pathological

---

## Research Objectives

- Improve fetal health classification accuracy
- Address class imbalance in CTG data
- Enhance detection of pathological fetal conditions
- Provide interpretable AI-based decision support
- Identify clinically relevant predictors of fetal distress

---

## Dataset

**Dataset:** Cardiotocography (CTG) Dataset

**Source:** UCI Machine Learning Repository

Dataset Characteristics:

- 2,126 CTG recordings
- 21 clinical features
- Three fetal health classes
 
|     Class    | Instances |
|--------------|-----------|
| Normal       |   1655    |
| Suspect      |   295     |
| Pathological |   176     |

---

## Proposed Framework

### Data Preprocessing

- Missing value inspection
- Data quality validation
- Z-score normalization

### Class Imbalance Handling

- SMOTE (Synthetic Minority Oversampling Technique)
- Applied within Stratified 10-Fold Cross Validation

### Stacked Ensemble Architecture

#### Base Learners

- Random Forest
- XGBoost
- Support Vector Machine (SVM)

#### Meta Learner

- Logistic Regression

### Explainability

- SHAP (SHapley Additive Explanations)

---

## Methodology Workflow

```text
CTG Dataset
      │
      ▼
Data Preprocessing
      │
      ▼
Z-score Normalization
      │
      ▼
SMOTE Balancing
      │
      ▼
Base Models
(RF + XGBoost + SVM)
      │
      ▼
Logistic Regression
Meta Learner
      │
      ▼
Final Prediction
      │
      ▼
SHAP Explainability
```

---

## Hyperparameter Configuration

|         Model       |          Configuration          |
|---------------------|---------------------------------|
| Random Forest       | 200 Trees                       |
| XGBoost             | 150 Estimators, LR=0.1, Depth=6 |
| SVM                 | RBF Kernel, C=1.0               |
| Logistic Regression | LBFGS, Max Iter=1000            |

---

## Results

### Performance Metrics

|        Metric       | Score |
|---------------------|-------|
| Accuracy            | 96.4% |
| Macro F1 Score      | 0.94  |
| Pathological Recall | 0.92  |
| ROC-AUC             | ~0.97 |

### Key Findings

- High classification performance across all classes
- Improved detection of minority pathological cases
- Strong generalization through ensemble learning
- Reliable clinical decision support capability

---

## Explainable AI Analysis

SHAP was used to improve transparency and interpretability of model predictions.

### Important Clinical Indicators

- Abnormal Short-Term Variability (ASTV)
- Prolonged Decelerations
- Accelerations
- Baseline Fetal Heart Rate
- Uterine Contractions

SHAP analysis demonstrated that the model relies on clinically meaningful fetal health indicators, supporting its use as an interpretable decision-support system.

---

## Clinical Impact

The proposed framework provides:

- Reliable fetal health assessment
- Early identification of high-risk fetal conditions
- Improved minority-class sensitivity
- Transparent AI-assisted clinical decision support

---

## Research Contributions

- Developed a stacked ensemble learning framework
- Integrated SMOTE for imbalance-aware learning
- Applied SHAP for explainable predictions
- Improved pathological case detection
- Generated clinically interpretable insights from CTG data

---

## Technologies Used

### Programming Language

- Python

### Machine Learning

- Scikit-learn
- XGBoost
- Random Forest
- Support Vector Machine
- Logistic Regression

### Explainable AI

- SHAP

### Data Processing

- Pandas
- NumPy

### Visualization

- Matplotlib
- Seaborn

---

## Research Paper

The complete research paper is available in the repository.

Title:

**Explainable Stacked Ensemble Machine Learning for Multiclass Fetal Classification from Cardiotocography Data**

---

## Authors

- Sreenidhi S (UG Scholar)
- R.M. Tharsanee (Assistant Professor)

Department of Artificial Intelligence and Data Science

Kumaraguru College of Technology, Coimbatore, India

---

## Future Work

- Validation on larger multi-center datasets
- Deep learning models for raw CTG signal analysis
- Real-time clinical deployment
- Enhanced explainability techniques
- Integration with healthcare decision-support systems
