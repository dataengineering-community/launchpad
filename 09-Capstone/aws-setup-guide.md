# AWS Setup Guide

To complete this capstone project, you will need access to the cloud environment where the datasets and infrastructure that you need are hosted.

We are using Amazon Web Services (AWS) for this.

The datasets are stored in **Amazon S3**, and some configuration values (such as database credentials) are stored in **AWS Systems Manager Parameter Store**.
Follow the steps below to configure your environment.

**Note:** An IAM user with the least required permissions to access what you need from the **SupllyChain360** AWS account has been created for you. 

Access to this account is very limited. You must use your own cloud platform account to work on the project.

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

## 4. Create Your Access Keys (Required for Programmatic Access)
Your data pipelines may need to access AWS programmatically (for example from Python scripts).

To do this you must create an **Access Key.**

**Steps:**

1. Login to the AWS Console
2. Click your username at the top right of the screen
3. Click Security Credentials
4. Scroll to Access Keys
5. Click Create Access Key

Download or copy the following credentials:
- Access Key ID
- Secret Access Key

**Important:**
- Save these values securely
- Never commit AWS credentials to GitHub
- Never share your Access Keys
