# Music-Store-Analysis
SQL-based analysis project using a music store database. Includes DDL, DML, and advanced SQL queries to extract customer insights, top artists, and genre trends.

# 🎵 Music Store SQL Analysis Project

This project showcases comprehensive data analysis on a music store database using SQL. It involves data exploration through advanced queries to extract business insights like top genres, best customers, high revenue cities, and artist performance.

---

## 🗃️ Database Schema

The schema is based on a relational database with the following tables:

- **employee**
- **customer**
- **invoice**
- **invoice_line**
- **track**
- **playlist**
- **playlist_track**
- **artist**
- **album**
- **media_type**
- **genre**

Entity relationships are established through foreign keys and normalized structures.

🔗 [Database ER Diagram]
![image](https://github.com/user-attachments/assets/7d1cee25-ea57-4cbd-b2f5-1edccec7f826)

---

## ⚙️ Tech Stack

- SQL (Structured Query Language)
- PostgreSQL / MySQL
- Excel (for data prechecks if needed)

---

## 📂 Files Included

| File | Description |
|------|-------------|
| `Music Store (SQL Project).sql` | Contains all analysis queries |
| `Create Table Queries (SQL Project).docx` | SQL DDL: Table creation scripts |
| `music store data (ALL CSV Files).zip` | Raw data files in CSV format |
| `Music Store Schema (SQL Project).png` | Entity Relationship Diagram |
| `Musuc Store Analysis Data Files.rar` | Consolidated archive of all resources |

---

## 🔍 Key Business Queries Implemented

1. Find the **senior-most employee**.
2. Identify **countries with the most invoices**.
3. Discover **top 3 invoices by amount**.
4. Which **city has the best customers**?
5. Who is the **best customer** by total spending?
6. List **Rock music listeners** and their emails.
7. **Top 10 Rock artists** by track count.
8. Tracks **longer than average duration**.
9. **Spending per customer on top artists**.
10. **Most popular genre** per country.
11. **Top customer** in each country by spending.

All queries use SQL features such as:
- `JOIN`, `GROUP BY`, `ORDER BY`
- CTEs (`WITH`)
- Window functions like `ROW_NUMBER()`
- Subqueries and nested logic

---

## 💡 Sample Query (Top Customer)

```sql
SELECT customer.customer_id, customer.first_name, customer.last_name, SUM(total) AS total_spending
FROM customer
JOIN invoice ON customer.customer_id = invoice.customer_id
GROUP BY customer.customer_id
ORDER BY total_spending DESC
LIMIT 1;
