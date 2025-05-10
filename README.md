# Data Engineering YouTube Analysis Project
**Domain:** Data Engineering | Cloud Computing | Data Lake Architecture | AWS | BI Analytics

**Overview:**
This project focuses on building an end-to-end Data Engineering pipeline to ingest, transform, store, and analyze structured and semi-structured YouTube video data. The core objective is to efficiently manage video metadata and trending metrics, categorized by video topics, in a scalable and secure cloud environment. The end output is an interactive BI dashboard answering key analytical questions.

**Project Goals:**

1.Data Ingestion: Collect data from multiple structured and semi-structured sources, including JSON/CSV files representing YouTube video details and statistics.  
2.ETL System: Build a robust Extract-Transform-Load (ETL) process to clean, validate, and enrich the raw data into analytics-ready datasets.  
3.Data Lake Formation: Store all raw and transformed data in a centralized Amazon S3 data lake using well-defined folder partitions (raw, processed, curated zones).  
4.Scalability: Design the system with scalability in mind to efficiently process increasing volumes of data with minimal changes.  
5.Cloud Deployment: Offload heavy data processing tasks to the cloud using AWS to ensure performance, cost-effectiveness, and manageability.  
6.Reporting: Build a dashboard using Amazon QuickSight to visualize key KPIs such as views, likes, trending categories, most engaging content, etc.

**Services & Tools Used:**

| AWS Service           | Description                                                                                                    |
| --------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Amazon S3**         | Centralized object storage used as the data lake to store raw, processed, and curated datasets.                |
| **AWS IAM**           | Securely manage user and service permissions across AWS services.                                              |
| **AWS Glue**          | Serverless ETL service used to crawl, transform, and catalog datasets. Supports PySpark and Glue Data Catalog. |
| **AWS Lambda**        | Event-driven compute service used to trigger data transformation and Glue workflows.                           |
| **AWS Athena**        | Serverless interactive SQL query engine to analyze data directly in S3 without moving it.                      |
| **Amazon QuickSight** | BI service used to build interactive dashboards and perform visual data exploration.                           |

**Workflow Architecture:**

            +-----------------+
            |   Raw Data      |   <-- JSON/CSV from Kaggle(Youtube Analysis Data), External sources
            +--------+--------+
                     |
                     v
        +------------+-------------+
        |      Amazon S3 (Raw)     |
        +------------+-------------+
                     |
                     v
        +--------------------------+
        |     AWS Glue Jobs        |   <-- Transform, Clean, Enrich
        +------------+-------------+
                     |
                     v
        +--------------------------+
        |    Amazon S3 (Curated)   |
        +--------------------------+
                     |
        +------------+-------------+
        |       AWS Athena         |   <-- Query curated data using SQL
        +------------+-------------+
                     |
                     v
            +-----------------+
            | Amazon QuickSight|   <-- Dashboard Reporting
            +-----------------+

**Key Features:**
1.Fully serverless architecture using AWS services — no need to manage servers or clusters.  
2.Supports structured and semi-structured data (CSV, JSON).  
3.Modular and scalable ETL pipeline using AWS Glue and S3.  
4.Secure access using AWS IAM policies and roles.  
5.Near real-time or scheduled updates using AWS Lambda triggers.  
6.Self-service analytics and visualizations using Amazon QuickSight.  

**Prerequisites:**
1.Before running or deploying this project, ensure:  
2.An active AWS account with access to IAM, S3, Glue, Lambda, Athena, and QuickSight.  
3.IAM roles with proper permissions for S3, Glue, and Lambda execution.  
4.Data files (CSV/JSON) representing YouTube video metadata.  
5.Basic understanding of AWS services and PySpark/SQL.  



