# LITA_CAPSTONE_PROJECT-1

### Project Tittle: Sales performance Analysis

### Project overview
This data Analysis Project is done analyse the sales performance of a retail store

#### Data Sources
The primary Source of Data used here is LITA Capstone Dataset.xlsx

### Tools Used
- Microsoft Excel
 1. For Data Cleaning
 2. For Analysis
 3. For Data Visualization
 
- SQL- Structured Query Language for Querying of Data
- Power Bi- for creating Dashboard
  
### Data Cleaning and Praparation
 In this process,duplicates were Removed, the Data was filtered and sorted

 ### Exploratory Data Analysis
 The data was explored to deduce the following:
 - Top selling products
 - Regional performance
 - Monthly sales trend

### Pivot Tables
These Pivot Tables Summarizes The Total sales Made on each Product, in each Region and each Month
![Sales Pivot Table](https://github.com/user-attachments/assets/0a6edf40-f438-4eba-8e39-6cd635311665)

### Average Sales By Product and Total Revenue By Region
The Average sales that was made on each product was calculated using the AVERAGEIF Function and the Total Revenue Made in each Region was calculated using the SUM Function
![Screenshot 2024-11-03 225341 tables](https://github.com/user-attachments/assets/c2fd797a-e593-4cf3-82de-4fbc314025c4)

### SQL
using Sql, the following queries were used to retrive some information

### Total sales for each product
Select 
	Product,
	SUM(Revenue) AS TotalSales
FROM 
	[dbo].[sales data 2]
GROUP BY 
        Product
ORDER BY 
	TotalSales Desc
 The total sales of each product can be seen in the visuals
 
 ### Number Of Sales Transaction In Each Region
SELECT
	Region,
	COUNT(*) AS NoOfSalesTransactions
FROM
	[dbo].[sales data 2]
GROUP BY 
	Region
ORDER BY Noofsalestransactions

![number of sales transaction](https://github.com/user-attachments/assets/893ac723-f46b-4df9-9f5a-0d0b0aeecad0)
 
 ### The highest-selling products by total sales value
	Select top 1 
	Product,
	SUM(Revenue) AS TotalSales
FROM 
	[dbo].[sales data 2]
GROUP BY 
	Product
ORDER BY 
	TotalSales Desc

![highest selling product by sales value](https://github.com/user-attachments/assets/324586a0-6021-4941-92a7-1b682cff7bcc)

 ### Total revenue by product
	Select 
	Product,
	SUM(Revenue) AS TotalSales
FROM 
	[dbo].[sales data 2]
GROUP BY 
	Product
ORDER BY 
	TotalSales Desc


 ### Monthly sales Totals for the current year
	select Datename(month, orderdate) as months, sum (Revenue) as totalsales
	from [dbo].[sales data 2]
	where year(orderdate) = year(getdate())
	group by month (orderdate),orderdate
	order by totalsales desc
 ![monthly sales for the current year](https://github.com/user-attachments/assets/42f4b740-e6e6-4ee7-b253-03fe75134c4e)

 
### Top 5 customers by total purchase amount
Select Top 5 Customer_ID, Sum (quantity) as Total_Purchase
from[dbo].[sales data 2]
group by Customer_ID
Order by Total_purchase desc

![sql](https://github.com/user-attachments/assets/f79d4720-08b9-4d07-a317-74002894a3ed)

### percentage of total sales contributed by each Region
Select Region, sum(Revenue)/sum(Quantity*unitprice)*0.1 As percentage_of_Total_Sales
from[dbo].[sales data 2]
group by Region
order by percentage_of_total_sales

![percentage of sales](https://github.com/user-attachments/assets/cb047b00-2a28-406e-9e5c-44467c10453d)

### Products with no sales
select product, sum(Quantity) as sales from[dbo].[sales data 2]
where Month(orderdate)Between 10 and 12
group by product having sum(quantity)=0

![products with no sales](https://github.com/user-attachments/assets/d3

### Dasshboard And Visuals
using Power Bi, A Dashboard Showing the Sum of Total Sales by Product, Sum of Revenue per Month and sum of Total Sales by Region
![Dashboard 1](https://github.com/user-attachments/assets/3711cf1e-7338-4db2-a66c-5d0048e89212)

The following are visual representations of the findings made. 
For the products, The HIghest total sales were gotten from shoes and hieghest sales was made in the East



