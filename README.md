# Banking_DataAnalytics
```markdown
# 🏦 Banking Data Analytics

An end-to-end banking analytics project featuring AI-assisted data generation, SQL-based data cleaning, and interactive Power BI visualizations. This project demonstrates real-world data engineering and analytics workflows with intentionally introduced data quality issues and their resolution.

[![Repository](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/Saksham-Pratap-Singh/Banking_DataAnalytics)
[![Power BI](https://img.shields.io/badge/Power%20BI-Report-yellow?logo=powerbi)](https://github.com/Saksham-Pratap-Singh/Banking_DataAnalytics/blob/main/BankingAnalytics_Report.pbix)
[![SQL Server](https://img.shields.io/badge/SQL%20Server-Database-red?logo=microsoftsqlserver)](https://github.com/Saksham-Pratap-Singh/Banking_DataAnalytics/blob/main/SQLQuerying-MS_SQLServer.sql)

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Project Workflow](#-project-workflow)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Database Schema](#-database-schema)
- [Data Quality Issues Addressed](#-data-quality-issues-addressed)
- [Key Performance Indicators (KPIs)](#-key-performance-indicators-kpis)
- [Installation & Setup](#-installation--setup)
- [Project Structure](#-project-structure)
- [AI Assistance](#-ai-assistance)
- [Screenshots](#-screenshots)
- [Learning Outcomes](#-learning-outcomes)
- [Future Enhancements](#-future-enhancements)
- [Author](#-author)

---

## 🎯 Overview

This project simulates a comprehensive banking analytics pipeline, from synthetic data generation with intentional data quality issues to advanced business intelligence reporting. The project showcases:
- **Data Generation**: AI-assisted creation of realistic banking datasets with deliberate anomalies
- **Data Engineering**: SQL-based data cleaning, transformation, and standardization
- **Business Intelligence**: Interactive Power BI dashboards for actionable insights
- **KPI Strategy**: Perplexity AI-recommended banking performance metrics

---

## 🔄 Project Workflow

```
1. Data Generation (SQL Server)
   ↓
2. Intentional Data Quality Issues Introduction
   ↓
3. Data Cleaning & Transformation (SQL)
   ↓
4. Data Integration (Combined Dataset Creation)
   ↓
5. Power BI Visualization & KPI Development
   ↓
