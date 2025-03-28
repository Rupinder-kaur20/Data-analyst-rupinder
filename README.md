
# HR - 8002p Conflict Resolution Procedure Analysis

## Introduction
This project focuses on analyzing conflict resolution patterns within an HR department using AWS services. The goal is to conduct an exploratory and descriptive analysis to identify trends, resolution effectiveness, and factors influencing conflict outcomes. The analysis leverages AWS services used throughout the term to process and visualize HR data efficiently.

### Project Title:
**Understanding Conflict Resolution in HR: An Exploratory Data Analysis**

### Objective:
The primary objective of this project is to utilize Amazon Web Services (AWS) to perform Exploratory Data Analysis (EDA) on the HR conflict resolution dataset associated with UCW HR-8002P. The goal is to implement cloud-based solutions that will enable efficient data processing, cleaning, transformation, analysis, and reporting of HR-related data.

### Dataset Overview:
The dataset consists of records related to conflict resolution cases within an organization, including:
- **Case ID**: Unique identifier for each conflict case
- **Employee ID**: Identification number for employees involved
- **Department**: Department where the conflict occurred
- **Role**: Employee’s job role (e.g., Manager, Analyst, Associate)
- **Conflict Type**: Nature of the conflict (e.g., Workplace Harassment, Performance Dispute, Policy Violation)
- **Reported Date**: Date the conflict was reported
- **Resolution Date**: Date the conflict was resolved
- **Resolution Time**: Time taken to resolve the conflict
- **Resolution Method**: Mediation, Investigation, Policy Change, or Other
- **Outcome**: Conflict resolution status (Resolved, Unresolved, Escalated)

The dataset consists of HR conflict resolution records, which are initially stored in AWS S3. The data undergoes transformation using AWS Glue and AWS Glue DataBrew, followed by advanced analysis with Amazon Athena. Monitoring and logging are carried out through AWS CloudWatch and CloudTrail.

### Methodology:
1. **Data Collection**: HR data is stored in Amazon S3 in raw bucket named hr-raw-rup, as a CSV file. S3 provides a scalable and secure storage solution for the large volumes of data, ensuring durability and ease of access (see Appendix, Screenshot 1).
2. **Data Cleaning**: Data quality is ensured by using AWS Glue DataBrew, a no-code tool that simplifies the process of data cleaning. This step involves identifying and correcting data anomalies, handling missing values, and standardizing data formats (see Appendix, Screenshot 2).
3. **Data Transformation**: AWS Glue is employed to process the data using Extract, Transform, and Load (ETL) jobs. This service facilitates the transformation of raw data into a structured format, suitable for querying and analysis (see Appendix, Screenshot 3).
4. **Data Analysis**: The cleaned and structured data is analyzed using Amazon Athena, a serverless query service that enables users to run SQL queries directly on data stored in S3. Athena’s seamless integration with S3 ensures an efficient querying process. This includes 3 business questions (see Appendix, Screenshot 4,5,6).
5. **Data Monitoring**: AWS CloudWatch is utilized for monitoring system performance and resource usage during the data analysis process. Implemented AWS CloudWatch to monitor S3 bucket activities, track bucket size and resource usage, and set up alarms for critical changes (see Appendix, Screenshot 7). AWS CloudTrail provides auditing capabilities, allowing for detailed logs of user and service activity for security and compliance purposes (see Appendix, Screenshot 8). Multi-region tracking is enabled for broader coverage, though log validation and SNS alerts are disabled. To enhance real-time monitoring, I configured AWS SNS and CloudWatch alarms, which send instant notifications if any metric crosses its threshold. This setup ensures proactive security, cost efficiency, and optimal data management in my AWS environment.
6. **Security & Access Management**: Security is managed using AWS KMS (Key Management Service) for encryption and AWS Organizations for controlling access across different accounts. These services ensure that sensitive HR data is protected and accessible only to authorized users. I configured Default Encryption, Bucket Versioning, and Replication for three S3 buckets: hr-trf-rup, hr-cur-rup, and hr-raw-rup (see Appendix, Screenshot 9).

   - **Replication**: Set up an S3 replication rule to automatically copy objects between buckets using AWS KMS encryption. This ensures data availability, disaster recovery, compliance, and backup, making the system more resilient (see Appendix, Screenshot 11).
   - **Default Encryption**: Enabled AWS KMS encryption, so objects are automatically encrypted for data security and protection against unauthorized access (see Appendix, Screenshot 12).
   - **Bucket Versioning**: Activated S3 Versioning to track changes, store encrypted versions and prevent accidental loss. IAM and key policies restrict decryption to authorized users for added security (see Appendix, Screenshot 10).

### Tools and Technologies:
- AWS Glue
- AWS Glue DataBrew
- Amazon S3
- Amazon Athena
- AWS CloudTrail
- AWS CloudWatch
- AWS Key Management Service (KMS)

