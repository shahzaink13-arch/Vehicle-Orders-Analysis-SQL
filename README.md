# 📊 SQL Vehicle Orders Analysis

![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Window Functions](https://img.shields.io/badge/Window_Functions-A78BFA?style=for-the-badge)
![CTEs](https://img.shields.io/badge/CTEs-38BDF8?style=for-the-badge)
![Multi Table Joins](https://img.shields.io/badge/Multi_Table_JOINs-FB923C?style=for-the-badge)
![UNION](https://img.shields.io/badge/UNION_Queries-4ADE80?style=for-the-badge)

> Advanced SQL analysis across 8 tables covering sales (2015–2017), customers, products, returns & territories with window functions, CTEs, multi-table JOINs and complete data cleaning.

---

## 🌐 [👉 View Full Project Page](https://shahzaink13-arch.github.io/SQL-Weekend-Analysis/)

---

## 📊 Project Stats

| Metric | Value |
|--------|-------|
| 🗄️ Tables | 8 (Customers, Products, Sales2015/16/17, Returns, Territories, Categories) |
| 📅 Data Range | Sales 2015, 2016 & 2017 |
| 🛠️ SQL Concepts | 10+ |
| 🔗 JOIN Types | INNER, LEFT, RIGHT, CROSS, SELF |

---

## 🧩 Analysis Performed

| Area | Key Queries |
|------|-------------|
| 👥 Customer Analysis | Income cleaning, occupation avg, self join (same last name/birthdate), income rank |
| 📦 Product Analysis | Top 10 by price, gross profit, avg profit by color, NTILE quartile, never-returned |
| 📈 Sales Analysis | UNION 3 years, top revenue products, seasonal trends, cumulative sales |
| 🔄 Returns Analysis | Returns by category/year/region, top 10 returned, 4-table JOIN |
| 🪟 Window Functions | Moving avg (3 & 5 day), DENSE_RANK, NTILE, cumulative SUM, MAX per group |
| 🧹 Data Cleaning | STR_TO_DATE, CASE WHEN for mixed formats, REPLACE, RPAD, INSTR |

---

## ⚡ Key Query — Seasonal Sales Trends
```sql
WITH AllSales AS (
  SELECT * FROM Sales2015
  UNION
  SELECT * FROM Sales2016
  UNION
  SELECT * FROM Sales2017
)
SELECT
  YEAR(s.OrderDate)  AS Year,
  MONTH(s.OrderDate) AS Month,
  pc.CategoryName,
  SUM(s.OrderQuantity) AS TotalOrderQty
FROM AllSales s
JOIN Products p           ON p.ProductKey = s.ProductKey
JOIN ProductSubcategories ps ON p.ProductSubcategoryKey = ps.ProductSubcategoryKey
JOIN ProductCategories pc    ON pc.ProductCategoryKey = ps.ProductCategoryKey
GROUP BY 1, 2, 3;
```

---

## 🛠️ SQL Concepts Applied

`5 JOIN Types` `CTEs` `Window Functions` `UNION` `Date Cleaning` `String Functions` `Aggregations` `DENSE_RANK` `NTILE` `Moving Average` `Subqueries` `Data Cleaning`

---

## 👤 Author

**Shahzain Sher Khan** — Data Analyst, Bhopal India

[![GitHub](https://img.shields.io/badge/GitHub-shahzaink13--arch-181717?style=flat&logo=github)](https://github.com/shahzaink13-arch)
[![Email](https://img.shields.io/badge/Email-Shahzaink13@gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:Shahzaink13@gmail.com)
