# 🛒 Walmart Sales Analysis (SQL)

> End-to-end SQL analytics project analyzing sales trends, branch performance, and customer purchasing patterns across 1,000 Walmart transactions.

---

## 📋 Project Overview

This project analyzes transactional sales data from **3 Walmart branches** located in **Mandalay**, **Yangon**, and **Naypyitaw** to uncover top-performing product categories, evaluate sales performance trends, and analyze customer purchasing behaviors.

The analysis is built entirely in **MySQL**, demonstrating data cleaning, feature engineering, complex aggregations, and business logic execution.

| Attribute | Details |
|---|---|
| **Dataset Source** | [Kaggle — Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting) |
| **Dataset Size** | 1,000 records × 17 features |
| **Database Engine** | MySQL 8.0+ |
| **Tools Used** | MySQL Workbench / CLI |

---

## 🔑 Key Insights & Business Findings

### 📈 Revenue & Product Insights
- **Top Product Line:** *Fashion Accessories* and *Food & Beverages* generated the highest total volume and revenue across branches.
- **Top Revenue Month:** **January** recorded peak revenue and highest Cost of Goods Sold (COGS).
- **Branch Performance:** The branch in **Naypyitaw** achieved the highest overall sales volume and gross margin.

### ⏰ Sales Trend & Operational Timing
- **Peak Sales Window:** The majority of transactions occur during **Evening hours (16:00 - 20:00)** across all three branches.
- **Busiest Days:** **Saturdays** and **Tuesdays** record the highest customer traffic and overall sales volume.

### 👤 Customer Segment & Tax Analysis
- **Customer Breakdown:** **Member customers** generate significantly higher revenue than normal guest shoppers.
- **Payment Preferences:** **E-wallet** is the most preferred payment method, followed by Cash and Credit Cards.
- **Tax / VAT Contributions:** *Food & Beverages* product line yields the highest Value Added Tax (VAT) contribution.

---

## 🛠️ SQL Technical Stack & Concepts

| Category | Technical Concepts | Applied Usage in Project |
|---|---|---|
| **DDL (Data Definition)** | `CREATE DATABASE`, `CREATE TABLE`, `PRIMARY KEY`, `NOT NULL` | Database schema initialization with strict data type definition and integrity constraints |
| **DML (Data Manipulation)** | `ALTER TABLE`, `ADD COLUMN`, `UPDATE ... SET` | Schema expansion and writing engineered feature columns back to table records |
| **Feature Engineering** | `CASE WHEN ... THEN ... ELSE ... END` | Binning transaction timestamps into `time_of_day` (*Morning*, *Afternoon*, *Evening*) and classifying sales metrics |
| **Temporal Functions** | `DAYNAME()`, `MONTHNAME()`, `EXTRACT()` | Extracting day of week and calendar month names for seasonal and weekly trend analysis |
| **Aggregations & Analytics** | `GROUP BY`, `SUM()`, `AVG()`, `COUNT()`, `ORDER BY` | Revenue categorization, branch benchmarking, average rating calculations, and top-N ranking |
| **Data Filtering** | `SELECT DISTINCT`, `WHERE`, `HAVING` | Distinct category extraction, branch-level filtering, and post-aggregation threshold filtering |

---

## 🗂️ Database Schema & Data Features

The project operates on the `sales` relational table comprising 17 attributes:

| Column | Type | Description |
|---|---|---|
| `invoice_id` | VARCHAR(30) | Unique invoice identifier (**Primary Key**) |
| `branch` | VARCHAR(5) | Branch identifier (A, B, C) |
| `city` | VARCHAR(30) | City location (Mandalay, Yangon, Naypyitaw) |
| `customer_type` | VARCHAR(30) | Customer tier (*Member* or *Normal*) |
| `gender` | VARCHAR(10) | Customer gender |
| `product_line` | VARCHAR(100) | Product line category |
| `unit_price` | DECIMAL(10,2) | Price per unit (USD) |
| `quantity` | INT | Number of units purchased |
| `VAT` | FLOAT(6,4) | Tax amount (5% Value Added Tax) |
| `total` | DECIMAL(12,4) | Total invoice amount including tax |
| `date` | DATETIME | Transaction date |
| `time` | TIME | Transaction timestamp |
| `payment` | VARCHAR(15) | Payment method (*E-wallet*, *Cash*, *Credit Card*) |
| `cogs` | DECIMAL(10,2) | Cost of Goods Sold |
| `gross_margin_pct` | FLOAT(11,9) | Gross margin percentage |
| `gross_income` | DECIMAL(12,4) | Gross profit generated |
| `rating` | FLOAT(2,1) | Customer satisfaction score (1–10) |

---

## 📁 Repository Structure



---

## 🚀 How to Setup & Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/ABHI-2802/Walmart_sales.git
   ```

2. **Set up MySQL Database**
   Open MySQL Workbench / CLI and run `Queries.sql` to:
   - Create the `WalmartSalesData` database
   - Execute table creation DDL
   - Perform feature engineering (`time_of_day`, `day_name`, `month_name`)

3. **Execute Analytical Queries**
   Run the EDA section of `Queries.sql` to generate product, sales, and customer analytics reports.

---

## 📄 License

This project is open-source under the MIT License for educational and portfolio purposes.

*Maintained by [Abhishek Biradar](https://github.com/ABHI-2802)*
