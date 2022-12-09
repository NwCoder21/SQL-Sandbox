# 5 - CRUD Basics

CRUD stands for:

* Create - how to create an entry - `INSERT INTO`
* Read - how to read an entry - `SELECT FROM `
* Update - How do we alter a row that already exists?
* Delete - How do we delete rows?

These are the four basic actions that we want to be able to do wth our data.

Until now, we have looked at how to create entries using the `INSERT INTO` command and retrieve entries using the `SELECT` commmand. 

---

![image](https://user-images.githubusercontent.com/107522496/206684867-25da807c-12f9-4b8e-b4cb-ae28eea31d07.png)

Recap: this is how we insert data.

---

In this section will be focusing on more Read, Update, and Delete and how we can update and delete information in our database. 

---

This is the table and data we will be working with:

![image](https://user-images.githubusercontent.com/107522496/206687025-cd037ef7-eba5-4c62-b0f0-b50315aa000a.png)

```sql
CREATE TABLE employees (
id INT AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR (50),
last_name VARCHAR (50),
age INT
);

INSERT INTO employees (first_name, last_name, age)
VALUES('Guy', 'Cheshire', 25),
	  ('John', 'White', 19),
      ('Jane', 'Doe', 29),
      ('Andrew', 'Jones', 35),
      ('Rebecca', 'Harvey', 23);
      
SELECT *FROM employees;
```

---
<! -- Lesson 57 - Officially Introducing SELECT --> 

# Read - SELECT in More Depth

Up until now, we have been using 

```sql
SELECT * FROM <table_name>;
```

This retrieves/reads all records from a table. 

`*` represents/means all rows from every column.

However, we do not always want all columns. We can also narrow down our search and only have certain columns retrieved back to us. For example, if wanted only the `last_name` column, we would write: 

```sql
SELECT last_name FROM employees;
```

![image](https://user-images.githubusercontent.com/107522496/206689364-4c4e70a6-e4cc-43b0-9db1-2c7ab12cf107.png)

---

# Combining Multiple Columns with `SELECT`

To retrive multiple columns from a table using `SELECT`, we seperate each column using a comma, `,`. For example, 


```sql
SELECT first_name, age FROM employees;
```

![image](https://user-images.githubusercontent.com/107522496/206689850-ad1aad5e-7a76-4b51-a063-14e0f7a20f33.png)

---

<! -- Lesson 59 - The WHERE Clause --> 

# The WHERE Clause 





















