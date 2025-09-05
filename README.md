# DA5401 Assignment 2: PCA, Visualization & Logistic Regression (Mushroom Dataset)

**Author:** BASAVARAJ A NADUVINAMANI  
**Roll Number:** DA25C005  
**Course:** DA5401  
**Last Edited:** 2025-09-05  

---

## Overview

This repository contains the analysis of the **Mushroom Dataset** to predict edibility (Edible vs. Poisonous) using **Principal Component Analysis (PCA)** and **Logistic Regression**. The analysis includes:

- Data preprocessing and one-hot encoding of categorical features  
- Dimensionality reduction using PCA  
- Visualization of feature distributions, scree plots, and PCA projections  
- Classification using Logistic Regression with performance evaluation  
- Insights on physical and environmental features affecting mushroom edibility  

---

## Dataset

- Source: [UCI Mushroom Dataset](https://www.kaggle.com/uciml/mushroom-classification)  
- Shape: 8124 rows × 23 columns  
- Features: All categorical, no missing values  
- Target: `class` (Edible or Poisonous)  

---

## Methodology

### 1. Data Preprocessing
- Applied **mapping dictionaries** to convert categorical codes to meaningful names  
- **One-hot encoding** applied to prepare data for PCA  
- Standardization ensures PCA treats all features equally  

### 2. Dimensionality Reduction (PCA)
- PCA applied to reduce feature redundancy while preserving variance  
- Scree plots and cumulative variance plots used to determine **optimal number of components**  
- First 59 principal components retain ≥95% variance  

### 3. Classification
- **Logistic Regression** trained on original and PCA-transformed data  
- Evaluated using **accuracy, precision, recall, F1-score, and confusion matrices**  

---

## Key Findings

- **High Separability:** Certain features almost perfectly separate edible and poisonous mushrooms  
- **Dimensionality Reduction Impact:** Test Accuracy on PCA-transformed features = 0.9992 (original = 1.0)  
- **Feature Insights:**  
  - Bruising, spore print color, ring type, cap size, stalk thickness, and cap color are strong predictors  
  - Habitat and growth pattern also impact edibility  
- **Multifactor Evaluation:** No single feature guarantees safety; multiple traits should be considered  

---

## Results (PCA-transformed Data)

| Class      | Precision | Recall | F1-Score | Support |
|------------|-----------|--------|----------|---------|
| Edible     | 1.00      | 1.00   | 1.00     | 1263    |
| Poisonous  | 1.00      | 1.00   | 1.00     | 1175    |
| **Accuracy** |           |        | 1.00     | 2438    |
| **Macro Avg** | 1.00      | 1.00   | 1.00     | 2438    |
| **Weighted Avg** | 1.00      | 1.00   | 1.00     | 2438    |

> Logistic Regression achieves **near-perfect performance** even after PCA, confirming minimal information loss.

---

## Visualizations

- **Categorical Feature Distributions:** Countplots for all features by class  
- **Scree Plot:** Explained variance and cumulative variance for principal components  
- **PCA Projections:** 2D and 5D pairplots for PCA-transformed data  
- **Confusion Matrices:** Original and PCA-transformed datasets  

---

## Insights & Safety Patterns

- **Bruising:** Mushrooms that bruise are predominantly safe  
- **Spore Print:** Black, brown, or white spore prints indicate higher edibility  
- **Ring Type:** Pendant rings → safer, Large rings → dangerous  
- **Cap and Stalk Size:** Broader caps and thicker stalks usually safer  
- **Habitat & Growth:** Open areas and scattered/solitary growth indicate lower toxicity  
- **Takeaway:** Accurate classification requires **multiple trait evaluation**; no single characteristic guarantees safety  

---

## Tools & Libraries

- Python 3.x  
- `pandas`, `numpy`, `matplotlib`, `seaborn`  
- `scikit-learn` (PCA, StandardScaler, LogisticRegression, train_test_split, metrics)  

---
## Folder Structure

- **DA5401_A2_Mushroom_Analysis/**
  - **notebooks/**
    - `DA5401_A2_Mushroom_Analysis.ipynb` → Main Jupyter notebook
  - `README.md` → Project documentation
  - **scripts/**
    - `data_preprocessing.py` → Optional Python scripts
  - **plots/**
    - `scree_plot.png`
    - `pca_2d.png`
    - `pca_pairplot.png` → Optional saved visualizations
  - **data/**
    - `mushrooms.csv` → Dataset file (if included)

> **Notes:**  
> - `notebooks/` contains all Jupyter notebooks for analysis  
> - `scripts/` holds any standalone Python scripts  
> - `plots/` stores all visualization images  
> - `data/` keeps the raw or processed dataset

## Conclusion

PCA effectively **reduces dimensionality and redundancy** without sacrificing predictive performance. Logistic Regression retains near-perfect accuracy on PCA-transformed features. Integrating physical and environmental features allows for **informed predictions** on mushroom edibility, highlighting the importance of **multi-trait evaluation** and expert validation.

