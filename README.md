# HR Workforce Analytics Platform

This project builds a data platform that helps HR teams analyze workforce trends, employee engagement, and attrition patterns using modern cloud data technologies.

The goal is to transform raw HR datasets into structured insights that support workforce planning, employee retention strategies, and organizational performance analysis.

---

## Business Problem

HR departments collect large volumes of employee data such as headcount records, termination information, engagement surveys, and exit interviews.  
However, this data is often fragmented across different systems and difficult to analyze.

This project creates a centralized analytics platform that enables HR teams to answer questions such as:

- How is workforce headcount changing over time?
- Which departments experience the highest attrition?
- What sentiments do employees express during exit interviews?
- How does engagement vary across departments?
- Are there early signals that indicate potential turnover?

---

## Key HR Insights Generated

The platform produces several analytics datasets that HR teams can use for decision making:

- **Employee Attrition Analysis**  
  Understand which teams or roles experience higher turnover.

- **Exit Interview Sentiment**  
  Analyze employee feedback to identify recurring concerns.

- **Engagement by Department**  
  Compare employee engagement scores across teams.

- **Engagement Trend Analysis**  
  Track changes in employee satisfaction over time.

- **Workforce Headcount Trend**  
  Monitor hiring and workforce growth patterns.

---

## Data Processing Approach

To transform raw HR data into usable analytics datasets, the platform uses a layered data architecture.

### Bronze Layer – Raw HR Data

Raw HR datasets are ingested from source files and stored without modification.

Examples of datasets:

- Employee records
- Workforce headcount snapshots
- Termination records
- Exit interview feedback
- Employee engagement survey results

---

### Silver Layer – Cleaned and Enriched Data

Data is cleaned and standardized to ensure it is reliable for analysis.

Processing includes:

- schema validation
- missing value handling
- duplicate removal
- consistent data formats
- enrichment of HR datasets

Additionally, **sentiment analysis** is applied to employee feedback to classify responses as positive, neutral, or negative.

---

### Gold Layer – HR Analytics Datasets

Curated datasets are created to support HR reporting and dashboards.

Examples include:

- Attrition analysis datasets
- Exit interview sentiment insights
- Department engagement metrics
- Workforce growth trends

These datasets are optimized for visualization and reporting tools such as Power BI.

---

## Technology Used

The platform is implemented using cloud data engineering tools:

| Technology | Purpose |
|------|------|
| Azure Data Factory | Data ingestion and pipeline orchestration |
| Azure Data Lake Storage | Centralized data storage |
| Azure Databricks | Data transformation and sentiment analysis |
| Azure Synapse Serverless SQL | Analytical query layer |
| Python (NLTK VADER) | Sentiment analysis |
| Power BI | HR dashboards (planned) |

---

## Data Flow

The data pipeline moves HR data through several processing stages.

```
HR Data Sources
      ↓
Azure Data Factory
      ↓
Azure Data Lake (Raw Data)
      ↓
Data Cleaning and Enrichment
      ↓
Sentiment Analysis on Employee Feedback
      ↓
Curated HR Analytics Datasets
      ↓
Business Intelligence Dashboards
```

---

## Example Use Cases

This platform enables HR teams to:

- identify departments with rising attrition risk
- understand employee sentiment from exit interviews
- monitor workforce growth across time
- analyze engagement trends across the organization
- support leadership decisions with data driven insights

---

