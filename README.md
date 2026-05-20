# sql e-commerce sales analysis

## project overview

this project analyzes e-commerce sales data using postgresql and sql queries to generate business insights related to customers, products, revenue, and sales performance.

the project demonstrates practical sql skills including joins, aggregate functions, ctes, subqueries, window functions, views, indexing, and stored procedures.

---

# objectives

- analyze customer purchasing behavior
- identify top-selling products
- generate revenue insights
- practice advanced sql concepts
- build a resume-ready sql project

---

# technologies used

- postgresql
- sql
- pgadmin
- github
- csv datasets

---

# database schema

the project contains the following tables:

## customers

| column name | description |
|---|---|
| customer_id | unique customer id |
| customer_name | customer name |
| city | customer city |
| signup_date | registration date |

---

## products

| column name | description |
|---|---|
| product_id | unique product id |
| product_name | product name |
| category | product category |
| price | product price |

---

## orders

| column name | description |
|---|---|
| order_id | unique order id |
| customer_id | customer reference |
| product_id | product reference |
| quantity | quantity ordered |
| order_date | order date |

---

# sql concepts used

- joins
- group by
- aggregate functions
- subqueries
- common table expressions (ctes)
- window functions
- ranking functions
- views
- stored procedures
- indexing
- query optimization

---

# analysis performed

## customer analysis
- top customers by spending
- customers with highest orders
- customer distribution by city

## product analysis
- best-selling products
- highest revenue products
- category-wise product analysis

## sales analysis
- monthly revenue trend
- running revenue totals
- revenue contribution percentage

## advanced sql analysis
- top products in each category
- ranking queries
- cte queries
- duplicate detection
- second highest revenue product

---

# sample queries

## top customers by spending

```sql
select c.customer_name,
       sum(p.price * o.quantity) as total_spent
from orders o
join customers c
on o.customer_id = c.customer_id
join products p
on o.product_id = p.product_id
group by c.customer_name
order by total_spent desc
limit 10;
```

---

## monthly revenue trend

```sql
select date_trunc('month', order_date) as month,
       sum(quantity * price) as revenue
from orders o
join products p
on o.product_id = p.product_id
group by month
order by month;
```

---

# project structure

```text
sql-ecommerce-analysis/
│
├── dataset/
│   ├── customers.csv
│   ├── products.csv
│   └── orders.csv
│
├── sql_queries/
│   ├── schema.sql
│   ├── analysis_queries.sql
│   └── advanced_queries.sql
│
├── screenshots/
│
└── README.md
```

---

# key insights

- identified top revenue-generating products
- analyzed customer spending behavior
- tracked monthly revenue growth
- compared category-wise sales performance
- generated business reports using sql

---

# future improvements

- power bi dashboard integration
- python data analysis
- sales forecasting
- dashboard visualization
- query performance optimization

---

# author

suraj tiwari
