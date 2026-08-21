# NYC Taxi Big Data Pipeline: 2015 vs 2025 🚕 

##  Project Overview
This project demonstrates a **Big Data Batch Processing** pipeline built with **Apache Spark (PySpark)**. The objective was to process and analyze over **195 million rows** of NYC Taxi & Limousine Commission (TLC) trip records to extract business insights regarding the impact of ride-sharing apps over the last decade.

Traditional libraries like Pandas fail to process datasets of this magnitude on a local machine due to RAM limitations (Out-Of-Memory errors). This project successfully implements a distributed computing architecture to handle gigabytes of highly compressed data.

##  Tech Stack
* **Language:** Python 3.10+
* **Big Data Engine:** Apache Spark (PySpark 4.0+)
* **Environment:** Jupyter Notebook
* **Data Formats:** Parquet (Columnar storage for Big Data), CSV
* **Concepts:** Distributed Computing, Lazy Evaluation, Schema Evolution, Joins, Aggregations, Memory Tuning.

##  Architecture & Data Flow
1. **Source:** Official NYC TLC Trip Record Data (Yellow Taxi). Over 195 million records spanning 2015 and 2025.
2. **Ingestion:** Loading highly compressed Parquet files and a CSV dimensional lookup table.
3. **Processing:** 
   * Calculating trip duration from Unix timestamps.
   * Filtering out anomalies (negative fares, zero-minute trips, invalid locations).
   * Joining large fact tables (Parquet) with dimension tables (CSV) to resolve Zone IDs.
4. **Aggregations:** Grouping data to extract market trends (average tips, total rides, average fares by Borough).
5. **Storage:** Exporting the cleaned, 45M+ row 2025 dataset back to optimal **Parquet** format, and the aggregated business report to **CSV** for stakeholder consumption.

##  Key Business Findings (The 10-Year Trend)
By comparing the 2015 and 2025 datasets (approx. 195 million combined records), the PySpark pipeline revealed:
* **The Fall of Yellow Cabs:** Total trips plummeted from **145.7M (2015)** to just **45.2M (2025)** — a nearly 70% market share loss, highlighting the rise of ride-sharing alternatives (Uber/Lyft) and post-pandemic remote work trends.
* **Fare & Tip Inflation:** The average fare increased from `$12.94` to `$20.19`, while average tips nearly doubled from `$1.73` to `$3.01`.
* **Manhattan Monopoly:** In 2025, Manhattan accounted for **38.9M** of the 45M total trips, proving that Yellow Taxis have become a highly localized service.

##  How to Run Locally
1. Clone the repository:
   ```bash
   git clone [https://github.com/kamilbigaj/NYC-Taxi-Big-Data-PySpark.git](https://github.com/kamilbigaj/NYC-Taxi-Big-Data-PySpark.git)
