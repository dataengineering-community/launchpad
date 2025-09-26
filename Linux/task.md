# Overview
As a data engineer, you have been tasked to set up a data processing pipeline using Linux commands and scripts. This project would cover file manipulation, automation, permissions management, scheduling with cron, and logging.

---

## 1. Set Up the Environment
Set up a Linux virtual machine (VM) or environment.
- Create directories for organizing the pipeline:
    - ~/data_pipeline/input 
    - ~/data_pipeline/output 
    - ~/data_pipeline/logs

---

## 2. Data Ingestion and Preprocessing
Simulate data ingestion by creating or downloading sample datasets (CSV files) and saving them to the input folder. (We can provide this)
- Write a script `preprocess.sh` to clean and prepare the data files. The script should:
    - Filter or remove unnecessary columns.
    - Format data (e.g., date formatting).
    - Save cleaned files in the output folder.
    - And so on.
    - Make preprocess.sh executable

## 3. Automate the Pipeline with Cron Jobs
- Set up a cron job to automate data processing.
- Schedule preprocess.sh to run every day at midnight
- Confirm the cron job is active by listing scheduled jobs

## 4. Logging and Monitoring
- Redirect output and error logs to the logs folder to monitor the pipeline’s progress.
- Write a `monitor.sh` script that checks for errors in the logs and notifies you if any are found. This script should:
    - Search for errors (e.g., "ERROR" or "failed") in log files.
    - If errors are found, print them to the terminal or write to a summary log.
    - Schedule this monitoring script to run after each daily processing job by adding it to cron (e.g., 12:05 AM).

## 5. Permissions and Security
- Adjust permissions to secure files and directories:
- Set the input folder to be writable only by your user.
- Restrict access to logs so only authorized users can read them.
