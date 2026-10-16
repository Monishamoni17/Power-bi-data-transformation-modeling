# 📊 Power BI – Data Transformation & Data Modeling

## 📝 Project Overview

This project focuses on transforming, cleaning, and modeling e-commerce sales data using **Microsoft Power BI and Power Query Editor**.

The project uses three related datasets to perform data preparation, column transformations, data quality checks, data aggregation, and relationship modeling. The objective is to create structured and consistent data that is ready for further analysis.

## 🎯 Project Objectives

- 📥 Import and transform multiple CSV datasets.
- 🧹 Identify and handle missing values and duplicate records.
- 🔠 Standardize text formats and correct data types.
- 🧮 Create custom and conditional columns.
- 🔗 Merge related datasets using common identifiers.
- 🔍 Sort and filter records based on business requirements.
- 📈 Group and aggregate data for meaningful summaries.
- 🧩 Establish relationships between tables in Power BI.

## 📂 Dataset Description

Three datasets were used in this project:

| Dataset | Key Attributes |
|---|---|
| 📦 **List of Orders** | Order ID, Order Date, Customer Name, City, State, Category, Amount, Profit |
| 🛍️ **Order Details** | Order ID, Category, Sub-Category, Quantity, Amount, Profit |
| 🎯 **Sales Target** | Category, Month of Order Date, Target |

## ⚙️ Data Transformation & Preparation

### 1. 📥 Data Import

- Imported `List of Orders.csv` into Power BI.
- Opened Power Query Editor using **Transform Data**.
- Imported `Order Details.csv` and `Sales Target.csv` into Power Query Editor.

### 2. 🔢 Row Limiting & Data Types

- Restricted the List of Orders table to the first 500 rows.
- Changed `Order Date` to the **Date** data type.
- Converted `Amount` and `Target` to **Fixed Decimal Number**.
- Applied appropriate data types to support consistent data processing.

### 3. 🔠 Text Formatting

- Applied **Proper Case** formatting to the `Customer Name` column.
- Standardized capitalization to improve text consistency.

### 4. 🧮 Custom Column Creation

**📍 Location**

- Merged `City` and `State` into a new column named `Location`.
- Used the required format: `City, State`.

**📈 Profit Margin**

- Created a custom column named `Profit Margin`.
- Applied the calculation:

  `Profit / Amount`

- Represented the result as a percentage where appropriate.
- Considered zero and null Amount values to avoid invalid calculations.

### 5. 🚦 Conditional Column – Profit Status

Created a conditional column named `Profit Status` using the following business rules:

| Condition | Profit Status |
|---|---|
| Profit < 0 | 🔴 Loss |
| Profit = 0 | 🟡 Break-Even |
| Profit > 0 | 🟢 Profit |

This classification distinguishes loss-making, break-even, and profitable records.

### 6. 🔗 Merging Data – Orders Data

- Merged the **List of Orders** and **Order Details** tables using `Order ID`.
- Named the merged output `Orders Data`.
- Used the common identifier to combine related order information.
- Selected the join type according to the required record-retention logic.

### 7. 🧹 Handling Missing Values & Duplicates

- Checked all three tables for missing values.
- Evaluated suitable strategies for replacing missing values.
- Retained null values when reliable replacement information was unavailable.
- Removed records only when justified by the data and business requirements.
- Identified duplicate rows and assessed whether they represented genuine duplication.

These steps help maintain data quality without introducing unsupported values or removing valid records.

### 8. 🔍 Sorting & Filtering

- Sorted `Orders Data` by `Order Date` in **descending order**.
- Applied a State filter to examine orders from **Tamil Nadu**.

These operations help organize records and focus on specific business requirements.

### 9. 📊 Grouping & Aggregation

Created a duplicate of the **Order Details** table and performed the following aggregations:

| Aggregation | Calculation |
|---|---|
| 🔢 Count of Order ID | Count Order ID |
| 📈 Average Profit | Average Profit by Category |
| 💰 Total Amount | Total Amount by Sub-Category |

**🎯 Sales Target Aggregation**

- Created a duplicate of the Sales Target table.
- Grouped the data by `Month of Order Date`.
- Calculated the **total Target for each month**.

These aggregations summarize detailed records into useful analytical metrics.

### 10. 🧩 Data Modeling & Relationships

Established the required relationships using Power BI's **Manage Relationships** feature.

| Tables | Relationship Key |
|---|---|
| List of Orders ↔ Order Details | `Order ID` |
| Order Details ↔ Sales Target | `Category` |

- Checked that the relationships were active and correctly configured.
- Validated relationship cardinality and filter direction against the actual data structure.

These relationships connect related datasets and support consistent analysis across tables.

## 🛠️ Tools & Techniques Used

- 🟡 **Microsoft Power BI Desktop**
- 🟢 **Power Query Editor**
- 📄 CSV Data Import
- 🧹 Data Cleaning & Quality Checks
- 🔠 Text Standardization
- 🧮 Custom & Conditional Columns
- 🔗 Merge Queries
- 🔍 Sorting & Filtering
- 📊 Grouping & Aggregation
- 🧩 Data Modeling & Relationship Management

## 💡 Key Learning Outcomes

Through this project, I developed practical experience in:

- Preparing raw datasets for analysis.
- Cleaning and standardizing data using Power Query.
- Creating calculated columns based on business rules.
- Combining datasets through merge operations.
- Identifying and handling missing and duplicate records.
- Summarizing data using grouping and aggregation.
- Establishing relationships between tables in Power BI.

**Key takeaway:** Reliable data analysis begins with clean, consistent, and well-structured data.

## 📁 Project Files

- `README.md` – Project documentation.
- `List of Orders.csv` – Order-level dataset.
- `Order Details.csv` – Order and product details dataset.
- `Sales Target.csv` – Sales target dataset.
- `Power BI Assignment 1.pbix` – Power BI project file, if included.
- `Power BI Assignment 1.pdf` – Assignment instructions, if included.

## 👩‍💻 About Me

**Monisha | Aspiring Data Analyst**

Currently developing practical skills in:

- Microsoft Excel
- SQL
- Power BI
- Python
- Data Analytics

This project is part of my ongoing journey to build practical data analysis skills and develop a professional portfolio through hands-on projects.

---

⭐ *Turning raw data into structured, analysis-ready information — one project at a time.*
