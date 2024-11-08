# SALES PERFOMANCE ANALYSIS PROJECT
## Table Of Contents
[Introduction](#introduction)

[Data Sources](#data-sources)

[Tools](#tools-used)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Results](#results)

[Recommendations](#recommendations)

[Limitations](#limitations)

[Conclusions](#conclusions)
### INTRODUCTION

This repository contains an Excel-based data analysis project focused on the understanding sales trends and patterns within a retail store dataset. The projects provides insights through data cleaning, visualization, dashboard creation. The Dataset is made up of 9 columns and 9922 rows. The columns include: 

- OrderID: This is a unique identifier assigned to a customer's order transaction.

- CustomerID: This is a unique identifiier assigned to a customer, used to track and manage customer interactions,transactions, and relationships.

- Product: This is a tangible or intangible item that satisfies customer needs, wants, or desires, and is offered for sal, trade, or exchange.

- Region: A geographic area defined by physical or administrative boundaries, used to organize and analyze data, manage operation, or target markets.

- Orderdate: The date when a customer places an order or purchase a product or service.

- Quantity: The amount of numberof items, units, or products.

- Unit Price: The price of a single unit of a product or service.

- Total Sales: The aggregate amount of sales revenue generated by a buisness of organization over a specific period.

- ```Total Sales
  Sum(Unit Price * Quantity Sold)
  ```
  
-Average Sales: The total sales revenue divided by the number of sales transactions or units sold, over a specific period.

  ```Average Sales
  Total Sales/Number of Transactions
  ```

  ### Data Sources
  The Primary Datasets used for this analysis is the https://drive.google.com/file/d/1Kg08Ogdvc05chhLHBC2EXTlpeqZzqUsu/view?usp=drive_link file,containing detailed information about 
 each sales made by the retail store.

  ### Tools Used
  -Microsoft Excel- This was used for Data Cleaning and also Data Visulization
  -SQL Server- This was used for Data Analysis
  -Power Bi- This was used for creating reports.

  ### Data Cleaning/Preparation
  
  -Steps Involved includes:
  1. Data Importation (Collected and imported data from various sources)
  2. Data Profiling
  3. Data Validation (Checked for null values)
  4. Data Transformation (Performed Data Calculations)
  5. Error Detection (identification of Duplicate records)

### Exploratory Data Analysis

EDA involved the sales data to answer key questions, such as:

- What is the Total Sales for each product.
- What is the Total number of Sales in each Region.
- What is the Highest Product by Total Sales Value.
- What is the Total monthly sales for the current year.
- What are the top 5 customers by total purchase amount.
- What is the percentage of total sales contributed by each region.
- What are the products with no sales in the last quarter.

### Data Analysis

Used SQL Server for the Data Analysis and the code used to answer the Key questions above include the following:

```SQL
Select * from  [dbo].[OYEMADE LITACSV]
-TOTAL SALES FOR EACH PRODUCT
 Select sum(TOTAL_SALES) AS Totalsalesbyproduct, Product
from [dbo].[OYEMADE LITACSV]
Group By Product
```

-TOTAL NUMBER OF SALES IN EACH REGION
```Sql
select Region, Count(*) as NumberOfSales
from [dbo].[OYEMADE LITACSV]
group by Region
order by Region
```
-HIGHEST PRODUCT BY TOTAL SALES VALUE
```
Select Max(TOTAL_SALES) as HighestSellingProduct, Product
from [dbo].[OYEMADE LITACSV]
Group By Product 
Order By HighestSellingProduct DESC
```
-TOTAL MONTHLY SALES FOR THE CURRENT YEAR
```
Select
year (OrderDate)  as Year,
month (OrderDate) as Month,
sum (TOTAL_SALES) as TotalSales 
from [dbo].[OYEMADE LITACSV]
where Year(OrderDate)=2024
Group By
year (OrderDate),
month (OrderDate)
Order by
year (OrderDate),
month (OrderDate)
```
-TOP 5 CUSTOMERS BY TOTAL PURCHASE AMOUNT
```
Select Top 5
Customer_Id,
Sum(TOTAL_SALES) as TotalAmount
From [dbo].[OYEMADE LITACSV]
Group By 
Customer_Id
Order By 
TotalAmount DESC
```
-Product with no Sales
```
Select Product, Customer_Id
From [dbo].[OYEMADE LITACSV]
Where Product NOT IN (Select Product from [dbo].[OYEMADE LITACSV]);
```

### Results
- The shoes are the top-selling product, while socks have the lowest sales.
  
  ![TOTAL SALES BY PRODUCT(1)](https://github.com/user-attachments/assets/ce718da3-2cdd-4492-a83d-6b61e06b6b76)

-The East region has the highest sales, while the West region has the lowest, with only a slight difference between them.

  ![TOTAL SALES BY REGION(2)](https://github.com/user-attachments/assets/2c472dc3-4a9e-4b20-9698-8906c66914c8)

  - When comparing the months, the highest sales in 2023 occurred in February, while the lowest were recorded in August. In 2024, the highest sales so far happened in July, based on the most recent data update in August.

- Looking at both years, 2024 has demonstrated stronger sales performance than 2023.

![months and year](https://github.com/user-attachments/assets/2b3ec3a2-e0be-4d85-b802-b746d317b94b)

![months and year 002](https://github.com/user-attachments/assets/7eacd163-541d-4bb8-a3d2-29ce90c75f2f)

![months and year 003](https://github.com/user-attachments/assets/e7e17bdc-0214-4359-b656-ad74b23719fa)

### Recommendations

- Use shoes as a gateway product to attract more customers and create brand loyalty.
- Offer discounts or bundle socks with shoes to encourage purchases.
- Try to replicate East region marketing tactics in other regions, especially the West.
- Focus on maximizing sales in high-performing months like February and July, and plan targeted campaigns for low-performing months like 
  August.
- Implement seasonal promotions around key sales periods.
- Focus on customer and retention with loyalty programs and personalized offers to sustain momentum.

### Limitations
Sales data for the past two years were incomplete, as the data for 2024 only covers up to August, making a full-year comparison between 
 2023 and 2024 challenging.
 
 ### Conclusions
 There is a strong likelihood that 2024 sales will surpass those of 2023 by the end of the year, as the total sales for 2023 reached 
 1,105,330 by December, while 2024's sales stand at 995,760, with only a 108,750 difference.











  
  



