# 🏦 Banking Data Warehouse & Power BI Financial Analytics

## 📌 Project Overview

The Banking Data Warehouse & Power BI Financial Analytics project is an end-to-end data analytics and business intelligence project developed using Excel/CSV, SQL, SQL Server, Data Warehousing concepts, Data Modeling, Power BI, and DAX. The main objective of this project is to transform a simple flat banking dataset into a structured Data Warehouse and then use the warehouse as the source for an interactive Power BI reporting solution. The project demonstrates the complete journey of data from a raw source file to a structured SQL Server Data Warehouse and finally to business-oriented dashboards in Power BI.

The project started with a banking master flat file containing approximately 40,000 customer records and multiple banking-related attributes. The source file contains information related to customers, accounts, branches, loans, deposits, withdrawals, transfers, transaction activity, customer segments, occupations, locations, and other banking metrics. Since all these business areas were initially available in a flat-file structure, the data was analyzed and organized into separate logical entities to make it more suitable for reporting and analytical purposes.

## 🎯 Project Objective

The main objective of this project is to build a structured banking Data Warehouse using SQL Server and use that warehouse to develop an interactive Power BI financial analytics solution. Instead of directly connecting the raw Excel/CSV file to Power BI, the source data was first loaded and processed in SQL Server. The data was then transformed into business-oriented tables with appropriate relationships between customers, accounts, branches, loans, transactions, and dates. After completing the Data Warehouse layer, the SQL Server database was connected to Power BI for data modeling, DAX calculations, KPI creation, and visualization.

## 🔄 Data Flow

The complete project follows an end-to-end data pipeline. The process begins with the raw Excel/CSV banking file, followed by data understanding, data cleaning, and transformation. The processed data is then stored and structured in SQL Server. Business entities are separated into dimension and fact tables, and relationships are established using primary keys and foreign keys. A date dimension is also included to support time-based analysis. Once the Data Warehouse is completed, the SQL Server database is imported into Power BI, where the data model is prepared and DAX measures are created. Finally, the data is presented through interactive dashboards that provide customer, branch, transaction, and financial analysis.

The overall architecture of the project can be represented as:

Excel / CSV Source Data → SQL Server → Data Transformation → Data Warehouse → Fact & Dimension Tables → Power BI Data Model → DAX Measures → Interactive Financial Dashboards

## 🗄️ Data Warehouse Development

The Data Warehouse is the core part of this project. The original banking master file contained multiple business processes within one flat structure. To make the data easier to manage and analyze, the data was separated into logical business entities in SQL Server. The warehouse includes customer, account, branch, loan, transaction, and date-related tables. The major tables used in the project include Customers, Accounts, Branches, Loans, Transection, Dim_Date, Fact_Bank_Transaction, and Fact_Bank_Loan.

The Customers table is used to maintain customer-related information such as customer identity, gender, age, location, occupation, and customer segment. The Accounts table contains account-related information such as account type, account opening details, account count, and balance-related information. The Branches table is used to maintain branch information and support branch-level analysis. The Loans table contains information related to loan types, loan amounts, interest rates, and loan status. The Dim_Date table provides a dedicated date structure for performing time-based analysis in Power BI.

## 📊 Fact Tables

The project contains fact tables to represent measurable banking activities. The Fact_Bank_Transaction table is designed to support transaction-related analysis. It contains measurable information such as total deposits, total withdrawals, total transfers, transaction counts, failed transactions, and transaction-related metrics. This table allows the Power BI report to analyze the movement and activity of banking transactions across customers, branches, locations, channels, and time periods.

The Fact_Bank_Loan table is used to support loan-related analysis. It contains measurable loan information such as loan amounts and other loan-related metrics while connecting the loan activity with relevant dimensions such as customers, branches, loan types, and dates. This structure makes it possible to analyze the bank's loan portfolio from different business perspectives.

## 🔑 Data Modeling

