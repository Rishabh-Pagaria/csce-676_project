# CDC 500 Cities Health Burden Analysis  
CSCE 676 – Data Mining Project  

## Overview

This project explores public health patterns across U.S. census tracts using the **CDC 500 Cities: Local Data for Better Health (2019 Release)** dataset.

The objective is to analyze structural relationships among health indicators, identify latent health burden factors, and prepare the data for clustering, anomaly detection, and spatial analysis.

This repository currently contains the full Exploratory Data Analysis (EDA) phase of the project.

---

## Dataset

**Source:**  
CDC Open Data Portal  
https://data.cdc.gov/500-Cities-Places/500-Cities-Local-Data-for-Better-Health-2019-relea/6vp6-wxuq/about_data  

**Dataset Characteristics:**

- Geographic level: Census Tract  
- Year analyzed: 2017  
- Measures: 20 health indicators  
- ~27,000 census tracts  
- Publicly available  

The dataset includes chronic disease prevalence, behavioral risk factors, and preventive care indicators.

---

## Project Structure
csce-676_project/
│
├── notebooks/
│ └── Project Checkpoint 1.ipynb
│
├── README.md

## Methods (EDA Phase)

The following analytical steps were performed:

### 1. Data Cleaning & Validation
- Schema validation with assertions
- Identifier normalization (tract FIPS handling)
- Missingness analysis
- Controlled dataset slicing (Census Tract, Crude Prevalence, 2017)

### 2. Feature Engineering
- Pivot to tract × measure matrix
- Median imputation (if needed)
- Standardization (z-score normalization)

### 3. Distribution Analysis
- Histogram analysis of prevalence measures
- Identification of skewness and heavy tails
- Outlier structure assessment

### 4. Correlation Analysis
- Correlation matrix computation
- Identification of strong multicollinearity (r > 0.9)
- Evidence of latent cardio-metabolic burden factor

### 5. Principal Component Analysis (PCA)
- Dimensionality reduction
- 4 principal components explain >90% variance
- Confirmation of structural redundancy among measures

---

## Key Findings

- Chronic disease indicators (diabetes, stroke, kidney disease, coronary heart disease, hypertension) are highly correlated.
- PCA reveals strong latent structure in the data.
- Only four principal components explain over 90% of total variance.
- Evidence suggests the presence of a dominant cardio-metabolic health burden gradient across census tracts.
- Some measures exhibit heavy-tailed distributions, motivating anomaly detection in future steps.

---

## Next Steps

The next phases of the project will include:

- K-Means clustering on PCA-reduced data (Course Technique)
- Anomaly detection for high-risk tracts (Course Technique)
- Spatial autocorrelation analysis (Moran’s I) to examine geographic clustering (Beyond-Course Technique)

---

## Technologies Used

- Python 3
- pandas
- NumPy
- scikit-learn
- matplotlib

---

## Reproducibility

The dataset is downloaded directly from the CDC Open Data API using Socrata paging to ensure reproducibility.

All preprocessing steps include assertions to validate structural correctness and prevent silent data corruption.

---

## Author

Rishabh Pagaria  
Master’s Student – Computer Science  
Texas A&M University  