### Deliverables:
- Data ingestion and transformation reports
- Analytical insights using Amazon Athena
- Monitoring logs from AWS CloudWatch and AWS CloudTrail
- Security and compliance report using AWS KMS and AWS Organizations
- Screenshots of AWS Console for different services used

---

## 2. Descriptive Analysis:

### Project Title:
**Exploring HR Conflict Resolution Data using AWS Services**

### Objective:
The objective of this phase is to conduct a detailed descriptive analysis of the HR conflict resolution dataset. The goal is to uncover trends, patterns, and statistical summaries that provide valuable insights into HR conflict resolution processes.

### Dataset:
The HR conflict resolution data, stored in AWS S3 and processed using AWS Glue DataBrew, is analyzed using Amazon Athena to generate descriptive statistics.

### Methodology:
1. **Data Ingestion**: Data is ingested from AWS S3 i.e., raw bucket hr-raw-rup, where it is stored in its raw form (see Appendix, Screenshot 1).
2. **Data Cleaning and Transformation**: AWS Glue DataBrew is used to clean and preprocess the data by removing duplicates, handling missing values, renaming the columns, and transforming data into an analyzable format (see Appendix, Screenshot 13).
3. **Statistical Analysis**: Summary statistics and aggregations are generated through SQL queries in Amazon Athena (see Appendix, Screenshot 4,5,6).
4. **Visualization and Monitoring**: Data trends and metrics are visualized through AWS CloudWatch dashboards to monitor the data's characteristics over time (see Appendix, Screenshot 7).

### Tools and Technologies:
- AWS S3
- AWS Glue DataBrew
- Amazon Athena
- AWS CloudWatch

### Deliverables:
- A report containing summary statistics generated using Amazon Athena queries
- Logs detailing the data cleaning and transformation processes
- Screenshots of the AWS Console displaying the data workflows and analysis

---

## 3. Diagnostic Analysis:

### Project Title:
**Diagnostic Analysis of Data Quality Issues in HR Conflict Resolution Records**

### Objective:
The purpose of this analysis is to identify data inconsistencies, missing values, and anomalies in the HR conflict resolution dataset to ensure the quality and accuracy of the data.

### Background:
Accurate data is essential for HR decision-making. This diagnostic analysis seeks to detect data quality issues and recommend necessary corrective actions.

### Dataset:
The HR conflict resolution dataset stored in AWS S3 is examined for issues such as missing values, inconsistencies, and duplicates.

### Methodology:
1. **Data Profiling**: AWS Glue DataBrew is used to profile the dataset and identify potential anomalies, such as missing or incorrect values (see Appendix, Screenshot 14).
2. **Anomaly Detection**: AWS Glue ETL jobs are employed to perform anomaly detection and handle any issues found in analysis (see Appendix, Screenshot 3).
3. **Query-Based Diagnostics**: Queries executed in Amazon Athena are used to further identify data inconsistencies (see Appendix, Screenshot 4).
4. **Security Auditing**: AWS CloudTrail logs any access or modification to the data, ensuring compliance and traceability (see Appendix, Screenshot 9).

### Tools and Technologies:
- AWS Glue
- AWS Glue DataBrew
- Amazon Athena
- AWS CloudTrail

### Deliverables:
- A report outlining detected data inconsistencies and anomalies.
- Results from Athena queries used for data quality diagnostics.
- CloudTrail logs documenting access and modifications to the data.
- Screenshots from the AWS Glue DataBrew and CloudTrail dashboards.

---

## 4. Data Wrangling

### Project Title:
**Data Wrangling for HR Conflict Resolution Analytics**

### Objective:
The objective of this phase is to preprocess, clean, and structure the HR-8002P dataset in preparation for further analysis.

### Background:
Data wrangling is necessary to ensure that the dataset is consistent, formatted correctly, and free of errors. This process involves handling missing values, removing duplicates, and standardizing data formats.

### Dataset:
The HR-8002P dataset stored in AWS S3 serves as the input for the data wrangling process.

### Methodology:
1. **Data Ingestion**: The dataset is ingested into AWS S3 (see Appendix, Screenshot 1).
2. **Preprocessing**: The data is cleaned using AWS Glue DataBrew, which identifies and resolves inconsistencies (see Appendix, Screenshot 15).
3. **Data Structuring**: AWS Glue is used to catalog the structured data for ease of access and analysis (see Appendix, Screenshot 19).

### Tools and Technologies:
- AWS S3
- AWS Glue
- AWS Glue DataBrew

### Deliverables:
- A cleaned and transformed dataset
- AWS Glue data catalog documentation detailing the structure of the dataset
- Screenshots of the AWS Glue and AWS DataBrew interfaces showing the data transformations and cataloging processes.

---

## 5. Data Quality Control

### Project Title:
**Ensuring Data Quality in HR Conflict Resolution Reports**

