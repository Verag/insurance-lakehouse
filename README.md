# NFIP Insurance Lakehouse

> A modern **Insurance Data Lakehouse** solution built with Databricks, Delta Lake, and PySpark. This project ingests public National Flood Insurance Program (NFIP) datasets, applies data quality validations under the **Medallion Architecture**, and exposes analytical datasets for reporting and business intelligence.

---

## Architecture Overview

The pipeline implements the **Medallion Architecture** to ensure data lineage, governance, and progressive data quality enrichment:

```text
[ Raw Data / NFIP ] 
       │
       ▼
 BRONZE LAYER      ──► Raw data ingestion (Schema-on-read, Delta Lake format)
       │
       ▼
 VALIDATION LAYER  ──► Data Quality (DQ) validation rules & anomaly detection
       │
       ▼
 SILVER LAYER      ──► Cleaned, deduplicated, and standardized datasets
       │
       ▼
 GOLD LAYER        ──► Business aggregations, KPIs, and dimensional models
       │
       ▼
 REPORTING / BI    ──► Executive dashboards & analytical reporting (Power BI)
