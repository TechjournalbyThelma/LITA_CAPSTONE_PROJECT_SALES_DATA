LITA_CAPSTONE_PROJECT-SALES-DATA
Referring to the Capstone Project Document, carry out the following exploratory process and tell a compelling story by building an interactive dashboard report to gather insight and make business decisions.

OUTLINE
[ PROJECT OVERVIEW: ].(project-overview)

[DATA DESCRIPTION:].(data-description)

[DASH BOARD REVIEW:].(dashboard-review)

[STATISTICS ABOUT THE DATASET:].(statistics about the dataset)

[METHODOLOGY:].(methodology)

[DATA ANALYSIS:].(data-analysis)

[DASHBOARD OVERVIEW WITH POWERBI:].(dashboard overview with powerbi)

[INSIGHTS GENERATION:].(insights generation)

[RECOMMENDATION:].(recommendation)

[CONCLUSION:].(conclusion) 

PROJECT OVERVIEW:
Making reference to the data and capstone project document shared earlier, by analyzing the sales performance of a retail store and carrying out the following exploratory process of the sales data to uncover key insights such as

Top Selling Products
Regional Performances
Monthly Sales trends and By telling a compelling story and building an interactive dashboard Power BI report: To gather insight, Highlight findings And make business decisions.

DATA DESCRIPTION:
This dataset includes the following Columns:

Order Number
Customer Id
products
region
Order Date
Quantity
Unit Price

DASH BOARD REVIEW:
•	Customer Id
•	products: Items sold in the store
•	region: The other regional branches of the store ( North, South, East West)
•	Order Date: The date the order was placed
•	Quantity: The number of units of the product ordered in each transaction
•	Unit Price: The acquisition cost per unit of the product
STATISTICS ABOUT THE DATA:
•	Number of Unique Customers: 50,000
•	Number of Products: 6
•	Total Sales: 10,587,500
•	Total Region: 4
METHODOLOGY:
Data Collection
LITA_ The Incubator Hub provided the dataset for this analysis for learning and training purposes. The data was provided in an Excel sheet [download Here].(https://canvas.instructure.com/files/273182802/download?download_frd=1) The Excel sheet made it accessible to analyze the Excel sheet The Excel sheet was further converted to CSV format for easy importing of files into:
•	SQL to write various queries
•	Power BI to create dashboards using various charts (PieChart and clustered Column Chart)
DATA ANALYSIS:
Calculation in Excel
•	Generating Total Sales (=F2*G2)

![image](https://github.com/user-attachments/assets/5350df93-930d-4ebb-8524-29624ce9ccbc)

•	calculating average sales by product =AVERAGEIF($C1:$C50001,$C2,$H1:$H50001)
![image](https://github.com/user-attachments/assets/eef9dc2a-7f33-4c9f-89e1-8317e8205d56)

•	calculating total revenue by region ==SUMIF($D1:$D50001,$D12630,$H1:$H50001)
![image](https://github.com/user-attachments/assets/78dae6d2-5498-4b12-ab5b-c782a478a54b)

Excel Chart
![image](https://github.com/user-attachments/assets/9ce09303-6f17-4654-b4d2-ffc6c1854120)
![image](https://github.com/user-attachments/assets/b59c11f5-2faa-4d76-a1f4-8babbcf7dcad)

Pivot Table
![image](https://github.com/user-attachments/assets/097eeda2-58a9-42ec-9cc0-557da7648fe3)

Queries in SQL
1. select product, sum (Quantity) as Quantity_Revenue from [dbo].[Sales data]
   Group by product
2. select Region, count (customer_id) as sales_by_region from [dbo].[Sales data]
   Group by Region
3. select product, sum (Total_sales) as product_total_sales from [dbo].[Sales data]
   Group by product
   order by product_total_sales desc
4. select orderdate, sum (Total_sales) as Totalsales from [dbo].[Sales data]
   where orderdate >='2024-01-01'
   group by orderdate
5. select customer_id, sum (Total_sales) as Totalsales from [dbo].[Sales data]
   group by customer_id
   order by Totalsales desc
6. SELECT Region, SUM(Total_sales) AS RegionalSales, 
   (SUM(Total_sales) / CAST((SELECT SUM(Total_sales) FROM [dbo].[Sales data])
   AS DECIMAL(10, 2)) * 100) AS SalesPercentage
   FROM [dbo].[Sales data]
   GROUP BY Region
7. SELECT DISTINCT  Product FROM [dbo].[Sales data]
   WHERE product Not In (select product from [dbo].[Sales data]
   Where OrderDate >= dateadd (quarter, -1, getdate ()) )

  DASH BOARD OVERVIEW WITH POWER BI:
 ![image](https://github.com/user-attachments/assets/3704db3a-068c-48a1-acd7-19a44cad87bf)

 INSIGHTS GENERATION:
 Regional Sales Performance
1.	South Region: Leads with $4,675,000 in sales (44% of total revenue), indicating high transaction values.
2.	East Region: $2,450,000 (23.14% of total sales), showing strong competition.
3.	North Region: $1,950,000 (18.42% of total sales), demonstrating consistent customer interest.
4.	West Region: $1,512,500 (14.29% of total revenue), indicating steady purchasing activity.
Product Revenue Breakdown
1.	Shoes: $3,087,500 (29% of total revenue), suggesting higher pricing or larger sales volumes.
2.	Shirts: $2,450,000 (23.14% of total sales), indicating strong demand and second-best-selling product.
3.	Other products contribute to the remaining revenue.
Actionable Recommendations
1.	South Region: Investigate factors driving high sales (marketing strategies, customer demographics).
2.	Product Pricing: Analyze pricing strategies for shoes and shirts to optimize profitability.
3.	East and North Regions: Implement targeted marketing campaigns to leverage competitive markets.
4.	West Region: Maintain competitive strategies to sustain purchasing activity.
5.	Product Portfolio: Expand shoe and shirt offerings based on demand.
Data Visualization Suggestions
1.	Regional sales: Bar chart or map visualization.
2.	Product revenue: Pie chart or stacked bar chart.
3.	Sales distribution: Histogram or density plot.
Additional Analysis
1.	Seasonal sales fluctuations.
2.	Customer demographics and purchasing habits.
3.	Product category expansion opportunities.
4.	Regional market trends.
5.	Customer retention strategies.

Action Plan
Short-term (0-3 months)
1.	Conduct regional market research.
2.	Develop targeted marketing campaigns.
3.	Adjust inventory to reflect demand.
Mid-term (4-6 months)
1.	Monitor campaign effectiveness.
2.	Analyze sales trends.
3.	Refine marketing strategies.
Long-term (7-12 months)
1.	Evaluate regional revenue growth.
2.	Expand product offerings based on demand.
3.	Continuously assess market trends.
Key Performance Indicators (KPIs)
1.	Sales growth in North and West regions.
2.	Revenue increase from shoes and shirts.
3.	Customer engagement and retention.

 






