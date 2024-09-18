
# DataAnalyst-Vijaya
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

![Project1](https://github.com/Vijaya397/Data-Analyst-Vijaya/blob/main/Images/Project1_Draw.io.jpg?raw=true
)
# Methodology
## 1. Data Discovery
From opendata.vancouver.ca, the Data team identified a robust dataset that could help us answer our initial doubts; the data from the website ensures open Government license, data quality, consistency, and governance, providing flexibility to leverage data effectively.

The Inquiry Volume dataset provides information about the volumes of inquiries for 2023 and 2024 that come into the 311 contact centers via channels like phone and chat for different departments and many types of queries. This dataset helps analyze the volume of the records for each department (3-1-1 Inquiry Volume, 2024).
## 2. Data Storage Design
In the data storage phase of the AWS Data Analytic Platform, the main objective is to set up a strong foundation and architecture to store the operational as well as the analytical data securely and optimally. This is made possible through Amazon Simple Storage Service (S3), which provides highly accessible, scalable, and durable object storage. S3 is well suited for storing data within a broad range, from raw operational data and analytical data structures to processed datasets, all stored and managed with no compromises on integrity and availability.
Using Amazon S3, we created three buckets for storing Excel files. S3 buckets are designed so that each bucket can store the data for two years, 2023 and 2024, and every operational bucket has 3 folders: Landing, Raw, and Curated. The operational dataset is loaded into the landing zone in Excel format, and the analytical, structured, cleaned data is loaded into a raw folder of high quality. The analytical data with summarized results are stored in a curated folder in CSV format.
 ## 3. Dataset Preparation
The main aim of dataset preparation is to assimilate and categorize the data by ensuring the quality and functionality of all s for analysis. This encompasses data ingestion, cleaning, normalization, and structuring. AWS Glue DataBrew is used for data categorization and allows working with different data sources on other platforms. Data preparation takes the ingested data and processes it into format data (What Is AWS Glue DataBrew? - AWS Glue DataBrew, n.d.).
In AWS Glue DataBrew, we have created two separate projects, one for each dataset for 2023 and 2024. Cleaning the datasets, we changed the column names and their datatypes and deleted the unwanted columns for precise results. Created two jobs to prepare for two CSV file dataset 


![Big Data Framework](https://github.com/your-github-username/your-repo-name/blob/main/images/bcframework.png)

## [Project 3: Analysing Big Data streams in Cluster](https://link-to-your-paper-or-github)
In this project, a framework was designed and implemented for the efficient analysis of Big Data streams using cluster resources.  
- Improved the efficiency of the analysis by up to 65%.
- A distributed cluster of 32 computing nodes was implemented using Linux, Storm, Java, and Python.
- All evaluations were executed on the implemented cluster with real-world scenarios.

![Cluster Analysis Framework](https://github.com/your-github-username/your-repo-name/blob/main/images/cluster_framework.png)
