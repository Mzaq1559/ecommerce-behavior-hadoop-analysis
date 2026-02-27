# E-Commerce User Behavior Analysis Pipeline
> **Big Data Project: Conversion Funnel & Promotional Effect Optimization**

An end-to-end big data engineering project demonstrating a complete ETL pipeline. The project processes ~100,000 user behavior records using the Hadoop ecosystem and generates business insights via Python visualizations.



---

## 🏛️ Data Engineering & Warehousing

### 1. Environment & Cluster Status
The project runs on a pseudo-distributed Hadoop cluster. Services are monitored via the HDFS Web UI and JPS command to ensure data node health.

![HDFS Web UI Status](images/4.png)
*Monitoring the Hadoop cluster via the Web Interface (Port 9870)*

### 2. Distributed Storage (HDFS)
Raw data (`d3.csv` and `d5.csv`) is partitioned into HDFS directories to facilitate parallel processing.

![HDFS File System](images/11.png)
*Visualizing the file hierarchy within HDFS*

### 3. Hive Schema & ETL
I implemented **External Tables** to decouple data storage from the Hive metastore. This ensures data persistence even if tables are dropped.

![Hive Table Creation](images/2.png)
*Defining the schema for e-commerce behavior logs*

---

## 📊 Business Insights & Visualizations

Using Python's Seaborn and Matplotlib libraries, I transformed processed Hive data into actionable charts.

### 1. Conversion Funnel Analysis
This chart identifies the "drop-off" points in the customer journey. The analysis shows a significant bottleneck at the **Add-to-Cart** stage.

![User Conversion Funnel](python_images/funnel_analysis.png)

### 2. Category Distribution
Understanding which product segments drive the most engagement.

![Product Category Distribution](python_images/category_bar.png)

### 3. Promotional Effect Heatmap
Comparing behavior patterns between promoted and non-promoted items to evaluate marketing ROI.

![Promotion vs Non-Promotion](python_images/promo_heatmap.png)

### Analytical Logic (Python)
The backend processing utilizes a dedicated virtual environment to manage dependencies and execute visualization scripts.

![Python Script Execution](images/12.png)
*Snippet of the visualization logic and environment setup*

---

## 🔧 Troubleshooting & Problem Solving
* **WSL2 Configuration:** Resolved hostname parsing errors by binding Hadoop services to `localhost`.
* **Hive Optimization:** Used `EXPLAIN` plans to verify query execution paths for join operations.
* **Metadata Repair:** Fixed metastore corruption by re-initializing the Derby database.

---

## 🚀 Optimization Recommendations
* **Funnel Bottleneck:** Analysis indicates a high loss rate at the "Add-to-Cart" stage.
* **Strategy:** Implementing small-value incentives (coupons) and optimizing the add-to-cart guidance button is expected to increase final conversion by ~15%.
