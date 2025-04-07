----Start

**
# Network Intrusion Detec**ton

This repository contains a machine learning project focused on detecting network intrusions using the NSL-KDD dataset. The work combines extensive exploratory data analysis (EDA), feature engineering, and model evaluation using several classification m.


**---

## Table o**fCotents
ectstructure)](#mehodology)
  - [Data Pre-procesing--eda)
  - [Feature Engineering-selection)
  - [Dimensionality Reduction an-intepretability)
  - [ode- g-approaches)
  -#evluation-metrics)
](#esults--findings)
-s [**ense](#l**iense)

---

## Overview

This project aims to develop an effective Intrusion Detection System (IDS) using machine learning techniques. By leveraging the NSL-KDD dataset—an improved version of the original KDD'99 dataset—the study assesses network traffic and detects various types of cyber attacks. The primary objectives include:
- **Exploratory Analysis:** Understanding the structure, distribution, and relationships within the data.
- **Feature Engineering:** Refining and selecting key features to improve model performance.
- **Modeling:** Implementing baseline and enhanced classification models (including Logistic Regression, Decision Trees, and Random Forests) for both multi-class and binary + multi-class detection.
- **Interpretability:** Using PCA for dimensionality reduction and SHAP values **ture im**prtance analysis.

---

## Dataset

The project uses the **NSL-KDD dataset**, which contains:
- **125,973 records** in the training set with 41 features and 1 label.
- A mix of numerical (float64, int64) and categorical (object) variables.
- Labels that initially include 23 distinct classes (various network attack types), later consolidated into five classes (normal  importantr types of attacks).

The dataset is crucial for developing an IDS capable of handling imbalanced data, where the majority of network traffic is benignth**xperimental**r### ts and recommendations for future work.

---

## Methodology

### Data Pre-processing & EDA

- **Data Integrity Checks:**  
  Verified that there are no missing or duplicate values.
  
- **Exploratory Data Analysis:**  
  Visualized the distribution of features, identified 23 distinct labels, and examined the balance between normal traffic and attack types.
  
- **Handling Mixed Data Types:**  
  Separated numeric features from categorical ones, ensuring that subsequent c### lation analysis and model training are performed on the correct data types.

### Feature Engineering & Selection

- **Label Consolidation:**  
  Reduced the original 23 labels into 5 consolidated classes (one normal and four attack types) to simplify the classification task.
  
- **Rare Service Handling:**  
  Rare values in categorical features (such as 'service') were grouped to avoid overfitting.
  
- **Feature Scaling:**  
  Applied standard scaling to numeric features to normalize their distributions.
  
- **Feature Selection:**  
  Removed highly correlated### nstant, or quasi-constant features to reduce dimensionality and improve model robustness.

### Dimensionality Reduction and Interpretability

- **Principal Component Analysis (PCA):**  
  Applied PCA for visualization purposes. The scatter plots of the first two principal components illustrated the overlap among classes, highlighting the classification challenges.
  
- **SHAP Analysis:**  
  Used SHAP values to identify the most important features influenc### the model predictions. Notably, features like `source_bytes` were found to be highly influential.

### Modeling Approaches

- **Baseline 5-Class Classification:**  
  Implemented three classifiers:
  - **Logistic Regression**
  - **Decision Tree**
  - **Random Forest**
  
  Each classifier was evaluated on its ability to distinguish between the five classes (normal and four attack types).

- **Balanced Weights Approach:**  
  Addressed the class imbalance by incorporating balanced weights, improving performance on minority attack classes (e.g., R2L and U2R).
  
- **Binary + Multi-class Approach:**  
  To preserve high accuracy for normal traffic, a two-phase approach was adopted:
  1. **Binary Classification:** Detect if an instance is an attack or normal.
  2. **Multi-class Classification:** For the attack instances, determine the specific type of attack.
  
### Evaluation Metrics

The models were evaluated using multiple metrics:
- **Accuracy**
- **Precision, Recall, Fnt (MCC)**

These metr
(more details in the jupyter notebook file)ics provided a comprehensive view of model performance, especially in the context of imbalanced classes.

---

## Results & Findings

- **Baseline Model:**  
  The initial 5-class classification model showed very high overall accuracy dominated by the 'normal' class. However, performance on smaller attack classes (especially U2R and R2L) was suboptimal.
  
- **Balanced Weights Variation:**  
  Incorporating balanced weights significantly improved the detection accuracy for smaller classes, albeit with a slight reduction in overall performance on the normal class.
  
- **Binary + Multi-class Approach:**  
  This approach further enhanced the
eu**d in the final repor**t, demonstrating that ensemble methods (Random Forest) were particularly effective in handling the imbalan & Usage

### Prerequisites

- **Python 3.7+**
- **Jupyter Notebook / JupyterLab**
- The following Python packages (see `requirements.txt` for detailsp and run the file.

----End to model evaluation and conclusions. For more detailed insights, refer to the Jupyter Notebook and the final report PDF.

---

*Generated based on project artifacts and findings from the provided materials citeturn0file0.*