Data modeling was an important part of the project because the source data originally existed as a flat file. The Data Warehouse was structured using fact and dimension concepts so that the data could be efficiently consumed by Power BI. Primary keys and foreign keys were used to establish relationships between the tables. A dedicated date dimension was created to support time-based reporting and trend analysis.

The model allows business users to move from high-level financial metrics to detailed analysis based on customers, branches, locations, transaction activity, loan information, and time. This approach also provides a structured foundation for creating DAX measures and interactive Power BI reports.

## 📈 Power BI Development

After completing the SQL Server Data Warehouse, the SQL Server data was connected to Power BI. The Power BI report was designed as an interactive financial analysis solution rather than a single dashboard. The report contains multiple pages, with each page focusing on a different area of banking analysis. Navigation buttons were also created so users can move between the Main Dashboard, Customer Analysis, Branch Analysis, and Transaction Analysis pages.

The Main Dashboard provides an executive-level overview of the banking data. It contains important KPIs such as the total number of customers, total financial amount, total deposits, total withdrawals, total transfers, and failed transactions. The page also acts as the starting point of the report and provides navigation to the other analytical pages.

## 👥 Customer Analysis

The Customer Analysis page focuses on understanding customer behavior and customer demographics. The page provides analysis based on occupation, gender, customer segment, location, and transaction activity. It includes a transaction-by-occupation visualization that compares transaction activity across different occupations. A gender-based transaction visualization is used to compare male and female transaction activity, while a deposit-versus-withdrawal analysis provides a comparison of financial activity by gender.

The page also contains customer segment analysis, which allows the distribution of customers across different segments to be examined. Interactive slicers for State, City, and Occupation allow users to filter the report and analyze customer behavior for specific locations or occupations.

![Customer Analysis](assets/customer-analysis.png)

## 🏢 Branch Analysis

The Branch Analysis page focuses on understanding banking activity across branches and different time periods. The page contains visualizations for deposit activity by day and cash deposit activity by month. It also provides transaction analysis by gender and a breakdown of preferred banking channels such as ATM, Branch, Internet Banking, Mobile App, and UPI.

Interactive filters are available for Year, Month, and Branch Name. These filters allow users to select a particular year, month, or branch and analyze the corresponding banking activity. This page is designed to provide a branch-level and time-based view of financial activity.

![Branch Analysis](assets/branch-analysis.png)

## 💰 Transaction Analysis

The Transaction Analysis page focuses on the overall movement of money through the banking system. The page compares total deposits, withdrawals, and transfers and provides a detailed view of transaction activity across different days and months. A state-level table is also included to compare total deposits, transfers, and withdrawals across different states.

The page contains monthly trend analysis that helps users understand how deposits, withdrawals, and transfers change over time. This provides a broader view of financial activity and allows users to identify changes in money movement across different periods.

![Transaction Analysis](assets/transaction-analysis.png)

## 🏦 Main Dashboard

The Main Dashboard acts as the executive overview of the entire Power BI report. It presents the most important financial KPIs in a single view, including approximately 40K customers, total financial amount, deposits, withdrawals, transfers, and failed transactions based on the project dataset. The page also provides navigation buttons that allow users to move to Customer Analysis, Branch Analysis, and Transaction Analysis.

![Main Dashboard](assets/main-dashboard.png)

## 📐 DAX and KPI Development

DAX was used in Power BI to create analytical measures and calculate important banking KPIs. Measures were created for total deposits, total withdrawals, total transfers, total transactions, failed transactions, and customer counts. These measures are used throughout the report to create KPI cards, charts, tables, and trend analysis.

For example, the Total Deposits measure is calculated using the transaction fact table, while the Total Customers measure uses a distinct customer count. Additional calculated measures can be developed to analyze net money flow, month-over-month changes, year-over-year growth, average transaction values, and other business metrics.

## 💡 Business Analysis

