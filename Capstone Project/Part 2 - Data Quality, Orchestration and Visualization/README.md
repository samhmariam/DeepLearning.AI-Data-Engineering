# Part 2 - Data Quality, Orchestration, and Visualization

## Overview

This project extends the DeFtunes data engineering pipeline by enhancing it with automated data quality checks, orchestration, and visualization capabilities. Building on the ETL and data modeling pipeline from Part 1, the goal is to ensure data reliability, automate workflows, and create insightful dashboards for business stakeholders.

Key objectives:
- Integrate robust data quality checks throughout the pipeline.
- Orchestrate ETL/data modeling tasks using workflow automation.
- Visualize and report on digital song purchase and usage data for analytics.

---

## Data Quality, Orchestration, and Visualization Process

### 1. Data Quality

- **Great Expectations:** Data quality is validated using Great Expectations, including schema checks, data type validation, missing/duplicate detection, and business rule enforcement.
- **Automated Tests:** Quality checks are integrated within the pipeline, ensuring that only valid data progresses to downstream analytics and reporting.

### 2. Orchestration

- **Apache Airflow:** The pipeline's ETL, testing, and modeling steps are orchestrated as Directed Acyclic Graphs (DAGs) in Apache Airflow.
- **Automation:** Orchestration includes data extraction, quality checks, transformations, and loading into Redshift, as well as dbt model execution and reporting.
- **Infrastructure as Code:** All orchestration components are provisioned and managed using Terraform for reproducibility.

### 3. Visualization

- **Dashboards:** The final, validated data is visualized using dashboards and reporting tools (e.g., Tableau, AWS QuickSight, or custom Python visualization).
- **Business Insights:** Dashboards provide insights into user behavior, song purchases, and operational metrics, supporting strategic business decisions.

---

## Instructions

### Requirements

- All requirements from Part 1, plus:
  - Great Expectations for data quality validation
  - Apache Airflow for orchestration (with required Python dependencies)
  - Dashboard/reporting tool (optional for local visualization)
- AWS account with permissions for Airflow, Glue, Redshift, S3, IAM, etc.
- Terraform CLI and dbt CLI installed

### Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/samhmariam/DeepLearning.AI-Data-Engineering.git
   cd "Capstone Project/Part 2 - Data Quality, Orchestration and Visualization"
   ```

2. **Provision infrastructure** (including Airflow, S3, Redshift, IAM):
   ```bash
   cd terraform
   terraform init
   terraform apply
   ```

3. **Configure and deploy Airflow DAGs:**
   ```bash
   # Copy DAGs to Airflow's DAGs folder, or use Airflow's CLI/UI as appropriate
   cd ../dags
   # (Sample command; actual deployment may vary based on your Airflow setup)
   ```

4. **Run data quality checks:**
   ```bash
   # Run Great Expectations validations as part of DAG or manually
   ```

5. **Execute pipeline and dbt models via Airflow:**
   - Use the Airflow UI or CLI to trigger DAG runs and monitor progress.

6. **Visualize the results:**
   - Use the preferred dashboarding tool to connect to Redshift or S3 and build visualizations.

---

## Project Structure

- `C4_W4_Assignment_2.ipynb` — Main notebook for pipeline orchestration, quality checks, and visualization.
- `dags/` — Airflow DAG definitions for workflow orchestration.
- `scripts/` — Supporting scripts for validation and transformation.
- `dbt_modeling/` — dbt models for advanced data transformations.
- `terraform/` — Infrastructure as Code for resources provisioning.
- `images/` — Visual assets and architecture diagrams.

---

## References

- Great Expectations: https://greatexpectations.io/
- Apache Airflow: https://airflow.apache.org/
- dbt: https://www.getdbt.com/
- AWS Glue: https://aws.amazon.com/glue/
- Tableau: https://www.tableau.com/
- AWS QuickSight: https://aws.amazon.com/quicksight/

---

## Contact

For questions or feedback, please open an issue or contact the repository owner.
