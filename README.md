**Zepto E-Commerce Sales & Customer Insights using SQL**

Welcome to the Zepto E-Commerce SQL Data Analysis Project – a hands-on portfolio project focused on solving real-world business problems using SQL. This project simulates an e-commerce business (inspired by Zepto) where data analysis is used to derive insights into customer behavior, sales performance, and operational efficiency.

**🔍 Project Objective**

The primary goal of this project is to demonstrate data analysis and problem-solving skills using SQL in an e-commerce environment. You’ll explore large datasets and use SQL queries to:

Analyze customer orders

Track product performance

Evaluate delivery efficiency

Identify business trends

Generate insights for business decision-making

**🛠 Tools & Technologies**

Database: PostgreSQL / MySQL (depending on your setup)

Language: SQL

Platform: GitHub, DB tools  pgAdmin / MySQL Workbench

Visualization (Optional): Excel 

**📁 Dataset Overview**

**sku_id:**

Type: SERIAL (auto-incremented integer)

Purpose: Uniquely identifies each product entry in the dataset.

**category:**

Type: VARCHAR(120)

Purpose: Describes the broad product category (e.g., Snacks, Beverages, Household, etc.). This field allows you to group products for higher-level analyses.

**name:**

Type: VARCHAR(150) (NOT NULL)

Purpose: Provides the product name. This field helps in identifying products and is used in queries to check for duplicate product entries or frequently listed items.

**mrp:**

Type: NUMERIC(8,2)

Purpose: Represents the Maximum Retail Price (MRP) of the product in rupees. This is used to assess pricing strategies and perform price comparisons.

**discountPercent:**

Type: NUMERIC(5,2)

Purpose: Indicates the discount percentage being offered on the product. It is crucial for evaluating best value offerings and promotional analysis.

**availableQuantity:**

Type: INTEGER

Purpose: The quantity of products available in the inventory. This field directly affects revenue calculations and stock management.

**discountedSellingPrice:**

Type: NUMERIC(8,2)

Purpose: The selling price after applying the discount. It’s used to compute revenue projections and to compare against the MRP.

**weightInGms:**

Type: INTEGER

Purpose: Records the weight of the product in grams. This value is useful when calculating the price per unit weight or categorizing products as low, medium, or bulk.

**outOfStock:**

Type: BOOLEAN

Purpose: A flag indicating whether the product is currently out of stock. This field is helpful to identify products that might need restocking or to filter out unavailable products during analysis.

**quantity:**

Type: INTEGER

Purpose: Although similar to availableQuantity, this field can be used to capture additional quantity-related metrics like ordered quantity or packaging details, depending on the business context.

🔧 Project Workflow

Here's a step-by-step procedure

**1.Database Creation and Table Creation**

create table zepto(
sku_id SERIAL PRIMARY KEY,
category VARCHAR(120),
name VARCHAR(150) NOT NULL,
mrp NUMERIC(8,2),
discountPercent NUMERIC(5,2),
availableQuantity INTEGER,
discountedSellingPrice NUMERIC(8,2),
weightInGms INTEGER,
outOfStock BOOLEAN,
quantity INTEGER
);

**2.Import Data**

Loaded CSV using pgAdmin's import feature.

To import this into PostgreSQL via a GUI tool, save the above content into a file called zepto_data.sql, then:

PostgreSQL (pgAdmin):
Open query tool → Load the script → Execute.

🔍 3. Data Exploration

Counted the total number of records in the dataset

→ Ensured the dataset was fully loaded and ready for analysis.

Viewed a sample of the dataset to understand structure and content

→ Checked column formats, data types, and a few example rows using LIMIT.

Checked for null values across all important columns

→ Verified data completeness and identified any missing fields needing cleaning.

Identified distinct product categories available in the dataset

→ Used SELECT DISTINCT to understand the diversity of product types.

Compared in-stock vs out-of-stock product counts

→ Grouped products using the outOfStock flag to evaluate inventory availability.

Detected products listed multiple times, representing different SKUs

→ Used GROUP BY name to find duplicate product names with different IDs or packaging.

🧼 4. Data Cleaning

Identified and removed rows where MRP or discountedSellingPrice was zero

→ These entries were considered invalid or placeholder values.

Checked for and ensured absence of null values in key columns

→ Verified completeness across product name, category, pricing, and inventory.

Converted mrp and discountedSellingPrice from paise to rupees

→ Improved consistency and human readability (divided by 100 where needed).

Standardized product naming for consistency (optional enhancement)

→ Could include trimming spaces, lowercasing, or resolving duplicates.

**📈 5. Business Insights**

🛒 Best Value Products

→ Identified the top 10 products with the highest discount percentages.

🏷️ Premium Products Out of Stock

→ Found high-MRP items currently unavailable for purchase (missed revenue).

💰 Estimated Category-Wise Revenue

→ Multiplied discounted price by available quantity to project revenue potential.

📉 Low Discount on High-MRP Products

→ Pinpointed expensive items with minimal discounts, potentially slowing sales.

📦 Inventory Distribution by Weight

→ Grouped products into Low (<1kg), Medium (<5kg), and Bulk (5kg+) categories.

⚖️ Best Price per Gram Analysis

→ Sorted products based on cost efficiency per gram for value insights.

**🛠️ How to Use This Project**
Follow these steps to explore and run the Zepto SQL Data Analysis Project on your own system:

1. 📥 Clone the Repository

git clone https://github.com/padmasharadhabadrinath/zepto-SQL-data-analysis-project.git
cd zepto-SQL-data-analysis-project


2. 🗃️ Load the Dataset
You can use either of the following:

Option A: Load from CSV

File: zepto_v2.csv

Import it using a tool like pgAdmin, DBeaver, or MySQL Workbench using the IMPORT CSV function.

Option B: Use SQL Script

File: Zepto_SQL_data_analysis.sql

Contains the CREATE TABLE statement and all INSERT commands for sample data.

Run it directly in your SQL IDE or CLI.

3. 🧪 Run SQL Queries
Use your preferred SQL tool to execute queries:

Open Zepto_SQL_data_analysis.sql or copy queries from the README

Perform data exploration, cleaning, and business insight queries

Modify or extend queries based on your learning goals











