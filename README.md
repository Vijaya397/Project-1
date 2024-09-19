
# Project 1
Project Portfolio for the 311 Inquiry Volume for the City of Vancouver
# Project Title 
Exploratory Data Analysis (EDA) Initiative for 311 Inquiry Volume for the City of Vancouver
# Project Description 
The Exploratory Data Analysis (EDA) Initiative aims to gain in-depth insights from the 311 Inquiry Volume dataset by transforming raw data into valuable information that can be used to enhance public services. This involves securely storing the data in AWS S3, applying data cleaning and validation techniques with AWS Glue, and analyzing the dataset using AWS Athena to identify patterns, trends, and relationships. By leveraging AWS services, the project enables the City of Vancouver to make data-driven decisions based on accurate, comprehensive insights derived from the 2023 and 2024 inquiry records.
# Objective
The objective of this project is to comprehensively process, clean, and validate the 311 Inquiry Volume dataset to ensure that the data is of high quality, secure, and reliable for analysis. Through Exploratory Data Analysis (EDA), the project will uncover critical patterns and trends within the inquiry data, such as inquiry types, volume fluctuations, and departmental workloads. The project ensures efficient data handling by utilizing AWS services like S3, Glue, and Athena. It enables the City of Vancouver to make informed decisions that enhance public service efficiency and responsiveness based on data-driven insights.
# Dataset
The dataset is a part of the 311 Inquiry Volume project for the City of Vancouver for the years 2023 and 2024, and it includes information about the following:
-	**Department**: Likely the department to which the inquiry was directed.
-	**Type**: The type of inquiry.
-	**Year Month**: The date the inquiry was made.
-	**Channel**: The communication method used (e.g., phone, chat).
-	**Number of Records**: The count of inquiries.
-	**BI_ID**: A unique identifier for each record.

# Background
The 311 Inquiry Volume dataset contains public inquiries about the City of Vancouver through various channels. This project involves processing the 2023 and 2024 datasets to ensure they are well-organized, accurate, and ready for exploratory analysis. The data is cleaned, transformed, and analyzed using AWS tools like Glue, Athena, and S3 to uncover trends and provide meaningful insights.
# Scope
-  Ingest and store the 311 Inquiry Volume dataset in AWS S3.
-  Perform data cleaning and transformation using AWS Glue.
-  Conduct exploratory data analysis using AWS Athena.
-  Use data visualization to uncover trends and insights.
-  Automate the data pipeline for consistent updates and analysis.

![Data Discovery](https://github.com/Vijaya397/Project-1/blob/main/Project1_Draw.io.jpg?raw=true)

# Methodology
## 1. Data Discovery
From opendata.vancouver.ca, the Data team identified a robust dataset that could help us answer our initial doubts; the data from the website ensures open Government license, data quality, consistency, and governance, providing flexibility to leverage data effectively.
![Data Discovery](https://github.com/Vijaya397/Project-1/blob/main/Data%20Discovery.png?raw=true)
The Inquiry Volume dataset provides information about the volumes of inquiries for 2023 and 2024 that come into the 311 contact centers via channels like phone and chat for different departments and many types of queries. This dataset helps analyze the volume of the records for each department (3-1-1 Inquiry Volume, 2024).
## 2. Data Storage Design
In the data storage phase of the AWS Data Analytic Platform, the main objective is to set up a strong foundation and architecture to store the operational as well as the analytical data securely and optimally. This is made possible through Amazon Simple Storage Service (S3), which provides highly accessible, scalable, and durable object storage. S3 is well suited for storing data within a broad range, from raw operational data and analytical data structures to processed datasets, all stored and managed with no compromises on integrity and availability.

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/DataStorageDesign.png?raw=true)

Using Amazon S3, we created three buckets for storing Excel files. S3 buckets are designed so that each bucket can store the data for two years, 2023 and 2024, and every operational bucket has 3 folders: Landing, Raw, and Curated. The operational dataset is loaded into the landing zone in Excel format, and the analytical, structured, cleaned data is loaded into a raw folder of high quality. The analytical data with summarized results are stored in a curated folder in CSV format.
 ## 3. Dataset Preparation
The main aim of dataset preparation is to assimilate and categorize the data by ensuring the quality and functionality of all s for analysis. This encompasses data ingestion, cleaning, normalization, and structuring. AWS Glue DataBrew is used for data categorization and allows working with different data sources on other platforms. Data preparation takes the ingested data and processes it into format data (What Is AWS Glue DataBrew? - AWS Glue DataBrew, n.d.).

In AWS Glue DataBrew, we have created two separate projects, one for each dataset for 2023 and 2024. Cleaning the datasets, we changed the column names and their datatypes and deleted the unwanted columns for precise results. Created two jobs to prepare for two CSV file dataset

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/2023datastructuring.png?raw=true)

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/2024datastructuring.png?raw=true)

For both datasets, the subsequent actions were performed:
-	Rename Type to InquiryType.
-	Rename Number of Records to Number of Records.
-	Rename Department to InquiryDepartment.
-	Rename Year Month to YearMonth.
-	Create column YearMonth_YEAR using the dateTime function YEAR.
-	Create column YearMonth _MONTH using dateTime function MONTH.
 ## 4. Data Ingestion
