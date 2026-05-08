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


# Module 1: Data Loading & Schema Handling

## Task 1: Load CSV Files into PySpark DataFrames

### Datasets Loaded
- full_grouped.csv
- covid_19_clean_complete.csv
- country_wise_latest.csv
- day_wise.csv
- usa_county_wise.csv
- worldometer_data.csv

### Concepts Practiced
- `spark.read.csv()`
- `inferSchema=True`
- `header=True`
- `printSchema()`
- `count()`

### Objectives
- Infer schemas automatically
- Validate dataset structure
- Count records
- Handle headers correctly

---

# Module 2: Data Cleaning Tasks

## Task 2: Handle Missing Province/State Values

### Dataset
`covid_19_clean_complete.csv`

### Operations
- Detect null Province/State values
- Replace missing values with `"Unknown"`

### Concepts
- `isNull()`
- `fillna()`
- Filtering

---

## Task 3: Standardize Country Names

### Example Fixes
- US → USA
- Korea → South Korea

### Concepts
- `when()`
- `regexp_replace()`
- Data normalization

---

## Task 4: Remove Duplicate Daily Records

### Duplicate Criteria
- Country
- Date

### Concepts
- `dropDuplicates()`

---

# Module 3: Aggregation Tasks

## Task 5: Top 10 Countries by Confirmed Cases

### Dataset
`country_wise_latest.csv`

### Output
| Country | Confirmed |
|---|---|

### Concepts
- `orderBy()`
- `limit()`

### Visualization
- Bar Chart

---

## Task 6: Top 10 Countries by Death Rate

### Formula

```text
Death Rate = (Deaths / Confirmed Cases) × 100
```

### Visualization
- Horizontal Bar Chart

---

## Task 7: WHO Region-wise Analysis

### Metrics
- Total confirmed
- Total deaths
- Total recovered

### Grouping
- WHO Region

### Concepts
- `groupBy()`
- `agg()`

### Visualization
- Pie Chart
- Stacked Bar Chart

---

# Module 4: Time-Series Analysis

## Task 8: Daily Global New Cases Trend

### Dataset
`day_wise.csv`

### Metrics
- Date
- New Cases

### Visualization
- Line Chart

---

## Task 9: Daily Global Death Growth Trend

### Formula

```text
(new_deaths / previous_day_deaths) × 100
```

### Concepts
- Window functions
- `lag()`

### Visualization
- Line Chart

---

## Task 10: Monthly COVID Case Growth

### Dataset
`full_grouped.csv`

### Concepts
- `month()`
- `groupBy()`

### Visualization
- Monthly Trend Chart

---

# Module 5: Window Function Tasks

## Task 11: Top 5 Countries per WHO Region

### Concepts
- `Window.partitionBy()`
- `dense_rank()`

### Objective
Rank countries by confirmed cases within each WHO region.

### Visualization
- Grouped Bar Chart

---

## Task 12: Country-wise Daily Case Increase

### Formula

```text
today_confirmed - yesterday_confirmed
```

### Concepts
- `lag()`
- Partition windows

### Visualization
- Country Trend Chart

---

# Module 6: Join Operations

## Task 13: Compare Latest Dataset Sources

### Datasets Joined
- country_wise_latest.csv
- worldometer_data.csv

### Comparisons
- Confirmed cases
- Deaths
- Recoveries

### Objective
Identify mismatches between data sources.

### Concepts
- `join()`
- Calculated columns

---

## Task 14: Population vs Total Cases

### Formula

```text
infection_rate = (TotalCases / Population) × 100
```

### Visualization
- Scatter Plot
- Bar Chart

---

# Module 7: Geographic Analysis

## Task 15: USA State-wise Case Distribution

### Dataset
`usa_county_wise.csv`

### Grouping
- Province_State

### Objective
Count counties reported per state.

### Visualization
- US Map
- Bar Chart

---

## Task 16: Latitude-Longitude Case Clusters

### Dataset
`covid_19_clean_complete.csv`

### Features
- Latitude
- Longitude
- Confirmed Cases

### Visualization
- Geo Scatter Plot

---

# Module 8: Advanced Analytical Tasks

## Task 17: Recovery Rate Analysis

### Formula

```text
(Recovered / Confirmed) × 100
```

### Objectives
- Best recovery countries
- Worst recovery countries

### Visualization
- Bar Chart

---

## Task 18: Active Case Burden Analysis

### Objective
Find countries where:

```text
Active Cases > Recovered Cases
```

### Output
- High-risk countries list

---

## Task 19: Pandemic Peak Detection

### Objectives
Identify dates where:
- New cases were maximum
- New deaths were maximum

### Visualization
- Peak markers on trend charts

---

# Module 9: Feature Engineering

## Task 20: Severity Category Creation

### Categories

| Category | Confirmed Cases |
|---|---|
| Low | < 10K |
| Medium | 10K–100K |
| High | 100K–1M |
| Critical | > 1M |

### Concepts
- `when()`

### Visualization
- Pie Chart

---

# Module 10: Final Analytics Pipeline

## Task 21: Build Complete COVID Analytics Pipeline

### Pipeline Steps

### Step 1
Extract all datasets

### Step 2
Clean missing values

### Step 3
Standardize columns

### Step 4
Join datasets

### Step 5
Generate analytics tables:
- Top countries
- Region summary
- Daily trends
- Mortality report
- Recovery report

### Step 6
Export outputs as:
- Parquet
- CSV

### Step 7
Use outputs for dashboards and visualization

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