The completed solution provides a centralized analytical view of banking activity. The report can be used to understand the customer base, analyze customer segments, compare transaction activity across occupations and genders, examine branch performance, analyze deposits and withdrawals, understand transaction channels, evaluate loan activity, and study the movement of money over time.

The project demonstrates how raw business data can be converted into meaningful business information by combining SQL Server Data Warehousing with Power BI Business Intelligence capabilities.

## 🖼️ Power BI Dashboard Screenshots

The Power BI report contains four major analytical views. The Main Dashboard provides the overall financial summary, the Customer Analysis page focuses on customer behavior and demographics, the Branch Analysis page focuses on branch and channel activity, and the Transaction Analysis page provides detailed financial transaction analysis.

### Main Dashboard

![Main Dashboard](assets/main-dashboard.png)

### Customer Analysis

![Customer Analysis](assets/customer-analysis.png)

### Branch Analysis

![Branch Analysis](assets/branch-analysis.png)

### Transaction Analysis

![Transaction Analysis](assets/transaction-analysis.png)

## 🛠️ Technologies Used

The project was developed using Excel/CSV as the source data, SQL for data manipulation and transformation, SQL Server and SQL Server Management Studio for database and Data Warehouse development, Data Modeling concepts for creating fact and dimension structures, and Power BI with DAX for business intelligence, KPI development, and visualization.

The major technologies and concepts used in this project include Excel, CSV, SQL, SQL Server, SSMS, Data Warehousing, Data Modeling, Fact Tables, Dimension Tables, Primary Keys, Foreign Keys, Date Dimensions, Power BI, DAX, KPI Development, Interactive Dashboards, and Business Intelligence.

## 📁 Project Structure

The recommended project structure is:

Banking-Data-Warehouse-PowerBI/

├── README.md

├── Data/

│   └── Banking_Master_Flat_File.csv

├── SQL/

│   ├── Database_Creation.sql

│   ├── Table_Creation.sql

│   ├── Data_Transformation.sql

│   ├── Fact_Tables.sql

│   ├── Dimension_Tables.sql

│   └── Relationships.sql

├── PowerBI/

│   └── ICICI_Bank_Analysis.pbix

├── assets/

│   ├── main-dashboard.png

│   ├── customer-analysis.png

│   ├── branch-analysis.png

│   └── transaction-analysis.png

└── Documentation/

    └── Data_Warehouse_Model.png

## 🚀 Project Outcome

The final outcome of this project is an end-to-end banking analytics solution that transforms a raw flat banking dataset into a structured SQL Server Data Warehouse and then uses that warehouse as the foundation for an interactive Power BI report. The project demonstrates practical experience in SQL, SQL Server, Data Warehousing, Data Modeling, Power BI, and DAX while showing how data can be transformed from its raw form into meaningful business insights.

The project follows the complete Business Intelligence workflow of Source Data → SQL Server → Data Warehouse → Data Model → DAX → Power BI → Business Analysis.

## 🔮 Future Enhancements

The project can be further enhanced by implementing advanced DAX calculations, year-over-year and month-over-month analysis, drill-through pages, tooltip pages, customer-level drill-down analysis, branch performance scorecards, Power BI Row-Level Security, incremental refresh, automated ETL processes, scheduled data refresh, and deployment to Power BI Service.

## 📌 Project Status

The source data analysis and SQL Server Data Warehouse development have been completed. The SQL Server database has been connected to Power BI, and the Power BI data model and visualization layer have been developed with multiple analytical pages. Further enhancements can be made to add more advanced business metrics, time-intelligence calculations, and additional interactive reporting features.

## 👨‍💻 Project Focus

This project was developed to gain practical hands-on experience in the complete data analytics and Business Intelligence lifecycle, starting from raw banking data and progressing through SQL Server Data Warehouse development, data modeling, DAX calculations, and Power BI visualization.

The overall project demonstrates the following workflow:

**Raw Banking Data → SQL Server → Data Warehouse → Fact & Dimension Model → Power BI → DAX → Interactive Financial Analytics**
