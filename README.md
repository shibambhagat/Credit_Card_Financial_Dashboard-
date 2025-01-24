# Credit Card Financial Dashboard

## Project Objective
The objective of this project is to **develop a comprehensive credit card weekly dashboard** that provides real-time insights into key performance metrics and trends. This dashboard enables stakeholders to effectively monitor and analyze credit card operations, facilitating data-driven decisions to improve business outcomes.

---

## Project Insights

### Week-on-Week Analysis
- **Revenue increased by 28.8%** week-over-week.
- **Total Transaction Amount and Count** have both increased.
- **Customer Count** has increased.

### Year-to-Date Overview
- **Overall Revenue**: $57M
- **Total Interest Earned**: $8M
- **Total Transaction Amount**: $46M
- **Revenue Contribution by Gender**:
  - **Male customers** contributed **$31M**.
  - **Female customers** contributed **$26M**.
- **Card Category Contribution**:
  - **Blue & Silver** credit cards contribute **93%** of overall transactions.
- **Geographic Contribution**:
  - **Texas (TX)**, **New York (NY)**, and **California (CA)** contribute **68%** of total transactions.
- **Activation Rate**: **57.5%** of customers have activated their cards.
- **Delinquent Rate**: The overall delinquent rate is **6.06%**.

---

## Features

### Customer Dashboard
- Total Revenue, Interest, and Income overview.
- Revenue trends over time (weekly breakdown).
- Revenue segmented by demographic factors:
  - Age groups (20-30, 30-40, etc.).
  - Marital status (Married, Single, Unknown).
  - Education level (Graduate, Post-Graduate, etc.).
  - Job types (Businessman, Govt., Self-employed, etc.).
  - Dependents (0 to 4).
- Top 5 states contributing to revenue.

### Transaction Dashboard
- Transaction volume and revenue by quarter (Q1 to Q4).
- Revenue by card categories (Silver, Blue, Gold, Platinum).
- Expenditure type analysis (e.g., bills, groceries, entertainment).
- Transaction methods (Swipe, Online, Chip).
- Revenue by education level and customer job type.

---

## SQL Database for Credit Card and Customer Data

This repository contains SQL scripts to create a database for storing and analyzing credit card and customer transaction data. The scripts include creating the necessary tables, importing data from CSV files, and resolving common import issues.

### Project Structure
- `ccdb.sql`: SQL script for creating and importing data into the `cc_detail` and `cust_detail` tables.
- `credit_card.csv`: Sample CSV file for credit card transaction data.
- `customer.csv`: Sample CSV file for customer information data.
- `cc_add.csv`: Additional data for the `cc_detail` table (e.g., Week-53 data).
- `cust_add.csv`: Additional data for the `cust_detail` table.

### Setup Instructions

Follow these steps to set up the database and import data:

#### 1. Create the Database
First, create a new database where all the data will be stored:

```sql
CREATE DATABASE ccdb;
```

#### 2. Create the Tables
Run the SQL script to create two primary tables: `cc_detail` for credit card transactions and `cust_detail` for customer details.

```sql
-- Creating cc_detail table
CREATE TABLE cc_detail (
    Client_Num INT,
    Card_Category VARCHAR(20),
    Annual_Fees INT,
    Activation_30_Days INT,
    Customer_Acq_Cost INT,
    Week_Start_Date DATE,
    Week_Num VARCHAR(20),
    Qtr VARCHAR(10),
    current_year INT,
    Credit_Limit DECIMAL(10,2),
    Total_Revolving_Bal INT,
    Total_Trans_Amt INT,
    Total_Trans_Ct INT,
    Avg_Utilization_Ratio DECIMAL(10,3),
    Use_Chip VARCHAR(10),
    Exp_Type VARCHAR(50),
    Interest_Earned DECIMAL(10,3),
    Delinquent_Acc VARCHAR(5)
);

-- Creating cust_detail table
CREATE TABLE cust_detail (
    Client_Num INT,
    Customer_Age INT,
    Gender VARCHAR(5),
    Dependent_Count INT,
    Education_Level VARCHAR(50),
    Marital_Status VARCHAR(20),
    State_cd VARCHAR(50),
    Zipcode VARCHAR(20),
    Car_Owner VARCHAR(5),
    House_Owner VARCHAR(5),
    Personal_Loan VARCHAR(5),
    Contact VARCHAR(50),
    Customer_Job VARCHAR(50),
    Income INT,
    Cust_Satisfaction_Score INT
);
```

#### 3. Import Data
Once the tables are created, use the `COPY` command to import data from CSV files into the corresponding tables.

```sql
-- Import credit card data into cc_detail
COPY cc_detail
FROM 'D:\credit_card.csv' 
DELIMITER ',' 
CSV HEADER;

-- Import customer data into cust_detail
COPY cust_detail
FROM 'D:\customer.csv' 
DELIMITER ',' 
CSV HEADER;
```

---

## Access the Dashboards
- **Customer Dashboard**: [View Live Dashboard](https://app.powerbi.com/view?r=eyJrIjoiYTBhNzY0MWUtZDAwNS00MzMyLTk3MWYtNDc2MWRmY2Y1ZTBlIiwidCI6IjJmMTMyMWI5LTVkYWEtNDM4NC04NjBlLTMzODQwYTc0OWVmYiJ9)

---

## Technologies Used
- **Power BI**: Used for creating interactive visualizations.
- **SQL**: Used for writing queries, creating tables, and importing data.
- **Data Sources**: CSV files for importing data.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
- Data sources and inspiration (replace with any relevant credits or acknowledgments).
- Tools and technologies used: Power BI, Excel, SQL.

---


