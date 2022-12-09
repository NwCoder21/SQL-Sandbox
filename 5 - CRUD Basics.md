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

![image](https://user-images.githubusercontent.com/107522496/206698216-d6401937-dd56-4b9c-9d24-bbd0f2e020c1.png)

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

`WHERE` is used with `SELECT` and when updating and deleting.

At the moement, when we use `SELECT`, we're selecting every single row. So, if we use:

```sql
SELECT age FROM employees;
```

we will get 7 rows back. `WHERE` allows us to retreive specfic rows back which meet a stated condition.

---

For example: 

```sql
SELECT * FROM employees
WHERE age=35;
```

![image](https://user-images.githubusercontent.com/107522496/206692479-0357cb89-b267-477e-8ea6-4caf78c2a34c.png)

Here, we see two rows. 

---

Another exmaple is 

```sql
SELECT first_name, age FROM employees
WHERE age=35;
```

![image](https://user-images.githubusercontent.com/107522496/206692808-22c12523-87b1-43fa-8795-878c53c52589.png)

Here, we are retriving two columns, where the age is equal to 35.

---


Note: we do not have to select `age` if we are trying to use `WHERE` with age, but we don't. We can only get the names from employees where age equals four.

```sql
SELECT first_name, last_name FROM employees
WHERE age=35;
```

![image](https://user-images.githubusercontent.com/107522496/206693445-0e557d05-1b69-498c-ac97-dae431ba74e6.png)

Here, `WHERE age=35` happens first, program checks the rows in the age column which have 35, then `SELECT first_name, last_name FROM employees`. This means we do not have to retrive a column using `SELECT` in order to work with that column using `WHERE`.

---

# Using a string with the `WHERE` Clause.

Can also use a string with `WHERE`.

```sql
SELECT * FROM employees
WHERE last_name=`Jones`;
```

![image](https://user-images.githubusercontent.com/107522496/206695302-9a2271cd-dfe7-4d88-b500-20cf311f03b6.png)

Note: When searching for a string using `WHERE`, search will be case insensitive. However, we can enforce case senstivity.

![image](https://user-images.githubusercontent.com/107522496/206695615-81a54180-41c3-4639-bd87-b58830e9c379.png)

Here, even though the name has been spelt as Jones (capital J), we can search for it using jones.

---

Excerises:

Q1: Print out all IDs for everyone on database:

![image](https://user-images.githubusercontent.com/107522496/206698412-90255478-2734-4822-b793-5f0a1a66eb48.png)


---

Q2: Output all rows for `first_name` and `department`. 

![image](https://user-images.githubusercontent.com/107522496/206698784-01964145-2473-4c8e-89d7-969df8101388.png)

---

Q3; Output  `first_name`, `last_name` and `department` for rows where department equals maths.

![image](https://user-images.githubusercontent.com/107522496/206699123-0dc5a9e8-7fb2-4dbf-b7dc-d85689152322.png)

---

Q4: Output everything for those rows where id is the same as age. 

![image](https://user-images.githubusercontent.com/107522496/206699334-920a294e-1b39-4c24-bf48-104120f4bed5.png)

---

<! -- Lesson 64 - Aliases --> 

# Aliases using the `AS` Keyword

When we are selecting data, we can rename a column to make it shorter or easier to understand. So it's not the same as renaming the column forever, it's just for that particular output we change a column's name.

> this is temporay, only for that query.

---


![image](https://user-images.githubusercontent.com/107522496/206703421-88b131e5-36b3-4723-9090-da6a3153e551.png)

Here, have renamed the `first_name` column as `name` for the output of this query.

---

![image](https://user-images.githubusercontent.com/107522496/206702460-d45b17d8-4ecf-4b97-8696-498c2ed77f05.png)

Here, the column is actually named `department`, but for the output ofthis query, we have namedit depart. If we then run the `DESC` command, it still be named `department`:

![image](https://user-images.githubusercontent.com/107522496/206702823-cb0bd614-8d30-446f-a1eb-11e22d8af3c4.png)

---

So this isn't just about renaming a column when you print it out. When we get into things such as joining data together or writing more complex select queries that are really complicated, we might have some resulting data that doesn't really have a name. We use the `AS` keyword to give it a meaningful name.

---

<! -- Lesson 66 - Using UPDATE --> 

# Using UPDATE













