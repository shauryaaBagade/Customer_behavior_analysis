Customer Shopping Behaviour Analysis

An end-to-end data analytics project focused on understanding customer purchasing patterns, preferences, and behaviour using Python, PostgreSQL, SQL, and Power BI.

Project Overview

This project analyzes customer shopping data to uncover meaningful business insights such as purchasing trends, customer segments, product preferences, discount usage, and category-level performance.

The workflow covers data cleaning and exploratory analysis in Python, SQL-based business analysis in PostgreSQL, and interactive dashboard creation in Power BI.

Tools & Technologies

Python

Pandas

PostgreSQL

pgAdmin 4

SQL

Power BI

Jupyter Notebook / VS Code

Project Workflow

Imported and explored the customer shopping dataset using Python.

Cleaned and prepared the data using Pandas.

Loaded the processed dataset into PostgreSQL.

Used SQL queries to answer key business questions.

Analyzed customer segments, purchasing patterns, discounts, and product performance.

Built an interactive Power BI dashboard to present the findings visually.

Key Analysis

The project includes analysis such as:

Customer segmentation based on previous purchases

Most purchased products within each category

Products with the highest discount usage

Customer purchasing behaviour and preferences

Category and product-level performance

Purchase patterns across different customer groups

Example SQL Analysis

WITH item_count AS (
    SELECT
        category,
        item_purchased,
        COUNT(customer_id) AS total_orders,
        ROW_NUMBER() OVER (
            PARTITION BY category
            ORDER BY COUNT(customer_id) DESC
        ) AS item_rank
    FROM customer
    GROUP BY category, item_purchased
)

SELECT
    category,
    item_purchased,
    total_orders,
    item_rank
FROM item_count
WHERE item_rank <= 3;

This query identifies the top 3 most purchased products within each category.

Project Structure

customer-shopping-behaviour-analysis/
│
├── customer_shopping_behavior.csv
├── shopping_analysis.ipynb
├── customer_behavior_queries.sql
├── README.md
└── dashboard/

Key Skills Demonstrated

Data Cleaning

Exploratory Data Analysis

SQL

Window Functions and CTEs

Customer Segmentation

Business Insight Generation

Data Visualization

Dashboard Development

Outcome

The project demonstrates an end-to-end analytics workflow that transforms raw customer shopping data into actionable business insights through Python, SQL, PostgreSQL, and Power BI.

Author

Shauryaa Bagade
