# Batch-4-Assignment-7

## **📂 Database Setup**

1️⃣ **Install PostgreSQL** on your system if it is not already installed.

2️⃣ Open **pgAdmin** or your PostgreSQL terminal.

3️⃣ **Create a new database** named **"bookstore_db"** or any appropriate name.

4️⃣ **Connect** to the newly created database.

---

## **📂 Table Creation**

1️⃣ **Create a "books" table** with the following fields:

- `id` (Primary Key): A unique identifier for each book.
- `title`: The name of the book.
- `author`: The author of the book.
- `price`: The price of the book (must be non-negative, enforced via CHECK constraint).
- `stock`: The number of available copies in stock.
- `published_year`: The year the book was published.

2️⃣ **Create a "customers" table** with the following fields:

- `id` (Primary Key): A unique identifier for each customer.
- `name`: The full name of the customer.
- `email`: The email address of the customer (must be unique).
- `joined_date`: The date the customer registered (default to the current date).

3️⃣ **Create an "orders" table** with the following fields:

- `id` (Primary Key): A unique identifier for each order.
- `customer_id` (Foreign Key): References the `id` field in the "customers" table.
- `book_id` (Foreign Key): References the `id` field in the "books" table.
- `quantity`: The number of books ordered (must be greater than zero).
- `order_date`: The date and time when the order was placed (default to the current timestamp).

---

## **📂 Sample Data**

### **1️⃣ `books` Table**

```markdown
| id  | title                        | author            | price | stock | published_year |
| --- | ---------------------------- | ----------------- | ----- | ----- | -------------- |
| 1   | The Pragmatic Programmer     | Andrew Hunt       | 40.00 | 10    | 1999           |
| 2   | Clean Code                   | Robert C. Martin  | 35.00 | 5     | 2008           |
| 3   | You Don't Know JS            | Kyle Simpson      | 30.00 | 8     | 2014           |
| 4   | Refactoring                  | Martin Fowler     | 50.00 | 3     | 1999           |
| 5   | Database Design Principles   | Jane Smith        | 20.00 | 0     | 2018           |
```

### **2️⃣ `customers` Table**

```markdown
| id  | name    | email              | joined_date  |
| --- | ------- | ------------------ | ------------ |
| 1   | Alice   | alice@email.com    | 2023-01-10   |
| 2   | Bob     | bob@email.com      | 2022-05-15   |
| 3   | Charlie | charlie@email.com  | 2023-06-20   |
```

### **3️⃣ `orders` Table**

```markdown
| id  | customer_id | book_id | quantity | order_date  |
| --- | ----------- | ------- | -------- | ----------- |
| 1   | 1           | 2       | 1        | 2024-03-10  |
| 2   | 2           | 1       | 1        | 2024-02-20  |
| 3   | 1           | 3       | 2        | 2024-03-05  |
```

---

## **📂 PostgreSQL Problems & Sample Outputs**

1️⃣ **Find books that are out of stock.**

**Sample Output:**

```markdown
title
----------------------------
Database Design Principles
```

2️⃣ **Retrieve the most expensive book in the store.**

**Sample Output:**

```markdown
| id  | title       | author        | price | stock | published_year |
| --- | ----------- | ------------- | ----- | ----- | -------------- |
| 4   | Refactoring | Martin Fowler | 50.00 | 3     | 1999           |
```

3️⃣ **Find the total number of orders placed by each customer.**

**Sample Output:**

```markdown
| name    | total_orders |
| ------- | ------------ |
| Alice   | 2            |
| Bob     | 1            |
```

4️⃣ **Calculate the total revenue generated from book sales.**

**Sample Output:**

```markdown
total_revenue
-----------------
135.00
```

5️⃣ **List all customers who have placed more than one order.**

**Sample Output:**

```markdown
| name    | orders_count |
| ------- | ------------ |
| Alice   | 2            |
```

6️⃣ **Find the average price of books in the store.**

**Sample Output:**

```markdown
avg_book_price
----------------------------
35.00
```

7️⃣ **Increase the price of all books published before 2000 by 10%.**

**Sample Output:***(No table output, but affected rows will be updated accordingly.)*

```markdown
| id  | title                        | author             | price  | stock | published_year |
|-----|------------------------------|--------------------|--------|-------|----------------|
| 1   | The Pragmatic Programmer     | Andrew Hunt        | 44.00  | 10    | 1999           |
| 2   | Clean Code                   | Robert C. Martin   | 35.00  | 5     | 2008           |
| 3   | You Don't Know JS            | Kyle Simpson       | 30.00  | 8     | 2014           |
| 4   | Refactoring                  | Martin Fowler      | 55.00  | 3     | 1999           |
| 5   | Database Design Principles   | Jane Smith         | 20.00  | 0     | 2018           |
```

8️⃣ **Delete customers who haven't placed any orders.**

**Sample Output:***(No table output, but affected rows will be removed accordingly.)*

```markdown
| id  | name    | email              | joined_date  |
| --- | ------- | ------------------ | ------------ |
| 1   | Alice   | alice@email.com    | 2023-01-10   |
| 2   | Bob     | bob@email.com      | 2022-05-15   |
```

---

## **📂 Submission Instructions**

1️⃣ **Prepare a document** that includes:

- SQL code for **table creation, sample data insertion, and all queries**.
- **Comments** explaining the purpose of each query.
2️⃣ Save your file as **"PostgreSQL_Assignment.sql"** or another appropriate name.
3️⃣ Submit the document according to your instructor's guidelines.

---

## **📂 Bonus Section (Answer Any 10 Questions on readme.md)**

1. What is PostgreSQL?
2. What is the purpose of a database schema in PostgreSQL?
3. Explain the **Primary Key** and **Foreign Key** concepts in PostgreSQL.
4. What is the difference between the `VARCHAR` and `CHAR` data types?
5. Explain the purpose of the `WHERE` clause in a `SELECT` statement.
6. What are the `LIMIT` and `OFFSET` clauses used for?
7. How can you modify data using `UPDATE` statements?
8. What is the significance of the `JOIN` operation, and how does it work in PostgreSQL?
9. Explain the `GROUP BY` clause and its role in aggregation operations.
10. How can you calculate aggregate functions like `COUNT()`, `SUM()`, and `AVG()` in PostgreSQL?

---

## **✅ Final Notes**

- Make sure your SQL queries **run successfully** before submitting.
- Use **comments** to explain complex queries.
- Focus on **clean formatting and proper indentation** for readability.
