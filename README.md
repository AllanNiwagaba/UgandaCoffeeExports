# Uganda's Coffee Exports Analysis
## Project Overview

This project analyzes **Uganda’s coffee export performance**. The goal is to analyze trends in export **volumes** and **Export revenue** with insights segmented by coffee type. It also explores the **Top** **Coffee destinations**, **Exporting companies** and **Coffee Buyers**.

The project leverages **Microsoft Excel** for data cleaning and transformation, and **Power BI** for analysis and building interactive dashboards that enable users to explore export patterns over time. By maintaining and updating this project regularly, it serves as a living tool for monitoring Uganda’s coffee trade performance, useful for stakeholders, policy makers and the general public. 

[View dashboard](https://app.powerbi.com/view?r=eyJrIjoiOTJkMDM5ZTMtODJmYS00MWIzLWFiODYtY2ViMzdiODRiMzc0IiwidCI6ImY0OTU4NDAzLTgyZGEtNDYxNC1hNjk2LTI3M2VkMWI4ZTU5OSJ9)

## Data Sources

The Data is sourced from the Uganda Coffee Development Authority (UCDA) website. Specifically this data is extracted from monthly reports (PDF). [Download here](https://ugandacoffee.go.ug/index.php/resource-center/reports/monthly-reports)

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

To derive meaningful insights from the data, I performed various calculations using DAX formulas Power BI as broken down below:

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
  
- **YoY Year Exports Volume**
  ```YoY exports = CALCULATE('Coffee Type Metrics'[TotalQty(60kg bags)],SAMEPERIODLASTYEAR('Calendar'[Date]))```

- **Previous Year Exports Revenue**
  ```prev year Revenue = CALCULATE([Revenue($)],PREVIOUSYEAR('Calendar'[Date]))```

- **YoY% Revenue Growth**
  ```YoY%(Revenue) = DIVIDE(([Value($)]-[PY_Value($)]),[PY_Value($)])```

- **YoY% Exports Volume Growth**
  ```%YoY(Qty) = DIVIDE([TotalQty(60kg bags)]-[Prev.yrCoffeeQty],[Prev.yrCoffeeQty])```

## Findings
### Export Performace overview

- Uganda has exported over 33.08 million 60kg bags of coffee, generating approximately $ 5,343.61 Million in revenue between Jan 2020 and Apr 2025.

- On average, Uganda exports 5.47 million bags with an annual revenue of $ 890.60 million selling at an average unit price of $ 3.36.

- Overall Annual growth, Uganda exported 6.36 million bags of coffee in 2024 compared to 5.49 million bags in 2020, translating to 15.86% increase between 2020 and 2024.

- By Apr 2025, Exports volume had grown by 27.95% YoY, while revenue had grown by 58.24% YoY and the Unit price by 11.53% YoY increase.

- Uganda exported 6.36 million bags in 2024, a 4.01% increase from 2023 and earned $1,547.14 million in revenue, a 60.27% increase from 2023.

- Uganda exported 6.11 million bags in 2023, an 8.67% increase from 2022 and earned $965.33 million in revenue, a 12.32% increase from 2022.

- Uganda exported 5.63 million bags in 2022, a 16.85% decrease from 2021 and earned $859.47 million in revenue, a 19.54 % increase from 2021

- Uganda exported 6.77 million bags in 2021, a 23.28% increase from 2020 and earned $ 718.96 million in revenue, a 39.46% increase from 2020.

- In 2020, Uganda exported 5.49 million bags earning $515.53 million in revenue.

- By destination, Europe received the largest share of Uganda’s coffee exports (64.24% of total volume), followed by Africa (18.2%) and Asia (12.59%) of the total export volumes

- Top countries were Italy (11.5 million bags, 34.92%), Germany (4.24 million bags, 13.24%) and Sudan (3.54 million bags, 10.79%) of the total export volume.

![Dashboard](https://github.com/user-attachments/assets/61859765-d37f-43e0-b33a-10bc8a6928c4)


## Type of Coffee

- Robusta coffee accounts for over 85% of total exports by volume. (28.05 million bags), contributing 85.53% of total volume and $4,315 Million in revenue.

- Arabica, while lower in volume (4.75 million bags), had a significantly higher average unit price ($3.99) compared to Robusta ($2.55).

#### Robusta

- Screen 15 was the most exported (13.23 million bags translating to 40.33% of the total export volume) and 47.16 % of the total Robusta coffee exports.

- Screen 12; 4.3 million bags, 13.10 % of total export volume and 15.32 % of Robusta exports

- Screen 18; 3.93 million bags, 11.97% of total export volume and 13.99% of Robusta exports

##### Destination:

- Italy ~ 10.43 million bags, 37.18%

- Germany ~~ 3.54 million bags, 12.61%

- Sudan ~~ 3.53 million bags, 12.59%

#### Arabica

- Drugar was the most preferred grade with total export volume 2.05 million bags, 6.26% of the total export volume and 43.22 of Arabica export.

- Wugar; 545K bags, 1.66% of the total export volume and 11.50% of Arabica export.

##### Destination:

- Italy ~~ 1.02 million bags, 21.55%

- U.S.A ~~ 624.29K bags, 19.47%

- Germany ~~ 804.21K bags, 16.94%

- Belgium ~~ 526.11K bags, 11.06%

## Monthly Averages

- Overall average, Uganda exports 512.51K bags generating an average revenue of $83.49 million at an average unit price of $3.36.

- Average volume of exports has increased from 457.43K bags in 2020 to 610.85k bags in 2025

![image](https://github.com/user-attachments/assets/d69b54f3-bdb6-484b-8cb2-f044ceb1483d)
  
## Export Trends

 - Export volume and revenue fluctuated year to year

 - Strong growth in 2021, 2023 and 2024.
 
 - Significant declines in 2022


##### Comparing periods (YOY%)
###### Export Volumes

- By April 2025, Uganda recorded a 77.59% YoY increase in exports volume compared to April 2024. This indicates strong year-over-year growth, suggesting exports volume performance has significantly improved over the same period last year.


##### Annual exports volume % age changes

- 2021 (+23.28%): Strong growth compared to the 2020 base year, likely driven by post-pandemic recovery interventions.
- 2022 (−16.85%): A sharp decline, signaling possible operational or market challenges that disrupted the momentum from 2021.
- 2023 (+8.67%): Partial recovery, suggesting some stability returned but not enough to fully rebound from the previous year’s dip.
- 2024 (+4.01%): Growth continued at a slower pace, indicating a possible plateau and the need to refresh growth strategies.

![Annual growth changes](https://github.com/user-attachments/assets/ac841009-dee1-486d-9b74-fd9d68892e71)

###### Export Renevnue & Unit %age  price Changes

- 2021 (Revenue +39.46%, Unit Price +21.29%): Strong revenue growth primarily driven by significant increases in unit prices, likely reflecting favorable global market prices or premium sales.

- 2022 (Revenue +19.54%, Unit Price +33.44%): Revenue grew at a slower pace despite a sharper rise in unit prices, suggesting a decline in volumes sold may have offset the price gains.

- 2023 (Revenue +12.32%, Unit Price −4.12%): Revenue growth continued but slowed down considerably, and was negatively impacted by a drop in unit prices, implying that increased sales volume helped sustain modest growth.

- 2024 (Revenue +60.27%, Unit Price +26.92%): A strong rebound in revenue driven by both volume and price recovery, signaling renewed market demand or export competitiveness.

- 2025 (Revenue +132.06%, Unit Price +48.10%) (partial year): Explosive revenue growth paired with a steep unit price increase suggests an exceptionally strong export performance in early 2025. This trend indicates substantial market gains.

- Overall Average Unit price grew from $ 2.17 in 2020 to $ 5.89 in Apr 2025.

![image](https://github.com/user-attachments/assets/45647788-3f40-4289-a27d-5e3cbcd72094)


##### Seasonality & Export Patterns

  - Monthly export volumes showed seasonal fluctuations, with notable peaks during mid-year (July, Aug) and year-end months (Nov, Dec).
 
  - Early 2025 showed volume peaks as well in Apr.

![image](https://github.com/user-attachments/assets/601f52b6-11de-4f74-84f0-1ba6ba681b8c)


## Export Destinations

  - Europe is the largest market (64.24% of total volume), followed by Africa (18.2%) and Asia (12.59%) of the total export volumes

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
      - Canada - 43.15k bags, 2.74%       
 
## Top Exporters:
- Ugacof (U) Ltd: 4.70 million bags, 14.34%
- Olam Uganda Ltd: 3.23 million bags, 9.84%
- Kyagalanyi coffee Ltd: 2.91 million bags, 8.86%
- Ideal quality Commodities Ltd: 2.86 million bags, 8.72%
- Louis Dreyfus Company (U) Ltd: 2.28 million bags, 6.96%

## Top Buyers:
- Sucafina: 4.49 million bags, 13.69%
- Olam International: 3.54 million bags, 10.79%
- Ecom Agro Industrialist: 1.94 million bags, 5.91%
- How ever, there is a category of “Others” which was not specific, with 4.60 million bags translating to 14.01% of the total export volume.


## Recommendations

###### Diversify Export Markets

- Reduce over-reliance on Europe by growing exports to emerging markets like Asia, North America, and South America.

###### Promote Value Addition

- Encourage domestic processing and branding to command even better prices internationally.

###### Strengthen Exporter-Buyer Relationships

- Support exporters in building long-term contracts with top buyers to ensure stable demand.

###### Leverage Trade Agreements

- Utilize or negotiate trade incentives and tariff reductions in untapped regions, especially Asia and North America.

###### Boost Arabica Production

- Given Arabica’s higher value, investing in quality and productivity could significantly increase export earnings.

## Limitations:
- The data was extracted from pdf reports, and as such could not tell what exactly was comprised in "Others" especially across Buyers
- I was unable to analyze exports by grade across destinations, exporting companies & buyers because the pdf reports lacked these  variables.



  
  


