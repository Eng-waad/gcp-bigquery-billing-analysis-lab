# gcp-bigquery-billing-analysisi-lab
Hands-on Google Cloud BigQuery lab for importing, querying, and analyzing billing data using SQL.
# GCP BigQuery Billing Data Analysis Lab

##  Project Overview
This project demonstrates how to use Google BigQuery to import, query, and analyze cloud billing data.

The lab was completed as part of a hands-on Google Cloud training (Qwiklabs), focusing on real-world data analysis using SQL on a large dataset.

---

##  Tools & Technologies
- Google Cloud Platform (GCP)
- BigQuery
- Cloud Storage
- SQL

---

##  Dataset Information
- Dataset Name: `billing_dataset`
- Table Name:Query Billing Data - Source: Google Cloud Storage (AVRO file)
- Total Records: Overview
This pro
---

##  Tasks Performed

###  Task 1: Data Import
- Created a BigQuery dataset
- Configured dataset location (US) and table expiration
- Imported billing data from Cloud Storage
- Used AVRO format for automatic schema detection

---

###  Task 2: Data Exploration
- Inspected table schema (strings, integers, timestamps, floats)
- Verified dataset size and structure
- Confirmed total number of rows

---

###  Task 3: Basic Query

```sql
SELECT * 
FROM: `billing_dataset`
- Table Name: `WHERE Cost > 0;

Result: 104 rows with cost greater than 0

 Task 4: Advanced Analysis

🔹 Top Product by Number of Records

SELECT 
  service.description, 
  COUNT(*) AS billing_records
FROMed as part of a hands-on Google CloGROUP BY service.description
ORDER BY billing_records DESC;

Result: Compute Engine (281,136 records)

🔹 Most Expensive Product (Total Cost)

SELECT 
  service.description, 
  ROUND(SUM(cost), 2) AS total_cost
FROMn Google Cloud training (Qwiklabs),GROUP BY service.description
ORDER BY total_cost DESC;

Result: Compute Engine ($2548.77)

🔹 Most Common Billing Unit

SELECT 
  usage.unit, 
  COUNT(*) AS billing_records
FROMlab was completed as part of a handWHERE cost > 0
GROUP BY usage.unit
ORDER BY billing_records DESC;

Result: Byte-seconds

🔹 Records with Cost Greater Than $1

SELECT 
  service.description, 
  COUNT(*) AS billing_records
FROMd as part of a hands-on Google ClouWHERE cost > 1
GROUP BY service.description
ORDER BY billing_records DESC;

Result: Cloud SQL has the highest number of records with cost greater than $1

Key Learnings
 • Importing structured data into BigQuery from Cloud Storage
 • Writing SQL queries to analyze billing data
 • Filtering and aggregating large datasets
 • Extracting insights from cloud cost data

Notes

This project demonstrates practical experience with BigQuery and cloud billing analysis, which are essential skills for cloud engineers and data analysts
