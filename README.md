# Uganda's Coffee Exports Analysis
## Project Overview

This project explores **Uganda’s coffee export performance** from **January 2020 to March 2025**, with plans for continuous updates as new data becomes available. The goal is to track trends in export **volumes**, **Export revenue**, **Export destinations**, **Exporting companies** and **Coffee Buyers**. With insights segmented by coffee type & grade of coffee.

The project leverages **Microsoft Excel** for data cleaning and transformation, and **Power BI** for building interactive dashboards that enable users to explore export patterns over time.By maintaining and updating this project regularly, it serves as a living tool for monitoring Uganda’s coffee trade performance—useful for stakeholders, analysts, and policy makers.

## Data Sources

The Data is sourced from the Uganda Coffee Development Authority (UCDA), the official body responsible for regulating and promoting Uganda’s coffee industry.Specifically
this data is extracted from monthly reports (PDF). [Download here](https://ugandacoffee.go.ug/index.php/resource-center/reports/monthly-reports)

## Tools used

- Excel - Data extraction & Cleaning
- Power BI - Data Analysis, Reports & Visualization

## Data Cleaning & Preparation.

In this initial preparatory stage, we performed the following tasks
- Extracted data from tables in PDF files using Excel power query
- Removed errors and nulls.
- Assigned the right data types (Dates, Texts, whole numbers)
- Transformed and combined data across different reporting periods
- Loaded standardized tables to create proper/clean datasets in excel form and stored them in a folder.

## Exploratory Data Analysis

This EDA Process involved the following:
- Used Power BI Power query to connect to the datasets folder. This ensured easy appending of datasets for different periods
- Depulicated the Main Facts table and created dimensions tables (Coffee type, Distinations, Buyers, Exporting companies)
- Used an alreading existing code stored in word to create the calendar table
- Created a star schema model and set up relationships  
