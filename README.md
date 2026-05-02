# 🔍 Fraud & Anomaly Detection in Digital Payment Transactions

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

> A statistical approach to detecting anomalous transactions in India's UPI (Unified Payments Interface) digital payment ecosystem using IQR-based outlier detection.

---

## 👥 Team 9

| Name | Registration No. |
|------|-----------------|
| N Shreyaa | RA2311003010309 |
| Khande Hemanth Abhay | RA2311003010347 |
| Arpita Salee | RA2311003010361 |
| Siddhartt Kumaran | RA2311003010362 |

---

## 📌 Overview

Digital payment systems like India's **Unified Payments Interface (UPI)** process millions of transactions daily. As usage scales, so do fraud risks. This project builds a robust pipeline to **detect anomalous and potentially fraudulent transactions** using statistical methods applied to real-world UPI app data from 2021.

---

## 🎯 Objectives

- Analyze transaction **volume and value patterns** across UPI banks and applications
- Detect outliers using the **Interquartile Range (IQR)** method
- Visualize anomalies to make them interpretable and actionable
- Improve data quality through rigorous **preprocessing and cleaning**

---

## 📂 Dataset

| Property | Details |
|----------|---------|
| **Source** | [Kaggle – UPI Apps Transactions in 2021](https://www.kaggle.com/datasets/ramjasmaurya/upi-apps-transactions-in-2021) |
| **Records** | 654 rows |
| **Coverage** | All 12 months of 2021 across multiple UPI banks/apps |

### Columns

| Column | Description |
|--------|-------------|
| `UPI Banks` | Payment bank or app name |
| `Volume (Mn) By Customers` | No. of transactions by customers (in millions) |
| `Value (Cr) by Customers` | Transaction value by customers (in crores) |
| `Volume (Mn)` | Total transaction volume (in millions) |
| `Value (Cr)` | Total transaction value (in crores) |
| `Month` | Month of record (1–12) |
| `Year` | Year of record |

---

## 🗂️ Project Structure

```
├── Data_Science_Team_9.ipynb      # Main Jupyter Notebook
├── README.md                      # Project documentation
└── UPI apps transaction data in 2021.csv   # Dataset (downloaded via Kaggle API)
```

---

## 🔧 Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, cleaning, and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Base plotting |
| `seaborn` | Statistical visualizations |
| `kaggle` | Dataset download via Kaggle API |

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn kaggle
```

### 3. Download the Dataset

Set up your Kaggle API credentials, then run:

```bash
kaggle datasets download -d ramjasmaurya/upi-apps-transactions-in-2021
unzip upi-apps-transactions-in-2021.zip
```

### 4. Launch the Notebook

```bash
jupyter notebook Data_Science_Team_9.ipynb
```

---

## 📊 Methodology

### Data Preprocessing
- Handled missing values and removed duplicate records
- Combined `Month` and `Year` into a unified `Date` column for time-series analysis
- Verified and corrected data types for accurate numerical operations

### Anomaly Detection — IQR Method

```
Q1  = 25th percentile of Value (Cr)
Q3  = 75th percentile of Value (Cr)
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR

Anomaly = Value < Lower Bound OR Value > Upper Bound
```

### Visualizations
- **Histogram** — Distribution of transaction values (with KDE)
- **Boxen Plot** — Extended quartile view of transaction values
- **Bar Chart** — Bank-wise total transaction values
- **Boxplot with Anomaly Markers** — Explicit outlier highlighting
- **Scatter Plot (Value vs Date)** — Temporal distribution of anomalies
- **Dual Histogram** — Normal vs. anomalous transaction comparison

---

## 📈 Key Findings

- The distribution of `Value (Cr)` is **heavily right-skewed** — most transactions are low value, with rare high-value outliers
- Anomalous transactions represent a **small percentage** of total records but account for a **disproportionately large share** of total transaction value
- Certain UPI banks appear more frequently in anomalous records, suggesting they either handle higher-value transactions or are more exposed to irregularities
- Anomalies are distributed across the year, with possible seasonal concentration during peak transaction months

---

## 🔮 Future Work

- Implement advanced ML-based anomaly detection (e.g., **Isolation Forest**, **One-Class SVM**, **Autoencoders**)
- Incorporate **bank-specific thresholds** for more nuanced detection
- Extend analysis to multi-year data for longitudinal trend analysis
- Build a **real-time anomaly detection pipeline** using streaming data

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- Dataset by [ramjasmaurya on Kaggle](https://www.kaggle.com/datasets/ramjasmaurya/upi-apps-transactions-in-2021)
- National Payments Corporation of India (NPCI) for UPI infrastructure context
- SRM Institute of Science and Technology — Data Science coursework
