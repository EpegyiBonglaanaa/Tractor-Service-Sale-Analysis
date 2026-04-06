# Tractor Service Sale Analysis
## Table of Content

•	[Project Overview](#project-overview)

•	[Data Sources](#data-sources)

•	[Tools](#tools)

•	[Data Cleaning and Preparation](#data-cleaning-and-preparation)

•	[Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)

•	[Data Analysis](#data-analysis)

•	[Dashboard Report](#dashboard-report)

•	[Findings / Results](#findings--results)

•	[Recommendations](#recommendations)

## Project Overview
This data analysis aims to provide insights into the threshing sales performance of a tractor service delivery company for the season 2025. By analyzing various sale variables, I seek to identify trends, make data driven recommendations, and gain a deeper knowledge of the company’s performances.

## Data Sources
Sales Data: The primary dataset used for this analysis is “TECAS Sale Data_Threshing 2025.xlsx”, which contains detailed information about where sales went to and who made the sales. 

## Tools
- Excel – Data Cleaning
- MySQL – Data Analysis
- Power BI – Creating report [Download for Free Here](https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads?ocid=ORSEARCH_Bing&msockid=2c328bbf2b3167101ab79c8d2ab46616)

## Data Cleaning and Preparation
1.	Error Correction
    - Fix typos in names, dates,
    - Fix misclassified entries
      
2.	Data Validation & Integrity Checks
    - Verify data types (dates, numeric)
    - Check for invalid entries (e.g. negative amounts, impossible dates)
    - Ensure consistent units (e.g. kg, GHS formatting)
  
3.	Handling Missing Data
    - Identify missing values (NULLs, blanks): Fill or remove them, whichever is necessary.
4.	Standardizing Data Formats
    - Dates → consistent format (mm/dd/yyyy)
    - Text → uniform casing (UPPER/Proper case)
    - Categories → unify labels 
        - Example: “Maize”, “maize” → “Maize”

## Exploratory Data Analysis (EDA)

EDA revolve around exploring the service delivery data to answer some key questions such as:
- Which product got sold more?
- Which operator made the largest sale?
- What month recorded the peak sale volume?
- Who is the largest value chain partner in 2025?
  
## Data Analysis
```sql
SELECT
    Commodity,
    SUM(Sale_Quantity) AS Total_Quantity
FROM
    `TECAS Sale Data_Threshing 2025`
WHERE
    Month = 11
    AND Name_of_Op LIKE '%Ashraf%'
GROUP BY
    Commodity;
```


**What the code does:** This query filters the dataset to include only records from November (Month = 11) where the operator’s name contains “Ashraf,” and then groups the results by commodity. It calculates the total quantity sold for each commodity by summing the Sale_Quantity values within each group. The final output is a summarized table showing how much of each commodity (e.g., maize, soya) Ashraf sold during that month, making it useful for performance tracking and reporting.

## Dashboard Report
<img width="1307" height="847" alt="Analysis Dashboard_2" src="https://github.com/user-attachments/assets/10efc599-f007-4935-b4c8-4ce8fcb311e2" />


## Findings / Results
- The company made more sales of the produce gathered from the service delivery in December 2025, the peak month for the activity.
- The company made more sales of the produce gathered from the service delivery in December 2025, the peak month for the activity.
- The tractor operator who made the largest sale in services delivery for the period under study is “Ashraf”
- December recorded the peak sale volume overall for the season.
- Looking at the volume of commodities in ‘kg” bought by buyers, Salifu Yahaya is our largest sale partner for 2024 and there is a reason; cold be that he is an aggregator, poultry farmer, or a processor.

## Recommendations
Based on the analysis, I recommend the following:
•	Soya covers the larger proportion of sale volumes meanwhile maize is widely grown in the region, so a market analysis needs to conducted to find out the cause and devise strategies to get the optimum share of both commodities in our operation.
•	Implement buyer segmentation to group top buyers for effective sale targeting

## Limitation
NA
