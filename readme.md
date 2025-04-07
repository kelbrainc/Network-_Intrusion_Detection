----Start

**Network Intrusion Detection**
This repository contains a machine learning project focused on detecting network intrusions using the NSL-KDD dataset. The work combines extensive exploratory data analysis (EDA), feature engineering, and model evaluation using several classification methods.


**Table of Contents**
- Overview
- Methodology
  - Data Pre-processing & EDA
  - Feature Engineering & Selection
  - Dimensionality Reduction and Interpretability
  - Modeling Approaches
  - Evaluation Metrics
- Results & Findings
- Installation & Usage


**Overview**
This project aims to develop an effective Intrusion Detection System (IDS) using machine learning techniques. By leveraging the NSL-KDD dataset—an improved version of the original KDD'99 dataset—the study assesses network traffic and detects various types of cyber attacks. The primary objectives include:
- **Exploratory Analysis:** Understanding the structure, distribution, and relationships within the data.
- **Feature Engineering:** Refining and selecting key features to improve model performance.
- **Modeling:** Implementing baseline and enhanced classification models (including Logistic Regression, Decision Trees, and Random Forests) for both multi-class and binary + multi-class detection.
- **Interpretability:** Using PCA for dimensionality reduction and SHAP values for feature importance analysis.


**Dataset**
The project uses the **NSL-KDD dataset**, which contains:
- **125,973 records** in the training set with 41 features and 1 label.
- A mix of numerical (float64, int64) and categorical (object) variables.
- Labels that initially include 23 distinct classes (various network attack types), later consolidated into five classes (normal plus four types of attacks).

The dataset is important for developing an IDS capable of handling imbalanced data, where the majority of network traffic is benign, and the attack types are under-represented.


**Methodology**
### Data Pre-processing & EDA

- **Data Integrity Checks:**  
  Verified that there are no missing or duplicate values.
  
- **Exploratory Data Analysis:**  
  Visualized the distribution of features, identified 23 distinct labels, and examined the balance between normal traffic and attack types.
  
- **Handling Mixed Data Types:**  
  Separated numeric features from categorical ones, ensuring that subsequent correlation analysis and model training are performed on the correct data types.

### Feature Engineering & Selection

- **Label Consolidation:**  
  Reduced the original 23 labels into 5 consolidated classes (one normal and four attack types) to simplify the classification task.
  
- **Rare Service Handling:**  
  Rare values in categorical features (such as 'service') were grouped to avoid overfitting.
  
- **Feature Scaling:**  
  Applied standard scaling to numeric features to normalize their distributions.
  
- **Feature Selection:**  
  Removed highly correlated, constant, or quasi-constant features to reduce dimensionality and improve model robustness.

### Dimensionality Reduction and Interpretability

- **Principal Component Analysis (PCA):**  
  Applied PCA for visualization purposes. The scatter plots of the first two principal components illustrated the overlap among classes, highlighting the classification challenges.
  
- **SHAP Analysis:**  
  Used SHAP values to identify the most important features influencing the model predictions. Notably, features like `source_bytes` were found to be highly influential.

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
- **Precision, Recall, F1 Score**
- **Cohen’s Kappa**
- **Log Loss and Zero-One Loss**
- **Hamming Loss**
- **Matthews Correlation Coefficient (MCC)**


## Results & Findings

(more details in the jupyter notebook file)
- **Baseline Model:**  
  The initial 5-class classification model showed very high overall accuracy dominated by the 'normal' class. However, performance on smaller attack classes (especially U2R and R2L) was suboptimal.
  
- **Balanced Weights Variation:**  
  Incorporating balanced weights significantly improved the detection accuracy for smaller classes, albeit with a slight reduction in overall performance on the normal class.
  
- **Binary + Multi-class Approach:**  
  This approach further enhanced the classification accuracy, achieving nearly 100% accuracy for normal traffic and very high precision, recall, and F1 scores for the attack classes.


**Installation & Usage**

### Prerequisites

- **Python 3.7+**
- **Jupyter Notebook / JupyterLab**
- The following Python packages
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - seaborn
  - SHAP
  - yellowbrick

### Installation

You can install the required packages using pip and run the file.

----End
