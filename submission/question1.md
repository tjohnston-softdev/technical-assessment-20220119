### Question 1

---

The `developers` table contains a single `name` column. This column has been populated by hand and contains erroneous data, including inaccurate letter casing, and leading/trailing whitespace.

Executing the query should return all developers whose name contains 'John', regardless of letter case, and with all leading/trailing whitespace removed. However, it currently returns no results.

Fix the bugs.

```sql
-- Modify the SELECT statement below
SELECT name AS name FROM developers WHERE name = 'John';
```

\
\
**Answer:**

```sql
SELECT TRIM(name) AS name
FROM developers
WHERE LOWER(name) LIKE '%john%';
```


---

**Previous:**  
**Next:** [Question 2](./question2.md)

[Return to Index](../readme.md)