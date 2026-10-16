# 📊 Power BI – Data Transformation & Data Modeling

A Power BI project focused on cleaning, transforming, merging, and modeling e-commerce datasets to create consistent, analysis-ready data.

## 📑 Table of Contents

- [🎯 Project Overview](#-project-overview)
- [🗃️ Data Sources & Architecture](#️-data-sources--architecture)
- [⚙️ Data Transformation (ETL)](#️-data-transformation-etl)
- [🧠 Data Model & DAX](#-data-model--dax)
- [🖥️ Dashboard Features](#️-dashboard-features)
- [💡 Key Insights](#-key-insights)
- [🚀 How To Use](#-how-to-use)

---

## 🎯 Project Overview

- **Business Problem:** Raw e-commerce datasets may contain inconsistent text formats, missing values, duplicate records, and data that requires transformation before analysis.
- **Objective:** Clean, transform, combine, and organize order and sales target data using Power BI and Power Query Editor.
- **Target Audience:** Data analysts, business analysts, and learners developing data preparation and data modeling skills.

### 🎯 Project Objectives

- Import and transform multiple CSV datasets.
- Identify and handle missing values and duplicate records.
- Standardize text formats and correct data types.
- Create custom and conditional columns.
- Merge related datasets using common identifiers.
- Sort and filter records based on business requirements.
- Group and aggregate data for meaningful summaries.
- Establish relationships between tables in Power BI.

## 🗃️ Data Sources & Architecture

### 📂 Source Datasets

This project uses three CSV datasets:

| Dataset | Key Attributes |
|---|---|
| 📦 **List of Orders** | Order ID, Order Date, Customer Name, City, State, Category, Amount, Profit |
| 🛍️ **Order Details** | Order ID, Category, Sub-Category, Quantity, Amount, Profit |
| 🎯 **Sales Target** | Category, Month of Order Date, Target |

- **Source System:** Local CSV files
- **Data Volume:** The List of Orders dataset was restricted to the first 500 rows as required by the assignment.
- **Storage Mode:** Import mode using Power BI Desktop.
- **Data Preparation Tool:** Power Query Editor.

## ⚙️ Data Transformation (ETL)

### 1. 📥 Data Import & Data Types

- Imported all three CSV datasets into Power BI.
- Opened Power Query Editor to perform data transformations.
- Restricted List of Orders to the first 500 rows.
- Changed Order Date to the Date data type.
- Converted Amount and Target to Fixed Decimal Number.
- Applied appropriate data types for consistent processing.

### 2. 🔠 Text Standardization

- Applied Proper Case formatting to Customer Name.
- Standardized text capitalization to improve consistency.

### 3. 🧮 Custom Columns

**📍 Location**

- Merged City and State into a new column named `Location`.
- Used the required format: `City, State`.

**📈 Profit Margin**

- Created a custom column named `Profit Margin`.
- Applied the calculation: `Profit / Amount`.
- Formatted the result as a percentage where appropriate.
- Considered zero and null Amount values to avoid invalid calculations.

### 4. 🚦 Conditional Column – Profit Status

Created a conditional column named `Profit Status` using these business rules:

| Condition | Profit Status |
|---|---|
| Profit < 0 | 🔴 Loss |
| Profit = 0 | 🟡 Break-Even |
| Profit > 0 | 🟢 Profit |

This classification distinguishes loss-making, break-even, and profitable records.

### 5. 🔗 Merge Queries – Orders Data

- Merged List of Orders and Order Details using `Order ID`.
- Named the merged output `Orders Data`.
- Used the common identifier to combine related order information.
- Selected the join type according to the required record-retention logic.

### 6. 🧹 Data Quality Checks

- Checked all three datasets for missing values.
- Evaluated appropriate strategies for handling missing data.
- Retained null values when reliable replacement information was unavailable.
- Removed records only when justified by the data and business requirements.
- Identified duplicate rows and assessed whether they represented genuine duplication.

### 7. 🔍 Sorting & Filtering

- Sorted Orders Data by Order Date in descending order.
- Filtered the State column to examine orders from Tamil Nadu.

### 8. 📊 Grouping & Aggregation

**Order Details Aggregation**

Created a duplicate of the Order Details table and performed the following aggregations:

| Aggregation | Calculation |
|---|---|
| 🔢 Count of Order ID | Count Order ID |
| 📈 Average Profit | Average Profit by Category |
| 💰 Total Amount | Total Amount by Sub-Category |

**Sales Target Aggregation**

- Created a duplicate of the Sales Target table.
- Grouped the data by Month of Order Date.
- Calculated the total Target for each month.

### 9. 🧩 Data Modeling & Relationships

Established and checked relationships using Power BI's Manage Relationships feature.

| Related Tables | Relationship Key |
|---|---|
| List of Orders ↔ Order Details | Order ID |
| Order Details ↔ Sales Target | Category |

- Checked that relationships were active and correctly configured.
- Validated relationship cardinality and filter direction against the data structure.

### 🛠️ Tools & Techniques Used

- 🟡 Microsoft Power BI Desktop
- 🟢 Power Query Editor
- 📄 CSV Data Import
- 🧹 Data Cleaning & Quality Checks
- 🔠 Text Standardization
- 🧮 Custom & Conditional Columns
- 🔗 Merge Queries
- 🔍 Sorting & Filtering
- 📊 Grouping & Aggregation
- 🧩 Data Modeling & Relationship Management

## 🧠 Data Model & DAX

- **Modeling Approach:** Relationship-based data modeling using the provided order, order detail, and sales target datasets.
- **Primary Tables:** List of Orders, Order Details, and Sales Target.
- **Relationship Keys:** Order ID and Category.
- **Calculated Columns:** Location, Profit Margin, and Profit Status.
- **DAX Measures:** No specific DAX measures are documented in this project; the main calculations and aggregations were performed in Power Query Editor.

The model connects related datasets and provides a structured foundation for further analysis.

## 🖥️ Dashboard Features

This assignment primarily focuses on data transformation and modeling rather than dashboard design.

Key project features include:

- 📥 Importing and preparing multiple datasets.
- 🧹 Cleaning and standardizing data.
- 🧮 Creating custom and conditional columns.
- 🔗 Merging related tables.
- 📊 Grouping and aggregating data.
- 🧩 Establishing and validating table relationships.

**Design Theme:** Focused on clear data preparation, consistent data types, and structured data modeling.

## 💡 Key Insights

### 📌 Key Learning Outcomes

- **Data Quality:** Identifying missing values and duplicates helps improve data reliability.
- **Data Consistency:** Standardizing text and data types supports accurate processing.
- **Data Transformation:** Custom columns and conditional logic help classify and prepare records for analysis.
- **Data Integration:** Merging tables using common identifiers combines related information.
- **Data Aggregation:** Grouping data produces useful summaries by category, sub-category, and month.
- **Data Modeling:** Properly configured relationships connect datasets for further analysis.

**Recommendation:** Validate data quality, calculation logic, and relationships before using transformed datasets for business reporting and decision-making.

**Key Takeaway:** Reliable data analysis begins with clean, consistent, and well-structured data.

## 🚀 How To Use

1. **Prerequisites:** Install Microsoft Power BI Desktop.
2. **Clone the Repository:** Download or clone this repository to your local system.
3. **Access Project Files:** Open the assignment PDF and available source CSV files.
4. **Import Data:** Load the CSV datasets into Power BI Desktop.
5. **Transform Data:** Open Power Query Editor and follow the documented transformation steps.
6. **Configure Relationships:** Use Manage Relationships to establish and validate the required table relationships.
7. **Save Your Work:** Save the completed Power BI project as a `.pbix` file.
8. **Refresh Data:** If the CSV files are moved, update their source paths through **Data source settings** before refreshing.

## 📁 Project Files

- `README.md` – Project documentation.
- `Power BI Assignment-Data Transformation & Data Modeling.pdf` – Assignment document.
- Source CSV datasets – List of Orders, Order Details, and Sales Target, where included.
- Power BI `.pbix` file – Completed project file, if included.

## 👩‍💻 About Me

**Monisha | Aspiring Data Analyst**

Currently developing practical skills in:

- Microsoft Excel
- SQL
- Power BI
- Python
- Data Analytics

This project is part of my ongoing learning journey to strengthen data analysis skills through practical assignments and build a professional portfolio.

⭐ *Turning raw data into structured, analysis-ready information — one project at a time.*
