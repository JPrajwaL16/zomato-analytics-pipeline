# Zomato Bangalore Restaurant Analytics Pipeline

## Project Overview
End to end data engineering pipeline that ingests, 
cleans and analyzes 51,000+ Zomato restaurant records 
from Bangalore using PySpark and Delta Lake on 
Azure Databricks.

## Architecture
Kaggle API -> Pandas Ingestion -> PySpark Cleaning
-> Delta Lake (Silver) -> Gold Aggregations -> Insights


## Medallion Architecture
| Layer  | Description            |  Format           |
|--------|------------------------|-------------------|
| Bronze | Raw CSV ingestion      | Pandas DataFrame  |
| Silver | Cleaned and typed data | Delta Lake Table  | 
| Gold   | Business aggregations  | Delta Lake Table  |

## Technologies Used
- Apache Spark (PySpark)
- Delta Lake
- Azure Databricks (Free Edition)
- Kaggle API
- Python (Pandas)
- SQL

## Key Insights Generated
- Top 10 Bangalore locations by restaurant rating
- Most popular cuisines and their avg cost
- Lavelle Road = highest rated area (4.14 avg)
- North Indian = most popular cuisine (2158 restaurants)

## Dataset
- Source: Kaggle (Zomato Bangalore Restaurants)
- Raw rows: 51,717
- Clean rows after processing: 41,665
- Columns: 12

## Pipeline Notebooks
|     Notebook      |      Description      |
|-------------------|-----------------------|
| 01_bronze_ingest  | Kaggle API ingestion  |
| 02_silver_clean   | PySpark data cleaning |
| 03_gold_aggregate | Business insights     |

## Data Cleaning Steps
- Removed corrupted CSV rows
- Cleaned rate column (removed "/5" suffix)
- Fixed approx_cost (removed commas, cast to integer)
- Dropped unnecessary columns (url, phone, reviews)
- Handled null values in key columns

## How to Run
1. Sign up at community.cloud.databricks.com
2. Set up Kaggle API token
3. Run notebooks in order (01 -> 02 -> 03)
