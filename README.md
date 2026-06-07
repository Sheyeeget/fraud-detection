# Fraud Detection for E-commerce and Bank Transactions

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

## 📋 Project Overview

This project implements a comprehensive fraud detection system for two distinct transaction streams:

- **E-commerce transactions** - Rich user behavioral context (device, browser, geolocation, signup patterns)
- **Bank credit card transactions** - Anonymized PCA features for privacy protection

The system is designed to:
- **Reduce false positives** - Legitimate transactions flagged as fraud (customer frustration)
- **Minimize false negatives** - Missed fraudulent transactions (direct financial loss)
- **Provide explainability** - SHAP-based interpretations for regulatory compliance

## 🎯 Business Impact

| Metric | Target | Business Value |
|--------|--------|----------------|
| False Positive Rate | < 1% | Customer trust & retention |
| False Negative Rate | < 5% | Fraud loss prevention |
| Fraud Detection Rate | > 95% | Revenue protection |

## 🏗️ Project Structure
fraud-detection/
│
├── .github/
│ └── workflows/
│ └── unittests.yml # CI/CD pipeline
│
├── data/
│ ├── raw/ # Original datasets (gitignored)
│ │ ├── Fraud_Data.csv
│ │ ├── IpAddress_to_Country.csv
│ │ └── creditcard.csv
│ │
│ └── processed/ # Cleaned & engineered features
│ ├── fraud_enriched.csv
│ ├── fraud_with_geolocation.csv
│ ├── creditcard_enriched.csv
│ ├── creditcard_standard_scaled.csv
│ └── creditcard_robust_scaled.csv
│
├── notebooks/ # Jupyter notebooks
│ ├── eda-fraud-data.ipynb # E-commerce EDA
│ ├── eda-creditcard.ipynb # Credit card EDA
│ ├── feature-engineering-ecommerce.ipynb # Feature engineering
│ ├── creditcard-preprocessing.ipynb # Credit card preprocessing
│ └── geolocation-analysis.ipynb # IP-to-country mapping
│
├── src/ # Reusable Python modules
│ ├── init.py
│ ├── feature_engineering.py # Feature engineering functions
│ ├── imbalance_handler.py # SMOTE & resampling utilities
│ └── utils.py # Helper functions
│
├── models/ # Saved model artifacts
│ ├── scaler_ecommerce.pkl
│ ├── scaler_creditcard_standard.pkl
│ └── scaler_creditcard_robust.pkl
│
├── tests/ # Unit tests
│ ├── init.py
│ ├── test_imports.py
│ └── test_feature_engineering.py
│
├── scripts/ # Utility scripts
│ ├── download_data.py
│ └── run_notebooks.py
│
├── requirements.txt # Python dependencies
├── .gitignore # Git ignore rules
└── README.md # This file


## 🚀 Quick Start

### Prerequisites

- **Python 3.8, 3.9, or 3.10** (3.11+ may have compatibility issues)
- **Git** for version control
- **4GB+ RAM** recommended for processing

### Installation

#### 1. Clone the repository

```bash
git clone https://github.com/Sheyeeget/fraud-detection.git
cd fraud-detection