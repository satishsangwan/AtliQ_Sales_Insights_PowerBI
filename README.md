# AtliQ Sales Insights Project

## About the Company

AtliQ Hardware is a leading supplier of computer hardware and peripherals across India, with its headquarters in New Delhi and regional offices nationwide. Bhavin Patel, the Sales Director, is facing significant challenges in tracking sales due to the rapidly changing market dynamics. This project was undertaken to address these challenges by providing data-driven insights and automating the reporting process to enhance decision-making.

## Problem Statement

The key issue faced by the Sales Director is the inability to efficiently track and analyze sales data in a dynamic market. This project aims to unlock hidden sales insights, reduce manual data gathering, and support the sales team in making informed decisions.

## Project Planning Using AIMS GRID

**Purpose**  
The primary objective is to uncover sales insights that were previously not visible to the sales team, enabling better decision-making. Additionally, the project aims to automate reporting processes, reducing the time spent on manual data gathering.

**Stakeholders**  
- Sales Director  
- Marketing Team  
- Customer Service Team  
- Data & Analytics Team  
- IT Department  

**End Result**  
An automated dashboard that provides up-to-date sales insights, enabling data-driven decision-making.

**Success Criteria**  
- A dashboard that reveals key sales order insights using the latest available data.  
- The sales team is able to make better decisions, leading to a 10% cost saving on total spend.  
- Sales analysts can eliminate manual data gathering, saving 20% of their time, which can be reinvested in value-added activities.

## Project Execution Steps

1. **High-Level Data Analysis**  
   Conducted an initial analysis of the data in SQL to gain a deeper understanding of the dataset.

2. **Data Integration**  
   Connected the SQL dataset to Power BI for further analysis and visualization.

3. **ETL and Data Cleaning**  
   Performed ETL (Extract, Transform, Load) processes and cleaned the imported data to ensure accuracy and consistency.

4. **Data Modeling**  
   Built a data model in Power BI to facilitate the creation of insightful reports.

5. **Measure Creation and Visualization**  
   Developed key DAX measures to meet reporting needs and created visuals in Power BI.

6. **Stakeholder Review and Iteration**  
   After the initial report was reviewed by stakeholders, incorporated their feedback to refine the report.

## Data Overview

- **Number of Transactions**: 150,283  
- **Number of Customers**: 38  
- **Customer Types**: 3  
- **Number of Products**: 279  
- **Product Types**: 3  

## Data Cleaning and ETL

1. **Market Exclusion**  
   Removed Paris and New York markets from the analysis as they were not relevant.

2. **Transaction Filtering**  
   Filtered out transactions with sale amounts of 0 and -1, as they were identified as irrelevant or erroneous.

3. **Currency Standardization**  
   - Removed duplicate currency entries (INR and INR\r, USD and USD\r).  
   - Converted all transaction amounts to INR by applying a conversion factor of 75 for USD transactions.

## Key DAX Measures

1. **Revenue**  
   ```DAX
   Revenue = SUM('sales transactions'[norm_sales_amount])
   
2. **Sales Quantity**  
   ```DAX
   Sales Quantity = SUM('sales transactions'[sales_qty])
   
3. **Revenue Contribution %**  
   ```DAX
   Revenue Contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales customers'),ALL('sales products'), ALL('sales markets')),0)
   
4. **Revenue Last Year**  
   ```DAX
   Revenue Last Year = CALCULATE([Revenue],SAMEPERIODLASTYEAR('sales date'[date]))

5. **Total Profit Margin**  
   ```DAX
   Total Profit Margin= SUM('sales transactions'[profit_margin])
   
6. **Profit Margin %**  
   ```DAX
   Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)
   
7. **Profit Margin Contribution %**  
   ```DAX
   Profit Margin Contribution % = DIVIDE([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales customers'),ALL('sales products'), ALL('sales markets')),0)
   
## Final Deliverable

The final deliverable is a comprehensive Power BI dashboard that provides real-time sales insights, enabling the sales team to make informed decisions quickly. The dashboard has streamlined the reporting process, leading to significant time and cost savings.

[**Live Dashboard Link**](https://app.powerbi.com/view?r=eyJrIjoiNWE1YWI0N2UtNDQ5OS00NDZkLWFmNjAtMjhjNDU5MDdmOTU4IiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)
