# Grocery Sales ETL Pipeline using Databricks & PySpark

## Project Description

This project demonstrates the development of a complete ETL pipeline for grocery sales data using Databricks, PySpark, and Delta Lake.

The objective of the pipeline is to transform raw retail datasets into structured and analytics-ready datasets by implementing the Medallion Architecture, which consists of Bronze, Silver, and Gold layers.

The processed data can be used for retail analytics, demand analysis, and sales forecasting by generating useful business features such as sales trends, promotion effects, and holiday demand patterns.

---

## Dataset Information

**Source:** Kaggle – Store Sales Time Series Forecasting

The dataset contains historical grocery sales records from Corporación Favorita, a major grocery retailer in Ecuador.

### Files used in the project

| File | Description |
|-----|-------------|
| train.csv | Historical product sales |
| stores.csv | Store metadata |
| transactions.csv | Daily customer transactions |
| holidays_events.csv | Holiday and event information |
| oil.csv | Historical oil prices |

These datasets together simulate a real-world retail analytics scenario.

---

## System Architecture

The project follows a data lake architecture where raw data is processed and refined in multiple stages.

```
Kaggle Dataset
      ↓
AWS S3 Data Lake
      ↓
Databricks ETL Processing
      ↓
Bronze Layer (Raw Data)
      ↓
Silver Layer (Processed Data)
      ↓
Gold Layer (Analytics Ready Data)
```

Each layer improves the quality and usability of the data.

---

## Medallion Architecture

### Bronze Layer – Raw Data Storage

The Bronze layer contains the original data in its raw format as received from the source.

#### Purpose

- Preserve original datasets
- Maintain data lineage
- Enable traceability of transformations

#### Tables

```
raw.sales_transactions
raw.stores
raw.transactions
raw.holidays
raw.oil_prices
```

#### Operations Performed

- CSV file ingestion
- Initial schema validation
- Metadata recording

---

### Silver Layer – Data Cleaning & Integration

The Silver layer processes the raw data to produce clean and standardized datasets.

#### Key Transformations

- Removing duplicate records
- Correcting data types
- Handling missing values
- Joining sales data with store metadata
- Integrating transaction data
- Extracting date-based features

#### Output Table

```
processed.sales_cleaned
```

---

### Gold Layer – Analytics Ready Data

The Gold layer prepares the data for business analytics and forecasting tasks.

#### Generated Features

- Weekly sales summaries
- Promotion performance metrics
- Holiday impact indicators
- Store level performance metrics
- Product family sales trends

#### Output Table

```
analytics.sales_forecast_features
```

---

## Project Directory Structure

```
grocery-sales-etl
│
├── ingestion
│   └── bronze_ingestion.py
│
├── transformations
│   └── silver_transformation.py
│
├── analytics
│   └── gold_features.py
│
├── utils
│   └── data_validation.py
│
├── configs
│
├── workflows
│   └── main_pipeline.py
│
├── requirements.txt
└── README.md
```

---

## ETL Pipeline Workflow

The pipeline is executed in a sequence of stages.

```
Bronze Ingestion
        ↓
Silver Data Processing
        ↓
Gold Feature Generation
        ↓
Main Pipeline Execution
```

The `main_pipeline.py` script coordinates the entire workflow.

---

## Technologies Used

- Python
- PySpark
- Databricks
- Delta Lake
- AWS S3
- Git & GitHub

These tools enable scalable data processing and modern data lake architecture implementation.

---

## Setup and Installation

### Clone the repository

```bash
git clone https://github.com/Manojmd1/grocery-sales-etl-P2_Databricks.git
cd grocery-sales-etl
```

### Install required dependencies

```bash
pip install -r requirements.txt
```

---

## Running the ETL Pipeline

To execute the pipeline locally, run:

```bash
python main_pipeline.py
```

Pipeline stages executed:

1. Data ingestion into the Bronze layer  
2. Data cleaning and integration in the Silver layer  
3. Feature generation and aggregation in the Gold layer  

---

## Business Insights Enabled

The processed datasets allow several useful analyses.

### Sales Trend Analysis
Understanding weekly and seasonal variations in product demand.

### Store Performance Evaluation
Identifying stores with the highest revenue generation.

### Product Category Insights
Finding product families with high customer demand.

### Promotion Impact Analysis
Measuring the effect of promotional campaigns on sales.

### Holiday Sales Patterns
Analyzing how holidays influence purchasing behavior.

### Customer Activity Analysis
Studying the relationship between store transactions and product sales.

---

## Future Improvements

Possible extensions to this project include:

- Real-time data ingestion pipelines
- Machine learning based sales forecasting models
- Interactive dashboards using Power BI or Tableau
- Automated data quality monitoring systems

---

## License

This project has been created for learning and research purposes.

---

## Project Contributors
- Manoj M D
- Suhas S Chauhan
- Rahul Garg    
- Revanth Sai Arcot  
- Bhaskar Rao Kodimela  

---

## GitHub

https://github.com/Manojmd1
