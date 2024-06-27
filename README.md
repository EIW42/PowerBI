# Shopee Latin America

### Dashboard Link : https://app.powerbi.com/groups/me/reports/384d017e-e935-44dc-9e7d-1626c1a36de1/ReportSection
## Problem Statement

This dashboard showcases business analysis for Shopee in the Latin America market, in the countries - Brazil, Chile, Colombia and Mexico. This dashboard is created in the pages of 1.Executive Summary , 2.Sales Analysis, 3.Customer Analysis , 4.Conclusions and finally 5.Recommendations, and with an Appendix page. 

In this analysis report, we aim to achieve an enhancement of Shopee customers’  experience and to recommend relevant products and thereby increasing revenue. To make an informed decision-making, we will be examining 3 years' worth of data^ (2020 - 2022) comprising of two key datasets - 1. the customer dataset and 2. the customer purchase dataset. 

Overall sales performance of the Latin America Market, y-o-y sales performance and a trend analysis of the sales performance will be analysed. Discounts offered to products are categorised to perform analysis to see if there is a relationship between discount and sales.

For an insight of the customer, analysis of customer purchases are made with interplaying factors such as income, age and gender. 

Upon completion of the analysis, in the Conclusions page, 3 key takeaways are made and with recommendations for the business. 

^Data used are not real data. They are simulated for the purpose of this exercise.
 

 
### Steps followed for ETL:

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : Using the discount column, new column to represent discount_bracket  was created. The date type set as text. Dax expression was written as follow:
        
Discount Bracket:

if [discount] <= 0.05 then "0-5%"
else if [discount] <= 0.1 then "6-10%"
else if [discount] <= 0.2 then "11-20%"
else if [discount] <= 0.3 then "21-30%" 
else if [discount] <= 0.4 then "31-40%"
else if [discount] <= 0.5 then "41-50%"
else "Above 50%" 

- Step 6 : To create an organised flow of Discount Bracket, Discount Bracket Order was created using Dax expression as follow:

Discount Bracket Order:

if [discount_bracket] <= 0-5 then "1"
else if [discount_bracket] <= 6-10 then "2"
else if [discount_bracket] <= 11-20 then "3"
else if [discount_bracket] <= 21-30 then "4" 
else if [discount_bracket] <= 31-40 then "5"
else if [discount_bracket] <= 41-50 then "6"
else "7"


 - Step 7 : Using the age column, new column for age_group was created using Add Column ribbon, Conditional Column, Add Conditional Column. Data type set as text.
- Step 8 : Using the age_group column, new column for age_category was created using Add Column ribbon, Conditional Column, Add Conditional Column. Data type set as text.

Age Group and Age Category created: 


-- Young adults  between the age of 18-24,

-- Early career adults between the age of 25-34,

-- Established adults between the age of 35-44

-- Middle-age adults between the age of 45-54

-- Pre-retirement adults between the ages of 55-64

-- Seniors who are 65 and above


- Step 8 : Using income column, new column for income_group was created. Dax expression as follow:

Income Group:

if [Income] <= 25000 then "Low Income" 
else if [Income] <= 50000 then "Lower-Middle Income" 
else if [Income] <= 75000 then "Middle Income" 
else if [Income] <= 100000 then "Upper-Middle Income" 
else if [Income] <= 150000 then "High Income" 
else if [Income] <= 200000 then "Very High Income" 
else "Ultra High Income"


### Steps followed for report formatting:
- Step 1 : In the report view, Shopee corporate colours were used and Shopee logo was inserted across the pages.

Primary Colors
Orange: #FF5722

White: #FFFFFF

Secondary Colors (example variations)

Gray: #9E9E9E (for text and secondary elements)

Black: #000000 (for primary text and high contrast elements)

- Step 2 : At the cover page, bookmarks was created for each analysis page 
- Step 3 : At the cover page, buttons was created and under Action, Page Navigation and Destination were set accordingly. 





 