AWS DataBrew is used for ETL job generation, automating and scaling the data ingestion process by consistently applying defined transformations to data. Data ingestion aims to clean and store data in an accessible and consistent central repository to prepare it for use within the organization. It manages the execution, scheduling, and output storage, ensuring efficient and reliable data preparation.

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/DATAINGESTIONJOBS.png?raw=true)

Our Data Team created two jobs to prepare for two CSV file datasets. 
## 5. Data Storage
The analytical datasets obtained from Datasets are stored in the raw folders of S3 buckets for each year, respectively. The datasets in the raw folder are of high quality with the structured CSV format.

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/2023%20RAW.png?raw=true)

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/2024RAW.png?raw=true)

## 6. Data Pipeline Design
Data pipeline design in AWS Glue involves creating a workflow that automates data ingestion, transformation (ETL), and cataloging. Extract retrieves data from a raw folder from S3 Bucket, and Transform, join. Aggregates are used to normalize and reformat the extracted data to ensure consistency and prepare it for analysis. The output is loaded into the Curated folder of S3 buckets (What Is AWS Glue? - AWS Glue, n.d.).

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/ETLPipeline.png?raw=true)

The Pipeline is designed with an S3 bucket first to get the data from a raw folder of S3 and then transform the data from functions, the two data tables are then joined to get the consolidated data, and the final output is loaded into the storage of S3 buckets.

The Pipeline was created to analyze the volume of inquiries for 2023 and 2024 based on phone communication. The necessary data from both years is combined for a consolidated analysis.
## 7. Data Cleaning
In AWS Glue, the filter function is used to refine data during the transformation process by selecting only the rows that meet the criteria. This helps narrow down the dataset to include only the relevant information, improving the efficiency and focus of the analysis.
## 8. Data Structuring
Change Schema in AWS Glue involves modifying the data structure as it's being processed, such as adding, removing, or altering columns and column names.

![DataStorage Design](https://github.com/Vijaya397/Project-1/blob/main/AGG_CHGSCH.png?raw=true)

## 9. Data Pipeline Implementation
The job created in Glue is to load the output in the curated folder of storage of the S3 bucket. We obtained a high-quality analytical dataset in structure format with summarized results in CSV format. However, the data loaded is not in a readable format. So, we need to proceed to the next step.

![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/DataPipelineImplemetation.png)

## 10. Data Analysis
The most crucial goal in this stage is to analyze processed datasets to gain meaningful insights and information. Amazon Athena is an essential tool for this task; it helps perform an interactive query on data stored in Amazon S3 using SQL. 

![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/Athena.png)

Athena is an AWS serverless analytical query service that lets you analyze data in S3 using SQL. They support comprehensive data formats, and here, they have AWS glue integration for partitioning the schema. Athena was explicitly designed to cost only for the amount of scanned data, making it easy on the pocket and very accommodating to data scientists. The use case is especially suited for ad hoc querying, log analysis, and querying data in a data lake (What Is Amazon Athena? - Amazon Athena, n.d.).
## 11. Data Visualization
The data can be downloaded in CSV Format and is available in readable format; with the available data, the Excel file generates the recommended charts to be presentable and can be easily analyzed. The developed results are stored in pdf format, so keep the format undisturbed.

![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/DATAVISUAL.png)

## 12. Data Publishing
Amazon EC2 (Elastic Compute Cloud) provides scalable computing capacity in the AWS cloud, allowing you to run virtual servers, known as instances, with various configurations based on your needs. EC2 instances, including t2 instances, can be used for a wide range of purposes, such as running general-purpose servers and web servers. T2 instances are designed to provide a baseline level of CPU performance that can burst to higher levels when needed, making them suitable for applications with variable workloads.


![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/GS.png)


![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/GS_console.PNG)

A general-purpose EC2 server is used for various tasks like providing access to files to remote hosts with security.

![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/WS.png)

An EC2 web server is specifically configured to host websites or web applications. It handles clients' HTTP requests and responds to web pages or web applications. It installs the IIS (Internet Information Services) platform from the server manager to host websites, web applications, and services. Making the data accessible from the front, as this is the crucial directory for the context of web servers. With the assigned IP address from the EC2 instance, the data is published and accessed through the Internet.

![DataStorage Design](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/WS_Output.png)

# Tools and Technologies
- AWS Simple Storage Service (S3): For storing raw, processed, and analyzed data.
- AWS Glue DataBrew: This is used to clean and prepare datasets.
- AWS Glue: This automates the ETL process and transforms data.
- AWS Athena: This is used to conduct exploratory data analysis using SQL.
- AWS QuickSight: This is for publishing and visualizing the final data insights.
- Excel: This is used to visualize the dataset and generate charts.
 # Deliverables
- Secure Data Storage: Data stored securely in AWS S3, organized by year and processing stage.
- Validated Dataset: A cleaned and validated dataset ready for exploratory analysis.
- Automated Data Pipeline: An automated data ingestion, transformation, and storage pipeline.
- Exploratory Data Analysis Insights: Key insights from analysis, including trends in inquiry volumes for 2023 and 2024.
- Published Dashboards: Interactive data dashboards published in AWS QuickSight for stakeholder access.






