# Datacleaning#
🚀 Data Cleaning with PySpark

This project showcases how to clean and preprocess a dataset using **Apache Spark (PySpark)** — a powerful big data engine. It includes handling of **missing values**, **removal of duplicate records**, and outputs summary statistics before and after cleaning.

---

## 📦 Dataset Used

### `trip_data.csv`

A sample trip dataset containing:

| trip_id | origin        | destination   | distance_km | passenger_count |
|---------|---------------|---------------|-------------|-----------------|
| 1       | New York      | Boston        | 350         | 2               |
| 2       | San Francisco | Los Angeles   |             |                 |
| 3       | New York      | Boston        | 350         | 2               |
| 4       | Chicago       |               | 800         | 3               |
| 5       | Miami         | Orlando       | 380         |                 |
| 6       | Dallas        | Houston       | 390         | 4               |

---

## 🧪 Features

- ✅ Load CSV dataset with header and schema inference
- 🗑️ Remove duplicate entries using `dropDuplicates()`
- ❌ Identify missing/null values per column
- 💧 Drop rows containing any null values using `dropna()`
- 📉 Display row counts before and after cleaning

---

## 🧠 Technologies Used

- Apache Spark
- PySpark (Python API for Spark)

---

## 🛠️ Project Files

pyspark-data-cleaning/
├── trip_data.csv # Sample input data
├── data_cleaning_trip_pyspark.py # Python script with PySpark logic
├── README.md # Project documentation

yaml
Copy code

---

## 📜 Script Overview: `data_cleaning_trip_pyspark.py`

```python
spark = SparkSession.builder.appName("Trip Data Cleaning").getOrCreate()
df = spark.read.csv("trip_data.csv", header=True, inferSchema=True)
df_cleaned = df.dropDuplicates().dropna()
df_cleaned.show()
spark.stop()
▶️ How to Run the Script
💻 If using CLI with spark-submit:
bash
Copy code
spark-submit data_cleaning_trip_pyspark.py
📓 If using Jupyter/Colab:
Install PySpark:

bash
Copy code
pip install pyspark
Then run the code block by block.

📊 Output Summary
Duplicates Removed: Trip ID 3 was a duplicate of ID 1

Missing Values Handled: Rows with missing distance or passenger count were dropped

Cleaned Rows: Only fully complete records retained

trip_id	origin	destination	distance_km	passenger_count
1	New York	Boston	350	2
6	Dallas	Houston	390	4

🧑‍💻 Author
Mohan Reddy Krishna T

📝 License
This project is open-source and available for academic and learning purposes.
