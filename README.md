# 🏦 Banking Data Analytics

End-to-end banking analytics project featuring AI-assisted data generation, SQL-based data cleaning, and interactive Power BI dashboards. Built to demonstrate real-world data engineering and business intelligence skills.

![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat&logo=microsoft-sql-server&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![AI Assisted](https://img.shields.io/badge/AI%20Assisted-Perplexity-00A4EF?style=flat)

## 🎯 Project Overview

A comprehensive banking analytics solution that simulates real-world data challenges and delivers actionable business insights through interactive visualizations. The project showcases end-to-end data pipeline development from synthetic data generation to executive-level dashboards.

## ✨ Key Features

- **Synthetic Data Generation**: Created 10,000+ realistic transaction records with intentional data quality issues
- **Advanced Data Cleaning**: Handled mixed date formats, case inconsistencies, NULL values, and referential integrity violations using T-SQL
- **ETL Pipeline**: Built complete Extract-Transform-Load workflow from normalized tables to analytics-ready dataset
- **Power BI Dashboards**: Designed interactive visualizations tracking customer demographics, transaction trends, and financial KPIs
- **AI-Powered KPIs**: Leveraged Perplexity AI for industry-standard banking metric recommendations

## 🛠️ Tech Stack

**Database**: MS SQL Server | **Query Language**: T-SQL | **Visualization**: Power BI Desktop | **AI**: Perplexity AI

## 📊 Database Schema

- **Customers**: Demographics, contact information, account relationships
- **Accounts**: Account types (Savings/Current), balances, opening dates
- **Transactions**: 10,000+ records with transaction types, amounts, currencies
- **Combined Dataset**: Integrated view using LEFT JOINs for comprehensive analysis

## 🔧 Data Quality Challenges Addressed

- Mixed date formats (YYYY-MM-DD, MM/DD/YYYY, DD-MM-YYYY, YYYY/MM/DD)
- Inconsistent text capitalization across categorical fields
- NULL values and empty strings handling
- Orphan records and broken foreign key relationships
- Financial outliers and negative balance scenarios
- Multi-currency transaction standardization

## 📈 Key Performance Indicators

- Total Account Balance & Transaction Volume
- Customer Acquisition Rate & Demographics Distribution
- Credit vs Debit Ratio Analysis
- Transaction Success Rate & Currency Distribution
- Account Type Performance (Savings vs Current)

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/Saksham-Pratap-Singh/Banking_DataAnalytics.git

# Execute SQL script in SQL Server Management Studio
# File: SQLQuerying-MS_SQLServer.sql

# Open Power BI report
# File: BankingAnalytics_Report.pbix
