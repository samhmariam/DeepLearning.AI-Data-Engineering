# Part 1 - ETL and Data Modeling

## Overview

This project is part of the DeFtunes Capstone, focusing on building a robust ETL data pipeline and data modeling solution for a music streaming company expanding into digital song purchases. The goal is to design a reproducible, cloud-based pipeline that ingests, transforms, and models data to support analytics and business insights for the new purchase feature.

Key objectives:
- Develop an end-to-end ETL pipeline using AWS Glue, Terraform, and S3.
- Apply the medallion architecture: landing, transformation (silver), and serving (gold) zones.
- Store data lake layers in S3, use Iceberg tables for the silver zone, and Redshift for the gold zone.
- Model data into a star schema in the serving layer using dbt and Redshift Spectrum.

---

## ETL and Data Modeling Process

### 1. Data Sources

- **Operational Database (RDS Postgres):** Contains song catalog and metadata, including tables derived from the Million Song Dataset.
- **REST API:** Provides transactional data on user sessions, song purchases, and user profiles related to digital purchases.

### 2. Pipeline Architecture

- **Landing Zone:** Raw data is ingested from both the RDS database and API endpoints and stored as-is in S3 buckets.
- **Transformation Zone (Silver Layer):** Data is cleansed, validated, and structured using AWS Glue, with Iceberg tables providing ACID compliance and better schema management.
- **Serving Zone (Gold Layer):** Refined business-ready data is loaded into Amazon Redshift and modeled as a star schema for analytics consumption.

### 3. Data Modeling

- **dbt (Data Build Tool):** Used to transform and model the data into fact and dimension tables, following best practices for analytics and reporting.
- **Redshift Spectrum:** Enables querying star-schema data directly from S3, integrating with Redshift for high-performance analytics.

### 4. Infrastructure as Code

- **Terraform:** All AWS resources (S3 buckets, Glue jobs, Redshift clusters, IAM roles, etc.) are provisioned using Terraform for reproducibility and version control.

---

## Instructions

### Requirements

- AWS account with permissions for Glue, Redshift, S3, and IAM.
- Python 3.x, Jupyter Notebook.
- `boto3`, `pandas`, `requests`, `sqlalchemy`, and other standard Python packages.
- Terraform CLI installed.
- dbt CLI installed.

### Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/samhmariam/DeepLearning.AI-Data-Engineering.git
   cd "Capstone Project/Part 1 - ETL and Data Modeling"
   ```

2. **Review and configure AWS credentials** for Terraform and Python scripts.

3. **Provision infrastructure** with Terraform:
   ```bash
   cd terraform
   terraform init
   terraform apply
   ```

4. **Run Jupyter Notebook** for ETL orchestration and EDA:
   ```bash
   jupyter notebook C4_W4_Assignment_1.ipynb
   ```

5. **Run dbt models** for data modeling:
   ```bash
   cd scripts/dbt
   dbt run
   dbt test
   ```

---

## Project Structure

- `C4_W4_Assignment_1.ipynb` — Main notebook for pipeline orchestration and analysis.
- `scripts/` — Python and dbt scripts for transformation and modeling.
- `terraform/` — Terraform configurations for AWS infrastructure.
- `images/` — Architecture diagrams and visual assets.

---

## References

- Million Song Dataset: http://millionsongdataset.com/
- AWS Glue: https://aws.amazon.com/glue/
- Apache Iceberg: https://iceberg.apache.org/
- dbt: https://www.getdbt.com/
- Redshift Spectrum: https://docs.aws.amazon.com/redshift/latest/dg/c-using-glue.html

---

## Contact

For questions or feedback, please open an issue or contact the repository owner.