### Objective:
This phase focuses on establishing data validation processes to ensure that the data used for analysis is of high quality and accuracy.

### Background:
Ensuring data quality is essential for making informed HR decisions. This project establishes a framework for data validation and quality control.

### Scope:
This phase covers identifying and correcting errors in the HR dataset, as well as implementing validation checks to maintain data integrity.

### Methodology:
1. **Data Profiling**: Data is profiled using AWS Glue DataBrew to detect inconsistencies and errors (see Appendix, Screenshot 16).
2. **Validation Rules**: AWS Glue ETL jobs are used to enforce validation rules and correct any issues identified. The system fetches data from the raw S3 bucket, applies transformations to maintain data quality, and records timestamps for entries. It enforces uniqueness by preventing duplicate records, ensures completeness by verifying mandatory fields, and maintains freshness by keeping data up-to-date (see Appendix, Screenshot 17). Records failing these checks are moved to the "failed" folder in the hr-trf-rup bucket for verification, while valid records are stored in the "passed" folder for further processing. This setup ensures data consistency, quality preservation, and accurate analytics (see Appendix, Screenshot 18).
3. **Logging**: AWS CloudWatch logs are used to monitor the effectiveness of data quality controls and track improvements over time.

### Deliverables:
- Data validation and quality control reports
- Logs from AWS CloudWatch showing quality metrics and validation rule outcomes
- Screenshots of the AWS DataBrew profiling and AWS Glue validation rule configurations.
### Appendix
![Screenshot 2025-03-27 131156](https://github.com/user-attachments/assets/80e54be8-50a0-4acb-aa35-18ac8bcd4065) screenshot 1

![Screenshot 2025-03-27 141654](https://github.com/user-attachments/assets/740d858a-9ef7-4c3e-b8e2-e26d8509d77f) screenshot 2

![Screenshot 2025-03-27 131950](https://github.com/user-attachments/assets/25d82fbf-b15c-425d-a449-d1ef3c36a27f) screenshot 3

![Screenshot 2025-03-27 132243](https://github.com/user-attachments/assets/cd75e6ae-2a82-4330-8a10-c8960f5adbd1) screenshot 4

![Screenshot 2025-03-27 132303](https://github.com/user-attachments/assets/019d0172-2aad-4993-82ce-3c110d3c2052) screenshot 5

![Screenshot 2025-03-27 132324](https://github.com/user-attachments/assets/a186a914-49fb-484d-a614-f3248121c2c9) screenshot 6

![Screenshot 2025-03-27 132645](https://github.com/user-attachments/assets/adc2c45b-3d96-44b0-aa2c-04b67215fb65) screenshot 7

![Screenshot 2025-03-27 132628](https://github.com/user-attachments/assets/66a458eb-937a-4e93-ab5e-d572495546a8) screenshot 8

![Screenshot 2025-03-20 213150](https://github.com/user-attachments/assets/27e9d2a0-8612-452c-b8a5-4fe9e6bfa13e) screenshot 9

![Screenshot 2025-03-20 213323](https://github.com/user-attachments/assets/b5521ea8-7697-4764-a798-5f326cef1055) screenshot 10

![Screenshot 2025-03-20 213350](https://github.com/user-attachments/assets/88bdcea9-e736-4e7c-99bb-df9196ca9aa5) screenshot 11

![Screenshot 2025-03-20 213259](https://github.com/user-attachments/assets/a590b7ec-4830-495f-8baf-76f7b048d7b9) screenshot 12

![Screenshot 2025-03-27 132529](https://github.com/user-attachments/assets/782ed02e-c25f-4b36-a27e-9d0a83135f5c) screenshot 13

![Screenshot 2025-03-27 195145](https://github.com/user-attachments/assets/64cb4fde-5cc7-4d6a-a091-2d2e694fbbd2) screenshot 14

![Screenshot 2025-03-27 132601](https://github.com/user-attachments/assets/1b28f7a2-e86d-468b-bdce-2ecc300cd747) screenshot 15

![Screenshot 2025-03-27 132546](https://github.com/user-attachments/assets/4fe048e0-f5d7-4d7d-ad1b-14ad8a2efe6e) screenshot 16

![Screenshot 2025-03-27 153649](https://github.com/user-attachments/assets/8f659592-5521-4b6a-8523-74e3d63e5fa9) screenshot 17

![Screenshot 2025-03-27 131442](https://github.com/user-attachments/assets/10f56167-b865-4166-9de5-7796ffd9d94e) screenshot 18

![Screenshot 2025-03-27 131735](https://github.com/user-attachments/assets/63a00073-a477-4f6b-aa7f-ec016a3c3797) screenshot 19

### Course completion Badge 
![Badge](https://github.com/user-attachments/assets/348dfeb9-8343-421c-9fbe-82bfa352685c)