6. Business Insights & Recommendations
```

---

## ✨ Features

### Data Engineering
- **Synthetic Data Generation**: 10,000+ transaction records with realistic patterns
- **Dirty Data Simulation**: Intentional introduction of common data issues
- **Advanced SQL Cleaning**: Multi-format date standardization, case normalization, and outlier handling
- **Referential Integrity Testing**: Orphan records and foreign key violations
- **Data Integration**: Combined dataset from multiple normalized tables

### Analytics & Visualization
- **Interactive Dashboards**: Power BI reports with drill-through capabilities
- **KPI Monitoring**: Real-time performance tracking across multiple dimensions
- **Trend Analysis**: Time-series visualization of banking metrics
- **Customer Segmentation**: Demographic and behavioral analysis

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|-----------|
| **Database** | Microsoft SQL Server |
| **Query Language** | T-SQL |
| **BI Tool** | Power BI Desktop |
| **AI Assistant** | Perplexity AI |
| **Version Control** | Git & GitHub |
| **Documentation** | Markdown, PDF |

---

## 🗄️ Database Schema

### Tables

#### 1. **Customers**
| Column | Type | Description |
|--------|------|-------------|
| CustomerID | INT (PK) | Unique customer identifier |
| Name | NVARCHAR(100) | Customer full name |
| Gender | VARCHAR(10) | Gender (M/F/NULL) |
| DateOfBirth | VARCHAR(20) | Birth date (multiple formats) |
| Address | NVARCHAR(200) | Residential address |
| Email | NVARCHAR(100) | Contact email |
| Phone | VARCHAR(20) | Phone number |
| AccountID | INT | Linked account ID |

#### 2. **Accounts**
| Column | Type | Description |
|--------|------|-------------|
| AccountID | INT (PK) | Unique account identifier |
| CustomerID | INT | Foreign key to Customers |
| Type | NVARCHAR(20) | Account type (Savings/Current) |
| OpenDate | VARCHAR(20) | Account opening date |
| Balance | DECIMAL(18,2) | Current balance |

#### 3. **Transactions**
| Column | Type | Description |
|--------|------|-------------|
| TransactionID | INT | Transaction identifier |
| AccountID | INT | Related account |
| TransactionDate | VARCHAR(20) | Transaction date |
| Type | VARCHAR(20) | Credit/Debit |
| Amount | DECIMAL(18,2) | Transaction amount |
| Description | NVARCHAR(200) | Transaction description |
| Currency | VARCHAR(10) | Currency code |

---

## 🔧 Data Quality Issues Addressed

### Intentionally Introduced Issues
- **Date Format Inconsistencies**: Mixed formats (YYYY-MM-DD, MM/DD/YYYY, DD-MM-YYYY, YYYY/MM/DD)
- **Case Sensitivity**: Inconsistent capitalization in categorical fields
- **Missing Values**: NULL values in Email, Gender, Address, and Description fields
- **Referential Integrity**: Orphan records (AccountID 9999, CustomerID 99)
- **Outliers**: Extreme balance values (-157,874.40, 1,000,000.99)
- **Negative Amounts**: Invalid transaction amounts for testing
- **Currency Variations**: Mixed case currency codes (USD, usd, INR)
- **Empty Strings**: Blank values vs NULL distinction

### Cleaning Solutions Applied
```sql
-- Date standardization using TRY_CONVERT with multiple format codes (101, 23, 111, 105, 103)
-- Case normalization for Type fields
-- NULL handling strategies
-- Outlier identification and flagging
-- Combined dataset creation with LEFT JOINs to preserve orphan records
```

---

## 📊 Key Performance Indicators (KPIs)

Based on [AI-recommended banking metrics](https://github.com/Saksham-Pratap-Singh/Banking_DataAnalytics/blob/main/KPI%20Recommandations%20by%20Perplexity.pdf), the dashboard tracks:

### Financial Metrics
- **Total Balance**: Aggregate account balances
- **Average Transaction Value**: Mean transaction amount
- **Credit vs Debit Ratio**: Transaction type distribution
- **Revenue Trends**: Time-series financial performance

### Customer Metrics
- **Customer Acquisition Rate**: New account openings
- **Customer Demographics**: Age, gender distribution
- **Account Type Distribution**: Savings vs Current accounts
- **Active vs Inactive Accounts**: Engagement metrics

### Operational Metrics
- **Transaction Volume**: Daily/monthly transaction counts
- **Transaction Success Rate**: Valid vs invalid transactions
- **Currency Distribution**: Multi-currency analysis
- **Data Quality Score**: Percentage of clean records

---

## 🚀 Installation & Setup

### Prerequisites
- Microsoft SQL Server (2016 or later)
- SQL Server Management Studio (SSMS)
- Power BI Desktop (latest version)
- Git (for cloning repository)

### Steps

1. **Clone the Repository**
```bash
git clone https://github.com/Saksham-Pratap-Singh/Banking_DataAnalytics.git
cd Banking_DataAnalytics
```

2. **Database Setup**
```sql
-- Open SQL Server Management Studio
-- Execute the script in the following order:
-- File: SQLQuerying-MS_SQLServer.sql

