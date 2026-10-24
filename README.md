# Olist E-Commerce Business Performance Analysis

**Tools:** `SQL` · `Python` · `Power BI`

An end-to-end business performance analysis of the [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), covering orders, customers, sellers, products, payments and reviews from a Brazilian marketplace.

> 🚧 **Project status: In progress.** I have started working with the data. Right now I'm focused on understanding the structure of the dataset and cleaning it before moving to deeper analysis.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Business Question](#business-question)
3. [Dataset](#dataset)
4. [Database Design](#database-design)
5. [Data Quality & Cleaning](#data-quality--cleaning)
6. [Exploratory Data Analysis](#exploratory-data-analysis)
7. [Revenue Analysis](#revenue-analysis)
8. [Key Insights](#key-insights)
9. [Recommendations](#recommendations)
10. [Tools & Technologies](#tools--technologies)
11. [Repository Structure](#repository-structure)

---

## Project Overview

Olist connects small businesses in Brazil to larger marketplaces. The dataset contains roughly 100k orders placed between 2016 and 2018, linked across multiple tables describing the customer, the order, the products, the seller, payments and reviews.

The goal of this project is to turn this raw relational data into business insight, starting from a solid, clean foundation.

## Business Question

The project will cover three areas of business performance: **revenue**, **delivery performance** and **customer satisfaction**. To keep it focused, I'm starting with **one business question on revenue**:

> **How is revenue performing, and what drives it?**
> *(Exact sub-questions will be finalised as the analysis progresses.)*

| Phase | Focus | Status |
|---|---|---|
| 1 | Revenue | 🔄 In progress |
| 2 | Delivery performance | 🚧 Coming soon |
| 3 | Customer satisfaction | 🚧 Coming soon |

## Dataset

The dataset consists of 9 tables. Below is the number of records in each:

| Table | Description | No. of Records |
|---|---|---:|
| `ol_customers` | Customer IDs and location | 99,441 |
| `ol_orders` | Order status and timestamps | 99,441 |
| `ol_order_items` | Items included in each order | 112,650 |
| `ol_order_payments` | Payment details per order | 103,886 |
| `ol_order_reviews` | Customer reviews and scores | 99,224 |
| `ol_products` | Product attributes | 32,951 |
| `ol_sellers` | Seller IDs and location | 3,095 |
| `ol_geolocation` | Zip code prefixes with latitude/longitude | 1,000,163 |
| `ol_product_category_name_translation` | Portuguese → English category names | 71 |


## Database Design

As a first step I studied how the tables relate to each other and created a **database diagram** that defines the **primary key** for each table wherever one exists and shows the relationships between the tables.

### Primary Keys

| Table | Primary Key |
|---|---|
| `ol_customers` | `customer_id` |
| `ol_orders` | `order_id` |
| `ol_order_items` | `order_id` + `order_item_id` (composite) |
| `ol_order_payments` | `order_id` + `payment_sequential` (composite) |
| `ol_order_reviews` | `review_id` + `order_id` (composite) |
| `ol_products` | `product_id` |
| `ol_sellers` | `seller_id` |
| `ol_product_category_name_translation` | `product_category_name` |
| `ol_geolocation` | *None – zip code prefixes repeat, so no natural key exists* |

### Database Diagram

The diagram below shows the primary keys and the relationships between the tables.

📌 [`**Database diagram:**`](database_diagram/database_diagram.png)    


## Data Quality & Cleaning

**Status: 🔄 In progress**

Before any analysis, I'm auditing the data for inconsistencies. The plan is to check every table for:

- [ ] **Missing values** (NULLs)
- [ ] **Blank / empty strings** that aren't technically NULL
- [ ] **Duplicate records** (including on primary keys)
- [ ] **Inconsistent formats** (dates, text casing, category names)
- [ ] **Invalid or illogical values** (e.g. negative prices, delivery dates before purchase dates)

For each issue found, I will:

1. Document what the issue is and where it occurs
2. Decide on a handling strategy (remove, impute, flag, or leave as is) and explain why
3. Record the before/after impact on the row counts

A full **data cleaning log** will be added here as the work is completed.

## Exploratory Data Analysis

🚧 *Coming soon*

## Revenue Analysis

🚧 *Coming soon*

## Key Insights

🚧 *Coming soon*

## Recommendations

🚧 *Coming soon*

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **SQL** | Database setup, data auditing and querying |
| **Python** | Data cleaning and analysis |
| **Power BI** | Dashboards and visualisation |

*Details on how each tool is used will be added as the project progresses.*

## Repository Structure

```
Olist-E-Commerce-Business-Performance-Analysis/
├── README.md
├── database_diagram/
│   └── database_diagram.png                    
├── SQL/
│   └── 
├── python_scripts/
│   └── 
├── docs/
│   └──  
└── images/                     

```

---

## Author : *[Meena Rawat]*

**Contact:** [`LinkedIn`](www.linkedin.com/in/meenarawat04) | [`Email`](mailto:meenarawat04@gmail.com)


*Dataset source: Olist & André Sionek, via Kaggle (CC BY-NC-SA 4.0).*
