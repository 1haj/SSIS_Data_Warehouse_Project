# Clinic Data Warehouse Project (SQL Server + SSIS)

## Overview
This project demonstrates the design and implementation of a **Data Warehouse** for a clinic management system using:

- **SQL Server Integration Services (SSIS)**
- **SQL Server Database Engine**
- **ETL workflows (Extract → Transform → Load)**
- **Star Schema dimensional modelling**

The system integrates multiple clinic-related data sources into a clean, analytics-ready data warehouse to support **reporting, data analysis, performance monitoring, and decision-making**.

## Project Goals
- Build a scalable **Data Warehouse** for clinic operations  
- Create **dimension tables** for patients, doctors, services, gender, insurance, etc.  
- Create **fact tables** representing clinical activities and transactions  
- Implement **ETL pipelines** using SSIS for automated loading  
- Apply data transformations, lookups, validation, and error handling  
- Enable analytical queries through a **star-schema** design  

## Data Warehouse Architecture

### Fact Tables
- `fact_header` — Summary-level clinic transaction information  
- `fact_details` — Detailed transaction items including services and costs  
- `fact_table_final` — Final optimized fact table used for reporting  

### Dimension Tables
Includes:  
`dim_patients`, `dim_doctor`, `dim_gender`, `dim_customertype`, `dim_insu_type`, `dim_insu_service`,  
`dim_city_provinc`, `dim_service_servicegroup`, `dim_relation_type`, `dim_user_usergroup`, `dim_date`

## ETL Pipeline (SSIS)

### Extract  
- Pulls clinic operational data from source systems

### Transform  
- Cleans raw data, handles nulls, standardizes values  
- Lookup transformations for all dimensions  
- Creates surrogate keys  
- Implements validation checks  

### Load  
- Inserts data into DW dimension & fact tables  
- Ensures referential integrity  
- Supports incremental loading  

SSIS solution includes:  
`.dtproj` project file, `.dtsx` packages, `Project.params`, database metadata files.

## Repository Structure

```
/Clinic Data Warehouse (SSIS)
│
├── dim tables (.dtsx / metadata)
├── fact tables (.dtsx / metadata)
├── clinic_WH.dtproj
├── Integration Services Project files
├── Project.params
└── Database schema files
```

## Business Value
This warehouse supports:

- Clinic performance analytics  
- Patient segmentation  
- Doctor productivity monitoring  
- Service utilization metrics  
- Insurance usage trends  
- Financial/operational reporting  

## Technologies Used
- SQL Server  
- SSIS (SQL Server Integration Services)  
- Dimensional Modelling (Star Schema)  
- ETL workflows  
- T-SQL  

## Future Improvements
- Schedule automated runs via SQL Server Agent  
- Add audit/error logging  
- Implement Slowly Changing Dimensions (SCD Type 1/2)  
- Build Power BI dashboards on top of DW  
