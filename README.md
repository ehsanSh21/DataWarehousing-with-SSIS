#  Data Warehousing - Gym and Fitness Center

## An Overview of the Business Domain

Gym and Fitness Center is a place where people go in order to do exercises and build
up their bodies. It offers wide ranges of sport facilities, starting from basic exercising facility like
treadmill to more specific facility like barbell, to satisfy the needs of the customers. 

#### ER Diagram

<img src="https://github.com/ehsanSh21/DataWarehousing-with-SSIS/blob/master/gymOLTP.png" alt="Database Diagram" width="900" height="600">
This ER diagram shows the relationship between each entity for gym and fitness center,
where data flows are, and how they are connected with each other.


### Sales Fact

<img src="https://github.com/ehsanSh21/DataWarehousing-with-SSIS/blob/master/gymSalesDW.png" alt="Database Diagram" width="800" height="600">
The total sales, number of members and number of course sales which derive from
Customer, Branch, Time and Course can be used for analysis the profit of each branch or which
course is the trend. Number of new customer also can be analysed for opening new branch.


### ETL process description

ETL process of extracting data from the database to the data warehouse is done by
using SSIS. Each query selects the data from database and mapping with the
ID of the data warehouse, so we can use those data for analysis. Below is the control flow of the
ETL process.

<img src="https://github.com/ehsanSh21/DataWarehousing-with-SSIS/blob/master/gymSSIS.png" alt="Database Diagram" width="900" height="400">


<b>Dim_Course ETL</b>​ takes the ID, course type, price, and day of the week from Mas_Course.

<b>Dim_Time ETL</b> takes the date of all transactions in Payment.

<b>Dim_Branch ETL</b>​ takes the ID, province, and region from Mas_Branch.

<b>Dim_Customer ETL</b> takes the ID, gender, birthdate, registerdate, and membership type from
Mas_Customer.

<b>Fact_Sales</b> takes the unique key of customer, time, branch, and course from each respective
table, and pay amount and pay date from Tran_Payment.




