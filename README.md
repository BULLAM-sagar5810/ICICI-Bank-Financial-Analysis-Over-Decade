# 🏦 Banking Data Warehouse & Power BI Analytics

## 📌 Project Overview

This project is an end-to-end **Banking Data Warehouse and Business Intelligence solution** developed using **Excel/CSV, SQL Server, SQL, Data Warehousing concepts, Data Modeling, Power BI, and DAX**.

The project starts with a flat banking dataset containing **40,000 customer records and 28 attributes** covering customers, accounts, branches, loans, and transaction-related information.

Instead of directly connecting the flat file to Power BI, the source data was first processed and structured using **SQL Server** to build a business-oriented Data Warehouse.

The completed warehouse is then connected to **Power BI** for data modeling, KPI development, interactive reporting, and visualization.

---

## 🎯 Project Objective

The primary objective of this project is to transform raw banking data into a structured analytical solution that can help analyze:

* Customer behavior
* Account information
* Branch performance
* Banking transactions
* Deposits and withdrawals
* Money transfers
* Failed transactions
* Loan portfolios
* Customer segments
* Time-based banking activity

---

# 🔄 End-to-End Architecture

```text
                  SOURCE DATA
                      │
                      ▼
             Excel / CSV Flat File
                      │
                      ▼
          Data Understanding & Cleaning
                      │
                      ▼
                  SQL Server
                      │
                      ▼
             Database & Tables
                      │
                      ▼
          Data Warehouse Development
                      │
          ┌───────────┴───────────┐
          ▼                       ▼
     Dimension Tables          Fact Tables
          │                       │
          └───────────┬───────────┘
                      ▼
                Data Model
                      │
                      ▼
                  Power BI
                      │
                      ▼
             DAX Measures & KPIs
                      │
                      ▼
          Interactive Dashboards
```

---

# 📂 Source Dataset

The project uses a banking master flat file containing:

* **40,000 records**
* **28 attributes**

The source data includes multiple business domains in a single flat structure.

### Customer Attributes

* Customer_ID
* Customer_Name
* Gender
* Age
* City
* State
* Occupation
* Customer_Segment

### Account Attributes

* Account_ID
* Account_Count
* Account_Type
* Account_Opening_Date
* Current_Balance

### Branch Attributes

* Branch_ID
* Branch_Name

### Loan Attributes

* Loan_ID
* Loan_Type
* Loan_Amount
* Interest_Rate
* Loan_Status

### Transaction Attributes

* Transaction_Count
* Total_Deposit
* Total_Withdrawal
* Total_Transfer
* Failed_Transaction_Count
* Last_Transaction_Date
* Preferred_Channel
* Avg_Transaction_Amount

---

# 🗄️ Data Warehouse

The original flat file contains multiple business entities in one structure.

To make the data more suitable for analytics, the data was organized into separate business-oriented tables using SQL Server.

## Main Tables

### Dimension / Master Tables

* `Customers`
* `Accounts`
* `Branches`
* `Loans`
* `Dim_Date`

### Fact Tables

* `Fact_Bank_Transaction`
* `Fact_Bank_Loan`

### Source / Supporting Table

* `Transection`

The warehouse model is designed to separate descriptive business information from measurable business events.

---

# ⭐ Data Warehouse Model

Conceptually, the model follows a fact-and-dimension approach:

```text
                       Dim_Date
                          │
                          │
Customers ─────── Fact_Bank_Transaction ─────── Accounts
      │                    │
      │                    │
      │                 Branches
      │
      │
Fact_Bank_Loan ───────── Loans
```

The model supports analysis across customers, accounts, branches, transactions, loans, and dates.

---

# 🧱 Fact Tables

## Fact_Bank_Transaction

The transaction fact table is designed to support banking transaction analysis.

Important measures include:

* Total Deposit
* Total Withdrawal
* Total Transfer
* Transaction Count
* Failed Transaction Count
* Average Transaction Amount

### Business Questions

* What is the total deposit amount?
* What is the total withdrawal amount?
* Which branches generate higher transaction activity?
* How many transactions are being processed?
* How many transactions fail?
* How does transaction activity change over time?

---

## Fact_Bank_Loan

The loan fact table supports analysis of the banking loan portfolio.

Important metrics include:

* Loan Amount
* Loan Count
* Interest Rate
* Loan Status

### Business Questions

* What is the total loan amount?
* How many loans are active?
* Which loan types have higher volumes?
* How is the loan portfolio distributed across branches?
* How does loan activity vary across customer segments?

---

# 📅 Date Dimension

A dedicated `Dim_Date` table is used for time-based analysis.

It supports:

* Year analysis
* Month analysis
* Date filtering
* Trend analysis
* Period-based reporting

