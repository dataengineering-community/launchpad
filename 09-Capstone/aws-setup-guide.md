# AWS Setup Guide

To complete this capstone project, you will need access to the cloud environment where the datasets and infrastructure are hosted.

We are using Amazon Web Services (AWS) for this.

The datasets are stored in **Amazon S3**, and some configuration values (such as database credentials) are stored in **AWS Systems Manager Parameter Store**.
Follow the steps below to configure your environment.

## 1. Login to AWS

You will receive the following credentials from the program administrators:
- AWS Console URL
- Username
- Temporary Password

Use these credentials to login to the AWS console.

After your first login, you will be prompted to change your password.

## 2. Access the Project Data in S3
The raw datasets for the project are stored in Amazon S3.

**Bucket structure:**

- s3://supplychain360-data/
    - raw/
        - products/
        - warehouses/
        - suppliers/
        - shipments/
        - inventory/

## 3. Access Configuration from Parameter Store
The credentials of the PostgreSQL database for the **Stores Sales Transactions** are stored securely in the AWS Systems Manager Parameter Store.
**parameters:**
- /supplychain360/db/host
- /supplychain360/db/port
- /supplychain360/db/dbname
- /supplychain360/db/user
- /supplychain360/db/password
