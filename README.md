# E-Commerce User Behavior Analysis Pipeline
> **Big Data Project: Conversion Funnel & Promotional Effect Optimization**

An end-to-end big data engineering project demonstrating a complete ETL pipeline. The project processes ~100,000 user behavior records using the Hadoop ecosystem and generates business insights via Python visualizations.


## 🛠️ Technical Stack
* **Storage:** Hadoop HDFS (Pseudo-distributed mode)
* **Warehousing:** Apache Hive (SQL-on-Hadoop)
* **Analytics:** Python 3.12 (Pandas, Seaborn, Matplotlib)
* **Environment:** Windows 11 + WSL2 (Ubuntu 24.04)

---

## 📂 Project Structure
* `sql/`: Hive DDL scripts for table creation and data cleaning.
* `scripts/`: Python visualization scripts.
* `images/`: System screenshots of Hadoop/Hive environment.
* `images generated using python/`: Final analytical charts.
* `data_samples/`: Representative samples of raw CSV data.

---

## 🏛️ Data Engineering & Warehousing

### 1. HDFS Storage
Raw data (`d3.csv` and `d5.csv`) is stored in a distributed file system.
* **Items path:** `/project/items/`
* **Behaviors path:** `/project/behaviors/`

### 2. Hive ETL Pipeline
I implemented **External Tables** to maintain data persistence. The pipeline includes:
* **Cleaning:** Standardizing time fields and promotional status.
* **Joins:** Merging behavior logs with product metadata for comprehensive analysis.

---

## 📊 Business Insights & Visualizations

The following insights were derived using a custom Python analytics engine:

### User Conversion Funnel
Identifies the "drop-off" points in the customer journey from exposure to final payment.
![User Conversion Funnel](images%20generated%20using%20python/funnel_bar.png)

### Category Distribution
Displays user interaction levels across various product segments (e.g., Food, Clothing, Electronics).
![Product Category Distribution](images%20generated%20using%20python/category_bar.png)

### Promotional Effect Heatmap
Compares behavior patterns between items with active promotions vs. standard items.
![Promotion vs Non-Promotion](images%20generated%20using%20python/promo_heatmap.png)

---

## 🔧 Environment Setup & Troubleshooting
Key challenges resolved in the **WSL2** environment:
* **Hadoop Configuration:** Resolved startup failures caused by Windows hostname conflicts by binding to `localhost`.
* **Metadata Initialization:** Fixed Hive metastore issues by clearing the Derby database.
* **Query Optimization:** Utilized `EXPLAIN` plans to verify query execution logic on a single-node cluster.

---

## 🚀 Optimization Recommendations
* **Funnel Bottleneck:** Analysis indicates a high loss rate at the "Add-to-Cart" stage.
* **Strategy:** Implementing small-value incentives and optimizing the add-to-cart guidance button is expected to increase final conversion by ~15%.
