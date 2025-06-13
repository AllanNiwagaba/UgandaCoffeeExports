# Uganda's Coffee Exports Analysis
## Project Overview

This project analyzes **Uganda’s coffee export performance**.The goal is to analyze trends in export **volumes**and **Export revenue** with insights segmented by coffee type. It also explores the **Top** **Coffee destinations**, **Exporting companies** and **Coffee Buyers**.

The project leverages **Microsoft Excel** for data cleaning and transformation, and **Power BI** for analysis and building interactive dashboards that enable users to explore export patterns over time.By maintaining and updating this project regularly, it serves as a living tool for monitoring Uganda’s coffee trade performance, useful for stakeholders, policy makers and the general public.

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
- Created dimensions tables (Coffee type, Distinations, Buyers, Exporting companies)
- Created the calendar table
- Created a star schema model and set up relationships 


## Exploratory Data Analysis (EDA)

This phase involved systematically exploring the dataset to uncover patterns, trends, and key insights. The analysis was guided by the following core questions:

- What is the **total volume** of coffee exported and **total revenue** generated from 2020 to date?
- What is the Coffee exports trend? (monthly, quarterly, annually)?
- What is the **year-over-year (YoY) growth** in export volume and revenue?
- Which **coffee type** (Robusta, Arabica) dominates in terms of volume and revenue contribution?
- What are the **top destinations** for Uganda’s coffee?
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
  
- **Previous Year Exports Volume**
  ```Prev.yrCoffeeQty = CALCULATE('Coffee Type Metrics'[TotalQty(60kg bags)],SAMEPERIODLASTYEAR('Calendar'[Date]))```

- **Previous Year Exports Revenue**
  ```prev year Revenue = CALCULATE([Revenue($)],PREVIOUSYEAR('Calendar'[Date]))```

- **YoY% Revenue Growth**
  ```YoY%(Revenue) = DIVIDE(([Value($)]-[PY_Value($)]),[PY_Value($)])```

- **YoY% Exports Volume Growth**
  ```%YoY(Qty) = DIVIDE([TotalQty(60kg bags)]-[Prev.yrCoffeeQty],[Prev.yrCoffeeQty])```

## Results
### Export Performace overview

- Uganda has exported over 33 Million 60kg bags of coffee, generating approximately $5,343.61 Million in revenue from 2020 to Apr 2025.
- Robusta accounted for the majority of coffee export (28 Million bags), contributing 85.53% of total volume and $4,315 Million in revenue.
- Arabica, while lower in volume, had a significantly higher average unit price ($3.99) compared to Robusta ($2.55).
- Overall, Uganda exported 6.36 million bags of coffee in 2024 compared 5.49 million bags in 2020, an 15.86% increase.

#### Coffee Grades & Types

  - Among Robusta grades, Screen 15 was the most exported, with over 13.23 Million bags, generating $2,087.5 Million in revenue followed by Screen 12 and Screen 18.
  - For Arabica, Drugar was the most exported, with 2.1 million bags generating $434,682,493 in value, followed by Wugar and Bugisu AA

### Export Trends

##### Comparing periods (YOY%)
###### Export Volumes

- By April 2025, Uganda recorded a 77.59% YoY increase in exports volume compared to April 2024. This indicates strong year-over-year growth, suggesting exports volume performance has significantly improved over the same period last year.


##### Annual exports volume growth
- 2021 (+23.28%): Strong growth compared to the 2020 base year, likely driven by post-pandemic recovery interventions.
- 2022 (−16.85%): A sharp decline, signaling possible operational or market challenges that disrupted the momentum from 2021.
- 2023 (+8.67%): Partial recovery, suggesting some stability returned but not enough to fully rebound from the previous year’s dip.
- 2024 (+4.01%): Growth continued at a slower pace, indicating a possible plateau and the need to refresh growth strategies.

###### Export Renevnue & Unit %age  price Changes

- 2021 (Revenue +39.46%, Unit Price +21.29%): Strong revenue growth primarily driven by significant increases in unit prices, likely reflecting favorable global market prices or premium sales.

- 2022 (Revenue +19.54%, Unit Price +33.44%): Revenue grew at a slower pace despite a sharper rise in unit prices, suggesting a decline in volumes sold may have offset the price gains.

- 2023 (Revenue +12.32%, Unit Price −4.12%): Revenue growth continued but slowed down considerably, and was negatively impacted by a drop in unit prices, implying that increased sales volume helped sustain modest growth.

- 2024 (Revenue +60.27%, Unit Price +26.92%): A strong rebound in revenue driven by both volume and price recovery, signaling renewed market demand or export competitiveness.

- 2025 (Revenue +132.06%, Unit Price +48.10%) (partial year): Explosive revenue growth paired with a steep unit price increase suggests an exceptionally strong export performance in early 2025. This trend indicates substantial market gains.

- Overall Average Unit price grew from $ 2.17 in 2020 to $ 5.89 in Apr 2025.

##### Seasonality & Export Patterns

  - Monthly export volumes showed seasonal fluctuations, with notable peaks during mid-year (July, Aug) and year-end months (Nov, Dec).
  - Early 2025 showed volume peaks as well in Apr.


## Export Destinations

  - Europe received the largest share of Uganda’s coffee exports (64.24% of total volume), followed by Africa (18.2%) and Asia (12.59%) of the total export volumes

     #### Europe
    
    Europe had imported 21.07 million bags by Apr 2025:

    ##### Top importing countries
  -  Italy -11.45 million bags, 54.35%
  -  German - 4.34 million bags, 20.61%
  -  Belgium - 1.72 million bags, 8.16% and Sudan(3.5 million bags) were the major destinations of Uganda's coffee

     #### Africa
     Uganda had exported over 5.97 million bags by Apr 2025.

     ##### Top importing countries
     - Sudan - 3.54 million bags, 59.27%
     - Morroco - 1.12 million bags, 18.75%
     - Algeria - 832.92K bags, 13.95%

     #### Asia
     Asia had by Apr 2025 imported 4.13 million bags

     ##### Top importing countries
     - India - 2.67 million bags, 64.76%
     - China - 395.64K bags, 9.58%
     - Isreal - 287.37K bags, 6.96%
   
     #### North America
       North America had imported 1.57 million bags of coffee by Apr 2025

      ##### Top importing countries
      - U.S.A - 1.44 million bags, 91.46%
      - Mexico - 80.24K bags, 5.73%
      - Canada - 43.15k bags, 2.74&
       
 
## Exporters & Buyers
- Top exporting companies included Ugacof (U) Ltd, Olam Uganda Ltd, and Kyagalanyi Coffee Ltd, each shipping over 2 million bags.
- Top Coffee buyers were Sucafina, Olam International, Ecom Agro Industrialist and Volcafe.

## Limitations:


  
  


