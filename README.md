# COVID-19 Data Analytics Pipeline Using PySpark

An end-to-end big data analytics pipeline built using PySpark to analyze global COVID-19 trends from multiple real-world datasets. The project demonstrates large-scale data ingestion, cleaning, transformation, aggregation, time-series analysis, window functions, joins, feature engineering, and exporting analytical datasets for visualization dashboards.

---

# Project Overview

This project focuses on building a scalable COVID-19 analytics workflow using PySpark and Spark SQL. Multiple datasets containing country-wise, region-wise, global, and geographic COVID-19 statistics are processed to generate meaningful insights for reporting and decision-making.

The pipeline simulates a real-world analytics engineering workflow involving:

- Data ingestion
- Schema validation
- Data cleaning
- Missing value handling
- Duplicate removal
- Standardization
- Aggregation and KPI generation
- Time-series analytics
- Window function analysis
- Multi-dataset joins
- Feature engineering
- Exporting analytics datasets

The final outputs can be visualized using:
- Matplotlib
- Plotly
- Tableau
- Power BI

---

# Business Problem Statement

During the COVID-19 pandemic, governments and healthcare organizations required reliable analytics such as:

- Which countries were most affected?
- Which WHO regions recovered fastest?
- When did global cases peak?
- Which countries had the highest active case burdens?
- How did population impact infection spread?

Since the datasets exist across multiple sources with varying formats and granularity, organizations require a scalable analytics pipeline capable of cleaning, transforming, and analyzing large-scale pandemic data efficiently.

---

# Tech Stack

| Technology | Purpose |
|---|---|
| PySpark | Large-scale distributed data processing |
| Spark SQL | Analytical queries |
| Python | Additional scripting |
| Parquet / CSV | Data storage |
| Matplotlib / Plotly | Visualization |
| Tableau / Power BI | Dashboard creation |

---

# Dataset Source

Dataset Link:  
https://www.kaggle.com/datasets/imdevskp/corona-virus-report

---

# Datasets Used

| Dataset | Description |
|---|---|
| full_grouped.csv | Daily country-level COVID trends |
| covid_19_clean_complete.csv | Historical location-level data |
| country_wise_latest.csv | Latest country statistics |
| day_wise.csv | Global daily trends |
| usa_county_wise.csv | US county-level statistics |
| worldometer_data.csv | Population and global COVID statistics |

---

# Deliverables

## Candidates Should Submit

### PySpark Scripts / Notebooks
- Data ingestion
- Cleaning
- Transformations
- Analytics

### Output Datasets
- Cleaned datasets
- Aggregated datasets
- Parquet files
- CSV exports

### Visualizations
Using:
- Matplotlib
- Plotly
- Power BI
- Tableau

### Final Report
Including insights such as:
- Highest death rate countries
- Fastest recovering WHO regions
- Pandemic peak periods
- Countries with strong recovery performance

---

# Key PySpark Concepts Practiced

| Concept | Usage |
|---|---|
| DataFrames | Structured big data processing |
| Spark SQL | Analytical queries |
| Window Functions | Time-series analytics |
| Aggregations | KPI generation |
| Joins | Multi-dataset analysis |
| Feature Engineering | Severity categorization |
| Exporting | CSV and Parquet generation |

---

# Learning Outcomes

By completing this project, you will gain:

- Hands-on experience with PySpark
- Real-world data engineering skills
- Expertise in large-scale data cleaning
- Time-series analytical skills
- Window function implementation knowledge
- Multi-dataset join operations
- Scalable analytics pipeline development
- Dashboard-ready dataset generation

---

# How to Run

## Install Dependencies

```bash
pip install pyspark matplotlib plotly pandas
```

---

## Start PySpark

```bash
pyspark
```

---

## Run Pipeline

```bash
python pipeline.py
```

---

# Sample Insights

## Top Affected Countries

```text
1. USA
2. Brazil
3. India
4. Russia
5. South Africa
```

## Highest Recovery WHO Region

```text
South-East Asia
```

## Pandemic Peak

```text
Peak Global Cases:
2020-07-24
```

---

# Future Enhancements

- Real-time streaming analytics
- Machine learning forecasting
- Vaccination trend analysis
- Interactive dashboards
- Cloud deployment using Spark clusters
- Apache Airflow orchestration

---
