# 🎧 SQL Practice – (Chinook Database)

## 📌 Overview
This project continues my **SQL learning journey ** using the **Chinook SQLite database**.  
Today, I focused on **advanced querying techniques** that go beyond basic analytics.  
These queries simulate real-world scenarios such as finding missing relationships, comparing data sets, and ranking results.

---

## 🗂️ Database Used
- **Chinook SQLite** (downloadable from [Chinook Database GitHub](https://github.com/lerocha/chinook-database))

---

## ✅ Concepts Practiced on Day 4
- 🔹 **NOT EXISTS** → to detect missing relationships (e.g., artists without albums)  
- 🔹 **LEFT JOIN with NULL filtering** → to find unassigned employees  
- 🔹 **Set Operations (`UNION`)** → to compare datasets (e.g., Rock vs Jazz sales)  
- 🔹 **Window Functions with Ranking** → to rank genres within each country  
- 🔹 **HAVING with COUNT(DISTINCT)** → to find customers who purchased from multiple genres  
 

---

## 🧠 Business Questions Answered
1. **Which artists have no albums in the database?**
2. **Which customers purchased tracks from multiple genres?**
3. **Compare total sales revenue of Rock vs Jazz music.**
4. **Which employees do not have any customers assigned to them?**
5. **Top 3 genres by revenue within each country.**


---

## 💻 Sample Query (Using NOT EXISTS)
```sql
SELECT ar.Name AS Artist
FROM artist ar
WHERE NOT EXISTS (
    SELECT 1
    FROM album al
    WHERE al.ArtistId = ar.ArtistId
);

