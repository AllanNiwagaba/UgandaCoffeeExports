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

### Transformation & Modelling - Power BI

This EDA Process involved the following:
- Used Power BI Power query to connect to the datasets folder. This ensured easy appending of datasets for different periods
- Depulicated the Main Facts table and created dimensions tables (Coffee type, Distinations, Buyers, Exporting companies)
- Used an alreading existing code stored in word to create the calendar table
- Created a star schema model and set up relationships 


## Exploratory Data Analysis (EDA)

This phase involved systematically exploring the dataset to uncover patterns, trends, and key insights. The analysis was guided by the following core questions:

- What is the **total volume** of coffee exported and **total revenue** generated from 2020 to date?
- How has coffee **export performance evolved over time** (monthly, quarterly, annually)?
- What is the **compound annual growth rate** or year-over-year (YoY) growth in export volume and revenue?
- Which **coffee type** (Robusta, Arabica) dominates in terms of volume and revenue contribution?
- How are coffee exports distributed across **continents** and **countries**?
- What are the **top destination countries** for Uganda’s coffee exports?
- How do **average unit prices** vary across coffee types and years?
- Which **grades** of coffee (Screen 15, Drugar, Wugar, etc) contribute most to export value and quantity?
- Who are the **leading exporters** of Uganda's coffee?
- Which **buyers** consistently purchase Uganda’s coffee in high volumes?
- Are there any **seasonal patterns** in coffee export volumes, unit price and export revenue?

## The Analysis Process - Calculations & Analytical Logic

To derive meaningful insights from the data,I performed various calculations using DAX formulas Power BI as broken down below:

- **Total Volume**
```Quantity (60kg Bags) = SUM('Coffee Exports Data'[Qty (60kg bags)])```

- **Coffee Revenue**
  ```Revenue ($ million) = SUM('Coffee Type'[Value ($)])```

- **No. of Export Years**
  ```No of years = DISTINCTCOUNT('Calendar'[Year])```

- **No. of Export Months**
  ```Number of Months = DISTINCTCOUNT('Calendar'[YearMonth])```

- **Annual Export Volume**
  ```AvgAnnualExport = DIVIDE([Coffee Export (Qty)], [No. of years])```

- **Annual Export Revenue**
  ```Avg Annual Revenue = DIVIDE([Value($)], [No. of years])```

- **Average Monthly Export Volume**
  ```AvgMonthlyExport = DIVIDE(Quantity (60kg Bags)],DISTINCTCOUNT('Calendar'[YearMonth]))```

- **Average Monthly Revenue**
  ```AvgMonthlyRevenue = DIVIDE([Revenue($)],DISTINCTCOUNT('Calendar'[YearMonth]))```

- **Average Unit Price**
  ```AvgUnitPrice = AVERAGE('Coffee Type'[Unit Price])```
  
  


