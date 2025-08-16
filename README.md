# 🎵 SQL Music Store Analysis

## 📌 Project Overview
This project is an **SQL-based analysis** of a digital music store database.  
The goal is to extract meaningful insights about **customers, sales, employees, and tracks** using SQL queries.  

It covers:
- Writing optimized SQL queries
- Data analysis using relational database concepts
- Business insights from music sales and customer behavior

---

## 📂 Dataset Description
The dataset represents a **music store database**, including the following tables:

- **Customers** → Customer details (name, location, email, etc.)
- **Invoices** → Sales invoices with purchase details
- **InvoiceLines** → Track-level invoice details
- **Tracks** → Songs with genre, album, and duration
- **Albums** → Music albums
- **Artists** → Artists of the albums
- **Genres** → Song categories
- **Employees** → Support representatives
- **Playlists** → Collections of tracks

---

## 🛠️ Tools & Technologies
- **SQL** (PostgreSQL / MySQL / SQLite – depending on your setup)
- **DB Browser / SQL Client**
- **Git & GitHub** (for version control)

---

## 🔍 Analysis Performed
Some key analysis performed includes:

1. 🎤 **Top Artists & Genres** – Most popular artists and genres by sales  
2. 💰 **Revenue Analysis** – Total sales per country, customer, and invoice  
3. 🛒 **Customer Insights** – Highest spending customers and purchase frequency  
4. 👨‍💼 **Employee Performance** – Sales support representative analysis  
5. 📀 **Track Insights** – Most purchased tracks, duration analysis  

---

## 📊 Example Queries

### 1. Find the top 5 customers by total spending:
SELECT c.FirstName, c.LastName, SUM(i.Total) AS TotalSpent
FROM Customer c
JOIN Invoice i ON c.CustomerId = i.CustomerId
GROUP BY c.CustomerId
ORDER BY TotalSpent DESC
LIMIT 5;

2.Find the most popular music genre by number of tracks sold:
SELECT g.Name AS Genre, COUNT(il.Quantity) AS TracksSold
FROM InvoiceLine il
JOIN Track t ON il.TrackId = t.TrackId
JOIN Genre g ON t.GenreId = g.GenreId
GROUP BY g.GenreId
ORDER BY TracksSold DESC
LIMIT 1;

3.How to Run the Project

Clone the repository:

git clone https://github.com/yourusername/SQL_Music_Store_Analysis.git


Open the database in your SQL client (SQLite / MySQL / PostgreSQL).

Run the queries from the queries.sql or analysis notebook.

Explore insights and modify queries as needed.
