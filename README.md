# Credit-Card-Financial-Dashboard-

Overview
## This project analyzes credit card customer data using Power BI, DAX, and SQL. It categorizes customers based on age and income, tracks revenue trends, and provides insights into customer spending behaviors.

# 1. SQL Database and Queries
Database Creation
A database named ccdb was created to store customer and transaction details."


# CREATE DATABASE ccdb;
Tables Created
1. cc_detail (Credit Card Transactions)
This table stores details about customer transactions, including credit limits, spending, and transaction history.

# CREATE TABLE cc_detail(
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
# 2. cust_detail (Customer Information)
This table contains customer demographics, such as age, income, and job type.

# CREATE TABLE cust_detail (
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
# Data Import
The data is loaded from CSV files into the database using the COPY command:


# COPY cc_detail
FROM 'C:\Users\priti\Downloads\credit_card.csv'
DELIMITER ','
CSV HEADER;

# COPY cust_detail
FROM 'C:\Users\priti\Downloads\customer.csv'
DELIMITER ','
CSV HEADER;
Updating Data with Additional Records

#COPY cc_detail
FROM 'C:\Users\priti\Downloads\cc_add.csv'
DELIMITER ','
CSV HEADER;

#COPY cust_detail
FROM 'C:\Users\priti\Downloads\cust_add.csv'
DELIMITER ','
CSV HEADER;


# 2. DAX Measures Used
Customer Segmentation
AgeGroup: Categorizes customers into age brackets (20-30, 30-40, etc.).
IncomeGroup: Groups customers based on income levels (LOW, MID, HIGH).
Revenue Analysis
Week_num2: Extracts the week number from transaction dates.
Current_week_Revenue: Calculates total revenue for the latest week.
Previous_week_Revenue: Computes revenue for the previous week.
WoW_Revenue: Determines the week-over-week revenue change percentage.

# 3. Analysis & Insights
📊 Revenue Breakdown
Total Revenue: $56.5M
Total Income: $587.6M
Total Interest Earned: $8M

📌 Revenue by Age Group
Age Group	Revenue Contribution
20-30	$4M
30-40	$11M
40-50	$9M
50-60	$6M
60+	$14M

📌 Revenue by Job Type
Job Type	Revenue Contribution
Blue-collar	$7M
Businessman	$17.6M
Govt	$8.3M
Retirees	$4.6M
Self-employed	$8.5M

📌 Revenue by Income Group
High Income: $23M
Mid Income: $10M
Low Income: $8M

🔍 Key Takeaways
✅ Age 30-40 and 50-60 contribute the highest revenue.
✅ Businessmen and self-employed customers generate the most revenue.
✅ High-income customers are responsible for 40% of total revenue.
✅ Revenue fluctuates significantly by week, with Q4 showing the highest earnings.
✅ Transactions using chips contribute more revenue than swipes and online payments.

# 4. Project Outcomes
1️⃣ Customer Segmentation
📌 Successfully categorized customers into age groups and income levels.
📌 Identified high-revenue segments for targeted marketing campaigns.

2️⃣ Revenue Trends
📌 Weekly revenue trends help predict sales fluctuations.
📌 Q4 shows the highest revenue spikes (holiday season spending).
📌 Low-revenue weeks indicate potential areas for improvement in business strategy.

3️⃣ Spending & Utilization
📌 Higher credit utilization ratios correlate with increased revenue.
📌 Customers with higher transaction counts contribute more revenue.

4️⃣ Business Impact
📌 The findings help identify profitable customer segments for better engagement.
📌 The insights enable banks to improve credit offerings and marketing strategies.
📌 Risk assessment is improved by tracking delinquent accounts and high-risk customers.

# 5. Power BI Visualizations 📊
Revenue by Customer Job
📌 Businessmen and self-employed customers generate the most revenue.

Revenue by Age Group
📌 Customers aged 30-40 and 50-60 generate the most revenue.

Revenue by Income Group
📌 High-income customers drive the majority of revenue.

# 6. How to Use
Database Setup: Execute the SQL scripts to create tables and import data.
Data Analysis: Use Power BI to connect to the database and perform insights analysis with DAX.
Visualization: Build reports on revenue trends, customer segmentation, and performance metrics.

# 7. Dependencies
Power BI
SQL
DAX