-- This will:
-- 1. Create database 'Power_BI2'
-- 2. Create tables (Customers, Accounts, Transactions)
-- 3. Insert sample data with quality issues
-- 4. Generate 10,000 synthetic transactions
-- 5. Clean and standardize data
-- 6. Create combined dataset (CombinedBankingDataset)
```

3. **Power BI Report**
```
1. Open Power BI Desktop
2. Open file: BankingAnalytics_Report.pbix
3. Update data source connection to your SQL Server instance
4. Refresh data model
5. Explore interactive dashboards
```

4. **Review Documentation**
- **KPI Recommendations**: `KPI Recommandations by Perplexity.pdf`
- **Prompt Engineering**: `Prompt_Engineering.pdf`

---

## 📁 Project Structure

```
Banking_DataAnalytics/
│
├── BankingAnalytics_Report.pbix          # Power BI dashboard file
├── SQLQuerying-MS_SQLServer.sql          # Complete SQL script
├── KPI Recommandations by Perplexity.pdf # AI-generated KPI strategy
├── Prompt_Engineering.pdf                # Prompt documentation
└── README.md                             # Project documentation
```

---

## 🤖 AI Assistance

This project leverages **Perplexity AI** for:

### Data Generation
- Schema design recommendations
- Realistic data generation strategies
- SQL query optimization

### KPI Development
- Industry-standard banking metrics identification
- KPI calculation formulas
- Visualization best practices

### Prompt Engineering
- Documented prompt strategies for data generation
- Iterative refinement techniques
- Context-aware query formulation

**Documentation**: See `Prompt_Engineering.pdf` and `KPI Recommandations by Perplexity.pdf` for detailed AI interaction workflows.

---

## 📸 Screenshots

### Power BI Dashboard Preview
*(Open `BankingAnalytics_Report.pbix` to view interactive dashboards)*

**Key Visualizations**:
- Customer demographic distribution
- Transaction trend analysis
- Account balance overview
- KPI scorecards
- Currency-wise transaction breakdown

---

## 💡 Learning Outcomes

This project demonstrates proficiency in:

### Technical Skills
- ✅ T-SQL advanced querying (CTEs, window functions, dynamic data generation)
- ✅ Data quality assessment and remediation
- ✅ ETL pipeline development
- ✅ Power BI data modeling and DAX
- ✅ Database schema design and normalization

### Analytical Skills
- ✅ Business requirements translation to KPIs
- ✅ Data storytelling through visualizations
- ✅ Anomaly detection and outlier analysis
- ✅ Trend identification and forecasting preparation

### AI & Automation
- ✅ Prompt engineering for data generation
- ✅ AI-assisted KPI recommendation systems
- ✅ Leveraging LLMs for technical problem-solving

---

## 🔮 Future Enhancements

### Planned Features
- [ ] **Python Integration**: Pandas-based data validation scripts
- [ ] **Automated Data Pipeline**: Scheduled data refresh with Azure Data Factory
- [ ] **Machine Learning**: Customer churn prediction model
- [ ] **Real-time Dashboard**: Power BI streaming datasets
- [ ] **Advanced Analytics**: Cohort analysis, RFM segmentation
- [ ] **API Integration**: RESTful API for data access
- [ ] **Docker Deployment**: Containerized SQL Server environment

### Potential Expansions
- Multi-branch banking analysis
- Loan portfolio management module
- Fraud detection system
- Customer lifetime value prediction

---

## 👨‍💻 Author

**Saksham Pratap Singh**

- **GitHub**: [@Saksham-Pratap-Singh](https://github.com/Saksham-Pratap-Singh)
- **Location**: Agra, Uttar Pradesh, India
- **Email**: sakshamraghav14@gmail.com
- **Bio**: Final Year ECE Student | Data Science & ML Enthusiast | Power BI | SQL | Python

### Connect With Me
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github)](https://github.com/Saksham-Pratap-Singh)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://linkedin.com/in/your-profile)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- **Perplexity AI** for KPI recommendations and prompt engineering guidance
- **Microsoft** for SQL Server and Power BI tools
- **GitHub Community** for open-source learning resources

---

## ⭐ Show Your Support

If you found this project helpful, please consider:
- Starring the repository ⭐
- Forking for your own learning
- Sharing with fellow data enthusiasts
- Providing feedback through issues

---

**Last Updated**: January 2026
```

***

This README follows industry best practices with:
- Clear structure with table of contents
- Comprehensive technical documentation
- Visual badges and formatting
- Detailed installation instructions
- Future roadmap transparency
- Professional presentation suitable for portfolio showcase

You can copy this directly into your README.md file! Let me know if you'd like any modifications.
