# BUSINESS SCENARIO
`SupplyChain360`, a fast-growing retail distribution company in the United States, manages product distribution for hundreds of retail stores across the country.

Over the past year, the company has been experiencing **serious operational inefficiencies** in its supply chain:
- Stores frequently run **out of stock** of popular products.
- Warehouses report **overstocked inventory** for slow-moving items.
- Delivery delays are becoming common.
- Management cannot accurately answer simple questions like:
    - Which products are causing the most stockouts?
    - Which warehouses are inefficient?
    - Which suppliers consistently deliver late?

The biggest issue is **data fragmentation**. Operational data is spread across multiple systems:
- Warehouse inventory systems
- Logistics shipment records
- Supplier delivery logs
- Store sales data

Each team manages its own data, and reports are manually compiled in spreadsheets every week. By the time leadership receives insights, the data is already outdated.

The company leadership has decided to build a **Unified Supply Chain Data Platform** that centralizes operational data and enables efficient analytics to improve:
- Inventory planning
- Supplier performance monitoring
- Shipment tracking
- Demand forecasting

You have been hired as a Data Engineer to design and implement this platform.

If successful, your platform will allow the company to **reduce stockouts, optimize inventory**, and improve delivery efficiency, potentially saving **millions of dollars annually**.

## DATA SOURCES
You have been granted access to several operational datasets from different systems.

Each dataset represents a **different operational domain of the supply chain.**

### Product Catalog
- Description: Master dataset containing product information sold across stores.
- Format: CSV
- Data Location: Stored in an **S3 Bucket on AWS**
- Frequency: Static dataset (rarely changes)

### Store Locations
- Description: Dataset containing information about retail store locations.
- Format: Google Spreadsheet
- Data Location: [Google Sheets](https://docs.google.com/spreadsheets/d/1y70rZ8qpPd5GJGgZYWwAR4mGAYn8aGGJynwm9GyEVnQ/edit?usp=sharing)
- Frequency: Static dataset

**Note**: You must **move the dataset to your own private Google Sheet** and configure a **Service Account** to programmatically extract the data via the **Google Sheets API**.

### Warehouse Inventory Snapshots
- Description: Daily inventory snapshot of each warehouse showing stock levels per product.
- Format: CSV
- Data Location: Stored in **S3**
- Frequency: Daily

### Shipment Delivery Logs
- Description: Shipment records representing goods transported from warehouses to retail stores.
- Format: JSON
- Data Location: Stored in **S3**
- Frequency: Daily

### Store Sales Transactions
- Description: Transaction records representing sales of products at retail stores.
- Format: PostgreSQL database tables
- Data Location: Transactional Postgres Database
- Credentials stored in **AWS SSM Parameter Store**
    - Schema name: **store_sales**
    - **Tables**:
        - sales_2026_03_10
        - sales_2026_03_11
        - sales_2026_03_12
        - Sales_2026_03_13
        - Sales_2026_03_14
        - Sales_2026_03_15
        - Sales_2026_03_16
- Frequency: New table generated daily

## PROJECT OBJECTIVES
You are required to implement a **Production-Grade Data Platform** that ingests, processes, and models this data.
### Data Ingestion (Raw Layer)
- Develop an ingestion layer that extracts data from each source.
- Store raw data in any Cloud Object Storage in Parquet format.
- The raw layer must preserve all original data for reproducibility.
- Include metadata such as ingestion timestamp
- You must also account for messy data issues

### Data Warehouse and Modeling
Design and implement a Data Warehouse using a platform of your choice such as:
- Snowflake
- BigQuery
- Redshift
Use **dbt** to model the data into **Fact and Dimension tables** suitable for analytics.

The final models should support analytical queries such as:
- product stockout trends
- supplier delivery performance
- warehouse efficiency
- regional sales demand

### Data Cleaning and Enrichment
Clean and standardize the raw datasets.
Examples include:
- standardizing column naming conventions
- removing duplicates
- correcting inconsistent formats
- validating foreign key relationships

You should also **enrich the datasets** by combining multiple sources.

### Workflow Orchestration

You **MUST** use **Apache Airflow** to orchestrate the entire workflow.

Airflow should coordinate:
- Data extraction
- Loading to the raw layer
- Data cleaning
- Data transformation
- dbt model execution
- Data quality checks

You **MUST** also follow best practices including:
- idempotent pipelines
- incremental processing
- retry mechanisms
- failure alerts

### Containerization
For reproducibility across environments, package all code into a Docker Image.
- The image should include all python and DAG codes.
- Push the image to a Container Registry such as Docker Hub, AWS ECR or GCR

### CI/CD Pipeline
Your GitHub repository must include a CI/CD pipeline.

CI should include:
- code linting
- formatting checks
- automated tests where applicable


CD should:
- build the Docker image
- push the image to a container registry

### Infrastructure as Code
All cloud infrastructure must be provisioned using **Terraform**.

Terraform state must be stored in a **remote backend** such as an object storage bucket.
