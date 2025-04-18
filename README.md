
# 📊 Scaler Learner Profiling & Clustering Analysis

## 🧠 Problem Statement

Scaler is a tech-versity offering industry-aligned programs in Data Science and Computer Science. As part of the Analytics team, the goal is to profile learners and cluster them based on their **job profile, company, compensation, and experience**, allowing Scaler to:

- Identify top job roles and companies
- Recommend ideal job paths for learners
- Understand compensation trends across clusters

---

## 📁 Dataset Description

- **File Name:** `scaler_kmeans.csv`
- **Size:** Anonymized dataset containing learner employment data

### 🔑 Data Dictionary:

| Column Name         | Description |
|---------------------|-------------|
| `Unnamed: 0`        | Index column |
| `Email_hash`        | Anonymized learner email (PII) |
| `Company_hash`      | Anonymized company identifier |
| `orgyear`           | Employment start year |
| `CTC`               | Current annual compensation |
| `Job_position`      | Learner's job designation |
| `CTC_updated_year`  | Last year when CTC was updated |

---

## 🔍 Objectives

- Clean, prepare, and engineer features from the raw dataset
- Perform **manual clustering** based on Company, Job Position, and Years of Experience
- Apply **unsupervised learning** techniques like KMeans and Hierarchical Clustering
- Extract actionable insights for learner-job-company profiling

---

## 🔧 Steps Performed

### 1. 🧹 Data Cleaning
- Handled missing values using **KNN/Mean imputation**
- Removed special characters using **regex**:  
  ```python
  import re
  re.sub('[^A-Za-z0-9 ]+', '', mystring)
  ```
- Removed duplicate records
- Converted columns to appropriate data types

### 2. 🛠 Feature Engineering
- **Years of Experience**:  
  `Current Year - orgyear`
- **Manual Clustering Flags**:
  - `designation`: Flag [1,2,3] based on CTC vs peers in the same company, role, and experience
  - `Class`: Flag [1,2,3] based on job role and company-level comparison
  - `Tier`: Flag [1,2,3] based on company-level CTC comparison

### 3. 📊 Manual Insights Extracted
- **Top 10 Tier 1 employees**
- **Top & Bottom performers in Data Science per company**
- **Best companies by average CTC**
- **Best job positions per company**
- **Top 10 employees with 5/6/7 years experience in each job role/company**

---

## 📈 Unsupervised Learning: Clustering

### ✅ Preprocessing
- **Label Encoding** for categorical columns
- **Standardization** using `StandardScaler`

### 🔄 Clustering Techniques
- **Clustering Tendency Check** (Hopkins Statistic)
- **Elbow Method** to identify optimal number of clusters (K)
- **KMeans Clustering**
- **Hierarchical Clustering** (sampled dataset if needed)

