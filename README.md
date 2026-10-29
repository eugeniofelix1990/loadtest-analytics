# loadtest-analytics

Automated data pipeline and analytics suite for load-test performance logs, featuring p95/p99 latency tracking, advanced SQL window functions, and data quality checks to drive engineering decisions.

## 1. Business Question / Objective
Evaluate API performance degradation, latency distribution (p95/p99), and throughput bottlenecks under simulated concurrent load using relational database queries and analytical data pipelines.

## 2. Methodology
- **Load Generation (`loadtests/`):** Simulating concurrent traffic via k6 / JMeter scripts.
- **Data Ingestion & Storage (`src/`, `sql/`):** Loading raw CSV logs into relational databases (SQLite / PostgreSQL) with immutable raw layers.
- **Data Quality (`tests/`):** Automated `pytest` suites validating schema integrity, null values, and metric ranges.
- **SQL Analytics (`sql/`):** Utilizing Window Functions (`RANK`, `LAG`), aggregations (`GROUP BY`), and regression comparisons.
- **Visualization (`notebooks/`, `reports/figures/`):** Exporting key performance charts directly to the repository.

## 3. Project Structure
- `loadtests/`: Performance test scripts generating raw logs.
- `data/raw/`: Immutable raw log samples.
- `data/processed/`: Cleaned datasets (git-ignored).
- `sql/`: Sequentially ordered DDL and analytical SQL queries.
- `src/`: Data ingestion, cleaning, and transformation pipelines.
- `tests/`: Pytest checks for pipeline and data quality.
- `notebooks/`: Exploratory Jupyter notebook.
- `reports/figures/`: Exported visualization charts.
