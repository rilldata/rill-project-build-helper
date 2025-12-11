# [Ingesting Data](https://docs.rilldata.com/build/connectors/data-source)

Rill previously used the concept of sources, but that terminology has been deprecated. However, we still organize these files into a dedicated folder to visually separate data-source models from intermediate models.

Rill supports two categories of data ingestion:

## 1. DuckDB-Backed Direct Ingestion

Defined with: driver: duckdb

These ingestion paths are natively supported by DuckDB and allow Rill to read data directly at query time or through managed ingestion:

- GCS
- S3
- Azure Blob Storage
- HTTPS endpoints
- Local files (CSV, Parquet, JSON, etc.)

## 2. Rill Ingestion

Non-DuckDB drivers include:

- BigQuery
- Redshift
- Athena
- MySQL
- Postgres
- Snowflake

Rill ingestion:
- Executes SQL queries against your warehouse or database
- Materializes results into your OLAP engine
- Supports partitioning, incremental refresh, and scheduling

## [Partitioning, Incremental Ingestion](https://docs.rilldata.com/build/models/incremental-partitioned-models), and [Refresh Schedules](https://docs.rilldata.com/build/models/data-refresh)

Rill supports incremental, partition-aware ingestion, which:

- Avoids expensive full table scans
- Reduces warehouse compute and data transfer
- Enables high-frequency refresh schedules
- Automatically detects updated partitions
- Allows reprocessing of old partitions when needed

See gcs_clickhouse_commits.yaml for a full example of:
- Partition definitions
- Incremental logic
- Scheduling
- Partition path templates

Example logs:
```
INFO    Resolved model partitions       {"model": "gcs_clickhouse_commits", "partitions": 12}
```