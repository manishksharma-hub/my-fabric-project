Earthquake Data Engineering Project (Microsoft Fabric)
Overview

This project demonstrates an end-to-end data engineering solution that I built on Microsoft Fabric to ingest, process and analyze worldwide earthquake data from the link as below:

**API Documentation - Earthquake Catalog:**
https://earthquake.usgs.gov/fdsnws/event/1/


The pipeline follows a Medallion Architecture (Bronze → Silver → Gold) to ensure scalable, structured and analytics ready data. 
The final insights are delivered through Power BI reporting.

Architecture

The solution is built using the following layered approach:

API Source → Ingestion Pipeline → Bronze Layer → Silver Layer → Gold Layer → Power BI

Components:
Data Source: Worldwide Earthquake Events API - https://earthquake.usgs.gov/fdsnws/event/1/

Ingestion: Fabric Data Ingestion Pipeline based on Notebook

Processing: Notebooks (PySpark)

Storage: Lakehouse

Serving Layer: SQL Analytics Endpoint + Semantic Model

Visualization: Power BI Report
Project Structure
Earthquake Project
01 Bronze Layer Processing Notebook
02 Silver Layer Processing Notebook
03 Gold Layer Processing Notebook
04 Earthquake Data Ingestion Pipeline
05 Lakehouse (earthquake_lakehouse)
06 SQL Analytics Endpoint
07 Semantic Model (Earthquake_Report)
08 Power BI Report
09 Environment (earthquake_env)

Data Pipeline Flow (Madellion Architecture)

Bronze Layer (Raw Data)
Ingests raw earthquake data from API
Stores unprocessed, schema-flexible data

Ensures data traceability
Silver Layer (Cleaned Data - extraction of longitude, latitude, magnitude data, elevation, place, etc) from raw data and write it up in a table


Standardizes schema and formats
Gold Layer - load up reverse_geocoder in separet env and the convert the latitude and longitued to get the nearest town/city and get country from there
Classify the significance of the earthquake based on magnititude into high, medium or low and load the output into a table

Orchestration
Managed using Fabric Pipelines which automates ingestion and transformation steps
Enables scheduling and monitoring

Reporting
Built using Power BI
Connected to Semantic Model
Provides insights such as:
1. Earthquake frequency by region
2. Magnitude distribution
3. Time-based trends

Key Features
End-to-end ELT pipeline
Medallion architecture implementation
Scalable Lakehouse design
Automated data ingestion based on weekly basis
Integrated analytics and visualization

Technologies Used
Microsoft Fabric
PySpark (Notebooks)
Lakehouse Architecture
SQL Analytics Endpoint

