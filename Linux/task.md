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
