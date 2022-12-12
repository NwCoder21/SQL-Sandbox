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
<!-- Lesson 57 - Officially Introducing SELECT --> 

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

<!-- Lesson 59 - The WHERE Clause --> 

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

<!-- Lesson 64 - Aliases --> 

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

<!-- Lesson 66 - Using UPDATE --> 

# Using `UPDATE`

Here, we are looking at how do we update existing rows in a table? `UPDATE` allows us to change data that's already in a table.

![image](https://user-images.githubusercontent.com/107522496/206719169-d171ecd8-5eef-49b4-b34e-63ed525b7ac1.png)

```sql
UPDATE <table_name> SET <Column-department What_are_we_trying_to_update> WHERE <which_rows_we_want_to_update>
```

![image](https://user-images.githubusercontent.com/107522496/206725814-c7a4f6d7-b467-4813-a1fe-be254daaecbc.png)

```sql
UPDATE employees SET department='Art'
WHERE department='Science';
```
> IMPORTANT! - if we just used `UPDATE employees SET department='Art';`, it would change all fields in the department column to `Art`. 
---

![image](https://user-images.githubusercontent.com/107522496/206726192-21649cda-aca3-422f-b19c-33417c2d7101.png)

Here, Guy Cheshire's age was 25, but we want to change it to 35. 

```sql
UPDATE employees SET age=35
WHERE first_name='Guy';
```

> IMPORTANT! - if we just used `UPDATE employees SET age=35;`, it would change all fields in the age column to `35`. 

`UPDATe` is mainly used with a `WHERE`.

---

# Updating Multiple Columns in One Go

Can also update multiple columns in one go. For example:

![image](https://user-images.githubusercontent.com/107522496/206740332-9bc2d505-6e7f-44a9-94ae-f7427866d73b.png)

This will set everyone's current status to Employed, and their age to 21. 

---

<!-- Lesson 66 - Using UPDATE --> 

# Tip - Try `SELECT`ing Before You `Update`

To prevent any unexpected updates or overwriting the wrong fields, it is recommended that you select whatever you're trying to update before you actually perform the update. For example, we want to change Guy Cheshire's age to 35.


```sql
UPDATE employees SET age=25 WHERE first_name='Guy';
```
 Instead of jumping straight into updating the field, use the end part, `WHERE first_name='Guy'` and add it to a `SELECT * FROM <table_name>`, such as:

```sql
SELECT * FROM employees WHERE first_name='Guy';
```

This will show us what we will be targeting when using the `UPDATE` command, such as:

![image](https://user-images.githubusercontent.com/107522496/206728536-39d5308c-2065-4d59-8d5a-79797b2b3f24.png)

Here, we are first checking our target row.

---

![image](https://user-images.githubusercontent.com/107522496/206729223-df9bac14-67d5-4548-b962-d7af6ea3e173.png)

Now, using the UPDATE command, we have update Guy's age to 35.

---

# UPDATE excerise

1. Change Andrew's name to Andy.
2. Change Chesire to Matt
3. Change all ages to 25 where departments are English 

![image](https://user-images.githubusercontent.com/107522496/206730439-0ee657d2-da1f-4bd0-aeeb-e553667128a6.png)


--- 

# Solution - Change Andrew's name to Andy.

![image](https://user-images.githubusercontent.com/107522496/206730721-2542f2a3-6e46-4225-b351-db8d6f87c98b.png)

First, I have used a `SELECT` statement to pinpoint what I will be changing with the `UPDATE` command.

![image](https://user-images.githubusercontent.com/107522496/206731029-0e6b91b8-c56a-4a39-8060-d1ac7c127673.png)

Then using `UPDATE`, I chnaged it to Andy.

---


# Solution - Change Chesire to Matt

![image](https://user-images.githubusercontent.com/107522496/206731381-ae12ba9a-e55e-41ad-8307-a41059c1d5ca.png)

First, I have used a `SELECT` statement to pinpoint what I will be changing with the `UPDATE` command.

![image](https://user-images.githubusercontent.com/107522496/206731578-4b038340-13d4-4723-810f-f844874ae641.png)

Then using `UPDATE`, I changed it to Matt.

---

# Solution - Change all ages to 25 where departments are English 

![image](https://user-images.githubusercontent.com/107522496/206732157-f2c2e254-4879-48df-a1e2-49c486e9a702.png)

First, I have used a `SELECT` statement to pinpoint what I will be changing with the `UPDATE` command.

![image](https://user-images.githubusercontent.com/107522496/206732389-40e55132-d234-4924-880a-52612231bc43.png)

Then using `UPDATE`, I changed all the ages to 25 where department equals English.

---

<!-- Lesson 72 - Introducing Delete --> 

# Introducing Delete 

Here, we will look at how to delete rows from a table in SQL.

![image](https://user-images.githubusercontent.com/107522496/206743413-7ea464e5-d106-4740-ac22-1bddb93c0940.png)

We use:

```sql
DELETE FROM <table-name> WHERE<condition>
```

<mark>IMPORTANT</mark> : Need to use the `WHER`E command with `DELETE FROM`, as otherwise, if we just used `DELETE FROM` followed by a table name, it would delete all rows of that table. The table will still remain however. 

---

In the below example, we want to delete rows which contain `Science` in the department column. 

![image](https://user-images.githubusercontent.com/107522496/206744767-6330271a-1009-47c6-ad4d-7ced30570e8c.png)

---

![image](https://user-images.githubusercontent.com/107522496/206745100-88d3b96d-1da6-46d2-bbc4-977d6a1fc780.png)

Using

```sql
DELETE FROM employees WHERE department='Science';
```

We have now deleted the whole row where the department column contained Science, i.e., where id number was 3.

---

> Remember to use DELETE FROM and not just DELETE.

---
Code

```sql
-- Delete all employees with name of 'Guy':
DELETE FROM employees WHERE name='Guy';

-- Delete all rows in the employees table:
DELETE FROM employees; 
```

---

<!-- Lesson 74 - DELETE Exercise -->

# `DELETE` Exercise

![image](https://user-images.githubusercontent.com/107522496/207077338-b9152f58-0352-43ff-a31d-7d9b30bcb800.png)

1. Delete all 35 year old employees 
2. Delete the employees whose age is the same as their id
3. Delete all emplyoees


---

# Solution 


1. Delete all 35 year old employees 

![image](https://user-images.githubusercontent.com/107522496/207077812-7551ee93-fc3b-4672-b675-0a71965c4249.png)

First we are using `SELECT` to see what will be targeted when we run the `DELETE` command.

---

![image](https://user-images.githubusercontent.com/107522496/207079041-d9a40efe-4dd6-4f34-9cc2-1e94bbbb3e77.png)


Using:

```sql
DELETE FROM employees WHERE age=35;
```

we hve removed the two rows where age was 35.

---

2. Delete the employees whose age is the same as their id

![image](https://user-images.githubusercontent.com/107522496/207079860-f7c41c0c-8795-4d50-9a73-52a500056a5e.png)

Using:

```sql
SELECT * FROM employees where age=id;
``

we can check what row/s will be targeted.

---

![image](https://user-images.githubusercontent.com/107522496/207080652-97ae980d-5ce2-4b55-bb26-cdfac36980ab.png)

```sql
DELETE FROM employees where age=id;
```
---

3. Delete all emplyoees

![image](https://user-images.githubusercontent.com/107522496/207081603-0279bac6-bf7b-43af-a17d-3092d0a8e8a6.png)

```sql
DELETE FROM employees;
SELECT * FROM employees;
```
This deletes all entries and leaves the table empty.

---

<!-- Section 6: CRUD Challenge -->







