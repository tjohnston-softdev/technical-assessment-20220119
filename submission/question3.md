### Question 3

---

A company uses an internal web application to track its customers. The web application needs a paged list of customers from the following table, ordered by name from A to Z:

```sql
TABLE customers
	id INTEGER NOT NULL PRIMARY KEY
	name VARCHAR(30) NOT NULL
```

Finish the `GetCustomerPage` stored procedure so that it returns a list of customers for the requested page, with the `id` and `name` for each customer. Page numbers start from 1.

See the [example case](../attachments/question3-example.sql) for more details.

```sql
-- Write only the T-SQL code that solves the problem and nothing else
CREATE PROCEDURE GetCustomerPage (@page INTEGER, @pageSize INTEGER) AS
BEGIN
    SELECT id, name FROM customers;
END;
```

\
\
**Answer:**

```sql
CREATE PROCEDURE GetCustomerPage (@page INTEGER, @pageSize INTEGER) AS
BEGIN
    
    DECLARE @skip INTEGER;
    SET @skip = (@page - 1) * @pageSize;
    
    SELECT id, name
    FROM customers
    ORDER BY name
    OFFSET @skip ROWS
    FETCH NEXT @pageSize ROWS ONLY;
END;
```


---

**Previous:** [Question 2](./question2.md)  
**Next:** [Question 4](./question4.md)

[Return to Index](../readme.md)