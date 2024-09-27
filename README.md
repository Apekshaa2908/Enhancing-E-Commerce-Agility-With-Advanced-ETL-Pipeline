# Enhancing-E-Commerce-Agility-With-Advanced-ETL-Pipeline
**Project Overview**
This project focuses on improving the agility of e-commerce operations by implementing an advanced ETL (Extract, Transform, Load) pipeline using various AWS services. The solution facilitates secure data uploads, efficient data processing, and comprehensive monitoring of data workflows.

**Key Features**
**Streamlit Web Application:** A user-friendly interface that allows the Order and Returns teams to upload their respective data files securely. The application ensures that uploaded files are directed to the appropriate S3 buckets for further processing.

**AWS Lambda Trigger:** An AWS Lambda function is automatically triggered upon the upload of new files to the Order and Returns S3 buckets. This function invokes an AWS Glue ETL job to process the uploaded data.

**Glue ETL Job:** The Glue ETL job fetches the uploaded data files, performs necessary data transformations using PySpark, and joins the datasets based on the "Order ID" column, resulting in a consolidated dataset.

**Data Storage and Querying:** The final joined dataset is stored in an Amazon Redshift data warehouse, allowing for efficient querying and analysis. Users can also implement similar functionality using Databricks if preferred.

**AWS Step Functions:** The workflow is orchestrated using AWS Step Functions, which manage the entire ETL process and monitor each stage of execution. This allows users to track the status of the pipeline and identify any failures.

**SNS Notifications:** Two subscription endpoints are configured for email notifications. After each execution, the system sends out SNS notifications to inform stakeholders of the pipeline's success or failure.

## Workflow
Data Upload: Users upload "order" and "returned" data files via the Streamlit application.

Trigger Lambda Function: The upload triggers a Lambda function that starts the Glue ETL job.

ETL Processing: The Glue job processes the files, performing data transformations and joining datasets.

Store Results: The joined dataset is stored in Amazon Redshift for further analysis.

Monitor with Step Functions: The entire process is monitored using AWS Step Functions.

Notifications: Email notifications are sent to inform users of the execution status.
