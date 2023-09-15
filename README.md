# Azure COVID Prediction & Reporting Pipeline

## Objective:   
The aim of the project is to create a pipeline for the purpose of reporting and prediction purpose of covid19 data. The prediction can be done by the data science team by building ML models from the data, but prediction is out of scope of this project. Another main objective is to create a data warehouse, where the analytics team can access the data, which could be used by our analytics team to do analysis on top of it. Here in our project, since the data is small in size, in place of a Data Warehouse, we use an Azure SQL database instead. Also to top it all, we built a minimum working Dashboard using Power BI.

Data Lake to be built with the following data to aid Data Scientists to predict the spread of the virus/mortality :
* Confirmed cases
* Mortality
* Hospitalization/ ICU Cases
* Testing Numbers
* Country’s population by age group

Data Warehouse to be built with the following data to aid Reporting on Trends :
* Confirmed cases
* Mortality
* Hospitalization/ ICU Cases
* Testing Numbers

Data Orchestration requirement:
* Pipeline executions are full automated
* Pipelines run at regular intervals or on an event occurring
* Activities only run once the upstream dependency has been satisfied
* Easier to monitor for execution progress and issues

## Architecture Diagram
![Architecture diagram](https://github.com/saheen619/Azure-COVID-Reporting-Pipeline/blob/main/architecture.jpg?raw=true)

## Data Sources:

ECDC Website for Covid-19 Data - https://www.ecdc.europa.eu/en/covid-19/data

Euro Stat Website for Population Data - https://ec.europa.eu/eurostat/estat-navtree-portlet-prod/BulkDownloadListing?file=data/tps00010.tsv.gz

## Workflow:

* ADF Activity - Data Ingestion from Azure Blob Storage
* Web ADF Activity - Data Ingestion from http
* Data Flow - Cases & Deaths Data Transformations
* Data Flow - Hospital Admissions Data Transformations
* HD Insight - Create Cluster
* Hive ADF Activity - Run Hive Script to Transform Data
* Databricks - Create Databricks Cluster and Mount Storage
* Databricks Notebook ADF Activity - Run the Databricks Notebook using Databricks Activity.
* ADLS Gen2 - Make available the required data in Azure Datalake Gen 2 for ML Workloads
* Copy ADF Activity - Copy data to Azure SQL Database for Analytics.
* ADF - Setup Triggers, Alerts and Monitors
* Azure Log Analytics - Setup ADF workflow logs to be monitored on log analytics.
* Power BI - Build a PowerBI Report

## Tools Used  
* Azure Data Factory
* Azure Data Lake Gen 2
* Azure Blob Storage
* Azure SQL Database
* ADF Data Flows
* Azure Databricks
* HD Insights
* Power BI

## Activities Used in ADF
* Copy Activity
* Execute Pipeline Activity
* Validation Activity
* If Condition Activity
* Get Metadata Activity
* Web Activity
* Delete Activity
* For Each Activity
* Lookup Activity
* Hive Activity
* Dataflow Activity
* Databricks Notebook Activity

## Transformations Used in ADF Dataflow
* Source Transformation
* Pivot Transformation
* Select Transformation
* Sink Transformation
* Lookup Transformation
* Filter Transformation
* Conditional Split Transformation
* Aggregate Transformation
* Join Transformation
* Derived Column Transformation
* Lookup Transformation
* Sort Transformation

## Author

[Saheen Ahzan](https://github.com/saheen619)

## Feedback

If you have any feedback, please reach out at saheen619.klm@gmail.com or [linkedin](https://www.linkedin.com/in/saheenahzan/)


