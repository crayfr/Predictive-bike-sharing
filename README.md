# Scalable Bike Demand Prediction & Analysis  

A scalable data engineering and machine learning project focused on urban mobility analytics and bike-sharing demand forecasting. Built with PySpark, the pipeline is designed to handle large-scale datasets efficiently, moving beyond single-node processing limitations.

---

## 🚀 Project Overview  

This repository implements an end-to-end distributed pipeline based on the UCI Bike Sharing Dataset.  
The dataset is treated as a virtual urban sensor network, where each rental record reflects real-time mobility behavior.

The workflow is divided into two core phases:

### 1️⃣ Exploratory Data Analysis (EDA)  
- Seasonal demand patterns  
- Weather impact analysis  
- Hourly and daily usage distribution  
- Data validation and cleaning  

### 2️⃣ Machine Learning Engineering  
- Feature engineering with Spark  
- Model training using Spark MLlib  
- Hyperparameter tuning and evaluation  
- Comparative benchmarking (Linear Regression, Random Forest, GBT)  

---

## 🛠️ Tech Stack  

- **Language:** Python 3.x  
- **Distributed Framework:** PySpark (Spark SQL & MLlib)  
- **Storage Format:** Apache Parquet (columnar, schema-aware, optimized I/O)  
- **Visualization:** Matplotlib, Seaborn  
- **Local Data Handling:** Pandas (used only for controlled sampling and visualization)  

---

## 📊 Data Engineering Highlights  

This implementation emphasizes engineering robustness rather than purely notebook-based analysis:

- **Distributed Processing:** Full transformation pipeline built on Spark DataFrames  
- **Optimized Storage Layer:** Intermediate datasets stored in Parquet for performance and schema consistency  
- **Production-Style ML Pipelines:** Use of `pyspark.ml.Pipeline` integrating:
  - `StringIndexer`  
  - `OneHotEncoder`  
  - `VectorAssembler`  
- **Feature Vectorization at Scale:** Fully distributed feature transformation workflow  
- **Automated KPI Extraction:** Lightweight ETL step exporting business-ready CSV reports  
- **Modular Architecture:** Clear separation between EDA, feature engineering, and modeling logic  

---

## 📁 Repository Structure  

    ├── data/                       
    ├── notebooks/
    │   ├── 01_EDA_Bike_Sharing.ipynb
    │   └── 02_Modeling_Bike_Sharing.ipynb
    ├── output/                     
    ├── .gitignore                  
    ├── README.md
    └── requirements.txt            

---

## 📈 Key Insights (Automated KPIs)

- **Total Rentals:** ~3.29M rides recorded  
- **Peak Hours:** Strong demand spikes at 08:00 and 17:00 (commute-driven behavior)  
- **Weather Sensitivity:**  
  - High temperature → ~263 rentals/hour  
  - Low temperature → ~77 rentals/hour  
- **Seasonality Effect:** Summer and Fall generate the highest cumulative rental volumes  

---

## ⚙️ Setup & Installation  

### Prerequisites  
- Java 8 / 11 / 17 (required for Spark runtime)

### Install Dependencies  

```bash
pip install -r requirements.txt
```

### Execution Order  

1. Run `01_EDA_Bike_Sharing.ipynb` (data cleaning + transformation)  
2. Run `02_Modeling_Bike_Sharing.ipynb` (model training + evaluation)  