This allows Power BI visuals to perform time-based analysis more effectively.

---

# 📊 Power BI Dashboard

After completing the SQL Server Data Warehouse layer, the warehouse was connected to Power BI.

The Power BI report contains multiple analytical pages.

## 1. Main Page

Provides an executive-level overview of banking activity.

Potential KPIs include:

* Total Customers
* Total Accounts
* Total Deposits
* Total Withdrawals
* Total Transfers
* Total Transactions
* Total Loan Amount
* Active Loans
* Failed Transactions

---

## 2. Customer Analysis

Focuses on customer demographics and customer behavior.

Analysis includes:

* Customer distribution
* State-wise customers
* City-wise customers
* Occupation analysis
* Customer segments
* Age distribution
* Account type analysis

---

## 3. Branch Analysis

Focuses on branch-level performance.

Analysis includes:

* Customers by branch
* Transactions by branch
* Deposits by branch
* Withdrawals by branch
* Transfers by branch
* Loan activity by branch

---

## 4. Transaction Analysis

Focuses on banking transaction activity.

Key metrics include:

* Total Transactions
* Total Deposits
* Total Withdrawals
* Total Transfers
* Failed Transactions
* Average Transaction Amount

---

## 5. Loan Analysis

Focuses on the bank's loan portfolio.

Analysis includes:

* Total Loan Amount
* Loan Count
* Loan Type
* Loan Status
* Interest Rate
* Branch-wise loan analysis
* Customer segment analysis

---

## 6. Money Flow in Bank

This page focuses on the movement of money through the banking system.

The analysis includes:

```text
Deposits
   │
   ├── Withdrawals
   │
   └── Transfers
```

A calculated net money-flow metric can be used to compare deposits and withdrawals.

---

# 📐 Example DAX Measures

### Total Deposits

```DAX
Total Deposits =
SUM(Fact_Bank_Transaction[Total_Deposit])
```

### Total Withdrawals

```DAX
Total Withdrawals =
SUM(Fact_Bank_Transaction[Total_Withdrawal])
```

### Total Transfers

```DAX
Total Transfers =
SUM(Fact_Bank_Transaction[Total_Transfer])
```

### Total Transactions

```DAX
Total Transactions =
SUM(Fact_Bank_Transaction[Transaction_Count])
```

### Failed Transactions

```DAX
Failed Transactions =
SUM(Fact_Bank_Transaction[Failed_Transaction_Count])
```

### Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(Fact_Bank_Transaction[Customer_ID])
```

### Net Money Flow

```DAX
Net Money Flow =
[Total Deposits] - [Total Withdrawals]
```

---

# 🛠️ Technologies Used

| Technology    | Purpose                              |
| ------------- | ------------------------------------ |
| Excel / CSV   | Source data                          |
| SQL           | Data manipulation and transformation |
| SQL Server    | Database & Data Warehouse            |
| SSMS          | SQL development                      |
| Data Modeling | Fact and dimension design            |
| Power BI      | Visualization & reporting            |
| DAX           | KPI and analytical calculations      |

---

# 🔑 Key Concepts Demonstrated

This project demonstrates practical understanding of:

* SQL
* SQL Server
* Data Warehousing
* Fact Tables
* Dimension Tables
* Star Schema concepts
* Primary Keys
* Foreign Keys
* Data Transformation
* Data Modeling
* Date Dimensions
* DAX
* KPI Development
* Power BI
* Interactive Dashboard Design
* Business Intelligence

---

# 📈 Project Outcome

The project converts a raw banking flat file into a structured analytical solution.

```text
Raw Banking Data
       ↓
SQL Server
       ↓
Structured Data Warehouse
       ↓
Fact + Dimension Model
       ↓
Power BI Data Model
       ↓
DAX KPIs
       ↓
Interactive Banking Analytics
```

The solution provides a foundation for analyzing customers, accounts, branches, transactions, loans, and money flow through a centralized BI environment.

---

# 🚀 Future Enhancements

The project can be extended with:

* Row-Level Security
* Incremental Refresh
* Advanced DAX calculations
* Year-over-Year analysis
* Month-over-Month analysis
* Drill-through pages
* Tooltip pages
* Customer-level drill-down
* Branch performance scorecards
* Advanced time intelligence
* Power BI Service deployment
* Scheduled data refresh
* SQL Server ETL automation

---

# 👨‍💻 Project Focus

This project was developed to gain practical experience in the complete BI workflow:

**Source Data → SQL Server → Data Warehouse → Data Model → DAX → Power BI → Business Insights**

---

## 📌 Project Status

**Data Warehouse:** Completed
**SQL Server Modeling:** Completed
**Power BI Connection:** Completed
**Dashboard Visualization:** In Progress
