# MTNBCPred: Prediction of Metastasis in Triple Negative Breast Cancer Patients

## Overview

MTNBCPred is a transcriptomics-based machine learning framework developed for predicting lymph node metastasis in Triple Negative Breast Cancer (TNBC) patients using gene expression profiles.

The study focuses on identifying diagnostic biomarkers capable of distinguishing:

- Metastatic TNBC patients
- Non-metastatic TNBC patients

The system uses transcriptomic signatures along with machine learning techniques for prediction and prognostic assessment.

---

# Background

Triple Negative Breast Cancer (TNBC) is one of the most aggressive breast cancer subtypes and is associated with:

- High metastatic potential
- Increased recurrence
- Poor prognosis
- Lack of targeted therapies

Unlike other breast cancer types, TNBC lacks:

- Estrogen Receptor (ER)
- Progesterone Receptor (PR)
- HER2 receptor

Because of this, early prediction of lymph node metastasis becomes critically important for treatment planning and survival improvement.



---

# Objectives

The major objectives of this work were:

- Identify transcriptomic biomarkers for TNBC metastasis
- Develop machine learning models for lymph node metastasis prediction
- Evaluate biomarkers across multiple transcriptomic platforms
- Perform prognostic survival analysis
- Develop a publicly accessible prediction server


---

# Dataset Information

## TCGA Dataset

The study used transcriptomic data from TCGA consisting of:

| Dataset Type | Number of Samples |
|---|---|
| Metastatic TNBC | 53 |
| Non-metastatic TNBC | 104 |
| Total Samples | 157 |

Independent validation datasets were obtained from GEO using:

- Affymetrix platform
- Illumina platform
- Agilent platform

:contentReference[oaicite:2]{index=2}

---

# Data Preprocessing

The following preprocessing techniques were applied:

## RNA-Seq Data

- CPM normalization using edgeR TMM method
- log2 CPM transformation using limma voom()

## Microarray Data

- Background correction
- Quantile normalization
- log2 transformation

:contentReference[oaicite:3]{index=3}

---

# Differential Gene Expression Analysis

After preprocessing:

- 20,531 genes were initially analyzed
- Low variance genes were removed
- 17,297 genes remained for further analysis

## Differentially Expressed Genes (DEGs)

| Type | Number |
|---|---|
| Upregulated genes | 643 |
| Downregulated genes | 367 |
| Total DEGs | 1010 |

:contentReference[oaicite:4]{index=4}

---

# Top 15 Gene Signatures

The top 15 genes were selected using logistic regression ranking based on prediction performance.

## Upregulated Genes

- DHRS7
- BAIAP3
- ZNRF2
- ETFDH
- HBG1
- RIOK2
- TCEAL4
- TCF21
- FRZB

## Downregulated Genes

- POU4F1
- COL24A1
- TRPA1
- IBSP
- VIL1
- PSAT1



---

# Single Gene Biomarkers

The best-performing single gene biomarkers were:

| Gene | AUC |
|---|---|
| DHRS7 | 0.689 |
| ZNRF2 | 0.689 |

These genes showed balanced sensitivity and specificity for LN-TNBC prediction.



---

# Machine Learning Models

The following machine learning classifiers were implemented:

- Gaussian Naive Bayes (GNB)
- Logistic Regression (LR)
- Random Forest (RF)
- Decision Tree (DT)
- Support Vector Classifier (SVC)
- K-Nearest Neighbors (KNN)
- eXtreme Gradient Boosting (XGB)



---

# Best Prediction Model

The Gaussian Naive Bayes (GNB) classifier achieved the best performance using the 15-gene signature.

## Performance on Validation Dataset

| Metric | Value |
|---|---|
| Sensitivity | 75.00 |
| Specificity | 79.17 |
| Accuracy | 78.12 |
| AUC | 0.81 |
| MCC | 0.50 |



---

# Cross-Validation Strategy

The dataset was split using:

- 80% training dataset
- 20% validation dataset

A 5-fold cross-validation strategy was applied for robust model evaluation.



---

# Cross-Platform Validation

The model was validated on multiple GEO microarray datasets.

However, performance decreased significantly across different platforms due to opposite gene regulation trends.

## Key Observation

Some genes were:

- Upregulated in TCGA
- Downregulated in GEO datasets

This highlighted challenges in cross-platform transcriptomic validation.

---

# Prognostic Biomarkers

## Poor Prognostic Markers

The following genes were associated with poor survival:

| Gene | Hazard Ratio |
|---|---|
| ZNRF2 | 2.711 |
| FRZB | 2.395 |
| TCEAL4 | 2.254 |

## Good Prognostic Markers

The following genes were associated with better survival:

| Gene | Hazard Ratio |
|---|---|
| PSAT1 | 0.41 |
| TRPA1 | 0.329 |
| VIL1 | 0.217 |

---

# Biological Insights

Enrichment and interaction analysis showed involvement of selected genes in:

- Neurotransmitter transport regulation
- Cell differentiation
- Osteoblast signaling
- Interleukin-11 signaling
- Serine metabolism
- Vitamin B6 metabolism



---

# Web Server Features

The MTNBCPred webserver contains:

## Prediction Module

Allows users to:

- Upload expression profiles
- Predict metastatic status
- Identify LN-metastatic or non-metastatic TNBC

## Analysis Module

Allows:

- Single gene analysis
- Biomarker investigation
- Expression-based interpretation


---

# Clinical Significance

The study demonstrated that:

- Transcriptomic biomarkers can predict TNBC metastasis
- Clinical factors like tumor stage and lymph node status strongly affect prognosis
- Machine learning models can assist in early metastasis prediction
- Cross-platform variability remains a major challenge



---

# Technologies Used

- Transcriptomics
- Machine Learning
- Logistic Regression
- Gaussian Naive Bayes
- Random Forest
- Support Vector Classifier
- Python sklearn
- R Bioconductor
- Survival Analysis
- t-SNE Visualization

---

# Conclusion

MTNBCPred provides a machine learning-based framework for predicting lymph node metastasis in Triple Negative Breast Cancer patients using transcriptomic signatures.

The study identified:

- 15-gene diagnostic biomarkers
- Prognostic survival markers
- Cross-platform validation challenges

The developed model achieved strong performance on TCGA datasets and provides a useful resource for TNBC metastasis prediction research.


---

# Contact

## Prof. G. P. S. Raghava

Email: raghava@iiitd.ac.in

Address:  
Indraprastha Institute of Information Technology Delhi

---

# License

This project is intended for academic and research purposes only.
