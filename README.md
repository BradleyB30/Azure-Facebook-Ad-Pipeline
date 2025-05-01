# Azure Ad Performance Data Pipeline

This project is an end-to-end ETL pipeline built using **Azure Databricks** and **Azure Blob Storage**. It processes raw Facebook Ad data, computes key marketing KPIs (CTR, CPC), and stores results in a structured **bronze-silver-gold** architecture.

---

## 🔧 Tools Used

- **Azure Blob Storage** – Cloud storage for raw, cleaned, and aggregated data
- **Azure Databricks** – Spark-based distributed compute for transformation
- **PySpark** – Data cleaning, enrichment, and aggregation
- **Bronze-Silver-Gold Architecture** – Data engineering best practice for organizing ETL layers

---

## 📊 Project Flow

### 1. **Bronze Layer** – Raw data ingestion  
Raw `facebook_ads.csv` is uploaded to the `bronze` container in Azure Blob Storage.

### 2. **Silver Layer** – Clean & Enrich  
- Data types are cast (e.g., impressions, clicks, spend)
- CTR and CPC are computed using PySpark
- Cleaned data is written to the `silver` container

### 3. **Gold Layer** – Aggregate  
- Data is grouped by `campaign_id`
- Aggregated metrics like total clicks, impressions, spend, CTR, and CPC are calculated
- Results are written to the `gold` container as `summary_ads.csv`

---

## 📁 Folder Structure

