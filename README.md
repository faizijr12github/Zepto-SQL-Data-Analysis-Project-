# 🛒 Zepto E-commerce Data Analysis with SQL

Welcome to my SQL Data Analyst Portfolio Project!
This project uses real-world inventory data from **Zepto**, a fast-growing e-commerce startup in India.
It shows how data analysts work with real, messy data to help businesses make smart decisions.

---

## 📌 Project Overview

In this project, I used SQL to:

✅ Set up a real e-commerce inventory database
✅ Explore the data to find patterns in products, prices, and stock
✅ Clean the data by fixing missing or wrong values
✅ Write useful SQL queries to find insights for business decisions

---

## 📁 Dataset Info

* 📦 The data is from **Kaggle** (scraped from Zepto’s product listings)
* Each row is a product SKU (stock keeping unit)
* Products may repeat with different weights, discounts, or packaging – just like real apps!

### 📊 Columns Explained

| Column                   | Description                                       |
| ------------------------ | ------------------------------------------------- |
| `sku_id`                 | Unique product ID                                 |
| `name`                   | Product name                                      |
| `category`               | Product category (e.g. Fruits, Snacks)            |
| `mrp`                    | Price before discount (converted from paise to ₹) |
| `discountPercent`        | Discount applied on MRP                           |
| `discountedSellingPrice` | Final price after discount (₹)                    |
| `availableQuantity`      | Items in stock                                    |
| `weightInGms`            | Product weight in grams                           |
| `outOfStock`             | True if product is out of stock                   |
| `quantity`               | Number of units or quantity per pack              |

---

## 🔧 Project Workflow

### 1. 🧱 Table Creation

Created a PostgreSQL table:

```sql
CREATE TABLE zepto (
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
```

---

### 2. 📥 Data Import

Used pgAdmin to import the CSV file.
If needed, use this command in PostgreSQL:

```sql
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
            discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv' 
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
```

🛠 Tip: Save the CSV in **UTF-8** format to avoid errors.

---

### 3. 🔍 Data Exploration

* Counted total records
* Viewed sample data
* Found null values
* Listed product categories
* Compared in-stock vs out-of-stock
* Found duplicate products with different SKUs

---

### 4. 🧹 Data Cleaning

* Removed rows with `MRP` or `Selling Price` as zero
* Converted prices from **paise to rupees**
* Ensured better readability and consistency

---

### 5. 📊 Business Insights (Using SQL)

* 🏆 Top 10 best-discounted products
* 🚫 High-MRP products out of stock
* 💰 Revenue estimates by category
* ❗ Expensive products with low discounts
* 📈 Top 5 categories with highest average discount
* ⚖️ Price per gram – best value products
* 📦 Grouped products by weight: Low / Medium / Bulk
* 🏋️‍♀️ Total inventory weight by category

---

## 🛠 How to Use This Project

1. **Clone the repository**
2. Open the SQL file: `zepto_SQL_data_analysis.sql`
3. Create a new database in PostgreSQL (pgAdmin or other client)
4. Run the SQL file step-by-step
5. Import the dataset (UTF-8 format recommended)
6. Explore, clean, and analyze the data using SQL
7. Watch the full walkthrough video (if available) 🎥

---

## 📌 Tools Used

* PostgreSQL
* pgAdmin
* SQL
* Kaggle dataset

---

## 📬 Contact

If you like this project or have questions, feel free to connect!
📧 Email: faizan.jr12@gmail.com
🔗 LinkedIn: https://www.linkedin.com/in/muhammad-faizan-074575250/

---
