# HR Analytics Data Platform (Azure)

End-to-end data engineering project that builds an HR analytics platform using Azure services and the **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline ingests HR datasets, performs data cleaning and sentiment analysis, and exposes curated datasets for analytics and reporting.

---

## Project Architecture

Data flows through multiple Azure services to build a scalable analytics pipeline.

```
GitHub (CSV Data)
      ↓
Azure Data Factory
      ↓
Azure Data Lake Storage (Bronze / Silver / Gold)
      ↓
Azure Databricks (Data Cleaning + Sentiment Analysis)
      ↓
Azure Synapse Serverless SQL
      ↓
Power BI (Planned Dashboards)
```

---

## Tech Stack

| Service | Purpose |
|------|------|
| Azure Data Factory | Pipeline orchestration |
| Azure Data Lake Gen2 | Data storage |
| Azure Databricks | Data transformation and NLP |
| Azure Synapse Serverless | Query layer and analytics views |
| Python (NLTK VADER) | Sentiment analysis |
| Power BI | Visualization (planned) |

---

## Medallion Architecture

### Bronze Layer (Raw Data)

Stores raw HR datasets ingested from GitHub.

Datasets:

- employees.csv
- headcount_snapshot.csv
- terminations.csv
- exit_interviews.csv
- engagement_survey.csv

Loaded using **ADF Copy Activity**.

---

### Silver Layer (Cleaned Data)

Processed using **Databricks notebooks**.

Transformations include:

- schema validation
- null handling
- duplicate removal
- data type standardization
- sentiment analysis using **NLTK VADER**

Output datasets:

- employees
- headcount_snapshot
- terminations
- exit_interviews_sentiment
- engagement_survey_sentiment

Stored as **Parquet files** in ADLS.

---

### Gold Layer (Analytics Data)

Curated datasets generated using **Synapse Serverless SQL** and **CETAS**.

Analytics views include:

- `vw_attrition_analysis`
- `vw_exit_sentiment`
- `vw_engagement_by_department`
- `vw_engagement_trend`
- `vw_headcount_trend`

These datasets are optimized for BI reporting.

---

## Azure Data Factory Pipeline

Pipeline workflow:

```
ForEach (GitHub Files)
        ↓
Copy Activity (Load Bronze)
        ↓
Databricks Notebook (Bronze → Silver)
        ↓
Databricks Notebook (Sentiment Analysis)
        ↓
Synapse Script Activity (Create Gold Tables)
```

---

## Example Analytics

The platform enables insights such as:

- Employee attrition analysis
- Exit interview sentiment analysis
- Workforce headcount trends
- Employee engagement trends
- Department-level engagement comparison

---

## Storage Structure

```
ADLS Container: hrdatalake

Bronze/
    raw HR CSV files

Silver/
    cleaned parquet datasets

Gold/
    curated analytics datasets
```

