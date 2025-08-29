# 🛒 Brazilian E-Commerce BIG DATA ENGINEERING & EXPLORATORY DATA ANALYSIS (EDA) with PySpark on GCP Dataproc  

This project is a **complete big data pipeline** implemented using **Apache Spark (PySpark)** on **Google Cloud Dataproc** with **HDFS** and **Jupyter Notebook**.  
The analysis is based on the [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data?select=olist_geolocation_dataset.csv).  

The goal is to demonstrate scalable **data ingestion, cleaning, transformation, integration, optimization, and serving** of large-scale e-commerce data.  

---

## 📂 Dataset Used  
The dataset contains multiple interconnected CSV files with details about:  
- 📦 Orders & items  
- 👥 Customers  
- 🏬 Sellers  
- 📍 Geolocation  
- 💳 Payments  
- ⭐ Reviews  

---

## 🧩 Project Modules  

### 1️⃣ Data Ingestion & Exploration (HDFS)  
- Ingest datasets into **HDFS**.  
- Explore schema, data quality, and distributions.  

### 2️⃣ Data Cleaning & Transformation  
- **Identify data quality issues**.  
- Handle missing values:  
  - Drop missing values (non-critical columns).  
  - Fill missing values (numerical columns).  
  - Impute missing values (continuous data).  
- **Standardize formats** (date, categorical).  
- **Correct datatypes** where required.  
- **Deduplicate** to remove redundancy.  
- **Transform data** for downstream tasks.  
- **Store cleaned data in Parquet** for efficient querying.  

### 3️⃣ Data Integration & Aggregation  
- Join multiple datasets efficiently.  
- Apply optimized join strategies:  
  - Broadcast joins  
  - Sort-merge joins  
  - Skew join handling  
  - Bucket joins  
- Aggregate data for key insights.  
- Use **caching & query optimization** for performance.  

### 4️⃣ Performance Optimization  
- **Cluster Resources (Dataproc):**  
  - Master: `n2-standard-4` (4 vCPUs, 16 GB RAM, 32GB disk)  
  - Workers (2x): `n2-standard-4` (4 vCPUs, 16 GB RAM, 64GB disk each)  
  - Total: 8 worker vCPUs, ~32 GB RAM (excluding master)  
- **Dataproc Features Disabled:**  
  - No autoscaling, Metastore, advanced execution layer, or advanced optimizations.  
- **Storage:** `pd-balanced` (non-SSD → I/O optimization critical).  
- **Networking:** Internal IP enabled.  
- **Optimization Strategy:**  
  - Tune shuffle partitions, broadcast join threshold, and storage persistence.  
  - Adjust parallelism for 2 workers × 4 cores.  
  - Avoid excessive caching due to disk-based storage.  

### 5️⃣ Data Serving & Visualization  
- Make processed datasets available for consumption.  
- Export transformed data to external systems or databases.  
- Build visualizations and identify trends (customer behavior, sales, delivery times, payments).  

---

## ⚡ Key Features  
- ✅ Distributed data processing with **Spark on Dataproc**  
- ✅ Clean, standardized, and integrated datasets stored in **Parquet**  
- ✅ Optimized joins & queries for performance  
- ✅ Scalable cluster-based processing with resource tuning  
- ✅ End-to-end workflow from **raw data → insights → serving**  

---

## 📊 Example Insights  
- 📍 Most orders come from **São Paulo (SP)**.  
- 💳 **Credit card** is the dominant payment method.  
- ⏱️ Average delivery time varies across states.  
- ⭐ Review scores are strongly linked to delivery delays.  

---

## 🏗️ Tech Stack  
- **Google Cloud Dataproc** – Managed Spark & Hadoop cluster  
- **HDFS** – Distributed file storage  
- **Apache Spark (PySpark)** – Big data processing  
- **Python** – Scripting & logic  
- **Pandas / Matplotlib / Seaborn** – Additional analysis & visualization  
- **Jupyter Notebook (on Dataproc)** – Development & interactive execution  

---

## 🚀 How to Run  
1. Clone the repository:  
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```
2. Upload datasets to **Google Cloud Storage (GCS)**.  
3. Create a **Dataproc Cluster** with HDFS.  
4. Open **Jupyter Notebook** on Dataproc and run the provided notebooks step by step.  

---

## 📌 Future Improvements  
- Apply **MLlib models** to predict delivery delays & review scores.  
- Deploy processed data to **BigQuery** for analytics.  
- Build dashboards with **Power BI / Tableau**.  
- Automate workflows using **Airflow / Prefect**.  

---

## 🤝 Contributions  
Contributions are welcome! Fork the repo, raise issues, or open pull requests to improve the pipeline.  
