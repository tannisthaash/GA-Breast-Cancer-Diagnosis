# Breast Cancer Classification Using Genetic Algorithm, SVM, and SHAP

An interpretable machine learning framework for breast cancer diagnosis using Genetic Algorithm (GA)-based feature selection, Support Vector Machine (SVM) classification, and SHAP explainability.

---

## Overview

Breast cancer is one of the most common cancers worldwide, and early diagnosis plays a critical role in improving patient outcomes. This project proposes a machine learning framework that combines feature optimization and explainable AI to classify breast tumors as **Benign** or **Malignant**.

The proposed approach uses a **Genetic Algorithm (GA)** to identify the most informative features, a **Support Vector Machine (SVM)** for classification, and **SHAP (SHapley Additive exPlanations)** to provide model interpretability.

---

## Dataset

**Wisconsin Diagnostic Breast Cancer (WDBC) Dataset**

* Total Samples: 569
* Original Features: 30
* Classes:

  * Benign
  * Malignant

The dataset contains numerical features extracted from digitized images of fine-needle aspirate (FNA) cell nuclei.

---

## Project Workflow

```text
WDBC Dataset
      ↓
Data Preprocessing
      ↓
Baseline Models
(LR, SVM, RF, DT, KNN, Ensemble)
      ↓
Genetic Algorithm
Feature Selection
      ↓
Final SVM Classifier
      ↓
Performance Evaluation
      ↓
SHAP Explainability
```

---

## Methodology

### 1. Data Preprocessing

* Removed non-predictive ID column
* Label encoded diagnosis labels
* Standardized features using StandardScaler
* Applied 80:20 train-test split

### 2. Baseline Model Evaluation

The following classifiers were evaluated on the full feature set:

* Logistic Regression (LR)
* Support Vector Machine (SVM)
* Random Forest (RF)
* Decision Tree (DT)
* K-Nearest Neighbors (KNN)
* Ensemble Classifier

### 3. Genetic Algorithm Feature Selection

GA was used to identify the most informative subset of features.

**Configuration**

* Population Size: 50
* Generations: 40
* Crossover Probability: 0.5
* Mutation Probability: 0.2
* Selection Method: Tournament Selection
* Crossover: Two-Point Crossover
* Mutation: Bit-Flip Mutation

### 4. Final Classification Model

A Support Vector Machine classifier was trained using the selected features obtained from the GA optimization process.

### 5. Explainability

SHAP was used to:

* Measure feature importance
* Explain model predictions
* Improve interpretability of the selected biomarker subset

---

## Results

| Metric            | Value  |
| ----------------- | ------ |
| Original Features | 30     |
| Selected Features | 11     |
| Features Removed  | 19     |
| Test Accuracy     | 98.25% |
| ROC-AUC           | 0.9957 |
| False Positives   | 0      |
| False Negatives   | 2      |

### Key Findings

* Reduced feature dimensionality by approximately 63%.
* Improved classification accuracy after GA optimization.
* Achieved excellent ROC-AUC performance.
* Maintained model interpretability through SHAP analysis.
* Demonstrated that a compact biomarker subset can provide reliable breast cancer classification.

---

## Technologies Used

* Python
* Google Colab
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* DEAP
* SHAP

---

## Repository Structure

```text
├── BreastCancer_Model.ipynb
├── README.md
├── requirements.txt
├── images/
│   ├── workflow.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── shap_summary.png
└── paper.pdf
```

---

## Installation

```bash
git clone https://github.com/your-username/breast-cancer-classification-ga-svm-shap.git

cd breast-cancer-classification-ga-svm-shap

pip install -r requirements.txt
```

---

## Running the Project

Open and run:

```text
BreastCancer_Model.ipynb
```

The notebook executes the complete pipeline from preprocessing and feature selection to classification and explainability.

---

## Limitations

* Evaluated on a single benchmark dataset.
* External clinical validation was not performed.
* SHAP was used as a post-hoc interpretability method rather than being integrated into the optimization process.

---

## Future Work

* Evaluate on larger and more diverse datasets.
* Explore alternative feature-selection algorithms.
* Investigate deep learning-based classification models.
* Incorporate external clinical validation datasets.
* Extend the framework to multi-class cancer diagnosis tasks.

---

## Author

**Tannistha Ash**

**Smegha Saha**




