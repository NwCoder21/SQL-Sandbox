# Manipulation

# Introduction to SQL

* **SQL**, Structured Query Language, is a **programming language** designed to **manage data** stored in **relational databases**. 
* SQL operates through **simple, declarative statements**. 
* This keeps data **accurate** and **secure**, and helps **maintain the integrity** of databases, regardless of size.

* SQL gives you the freedom to explore your data, and power to make better decisions.
* By learning SQL, you will also learn concepts that apply to nearly every data storage system.

The **statements** covered in this course use **SQLite Relational Database Management System** (RDBMS). You can also access a glossary of all the SQL commands taught in this course by clicking [here](https://www.codecademy.com/article/sql-commands).

Below is a simple SQL command

``` sql
SELECT * FROM Customers;
```

![image](https://user-images.githubusercontent.com/107522496/205068071-0da61991-b9d6-4a9f-abdf-1e81ba415ba1.png)

![image](https://user-images.githubusercontent.com/107522496/205069001-c71333a8-8721-4c09-ac50-ff4e7d6ccd7b.png)


Hint: common errors:

```
Did you forget the *?
Did you forget the ;?
```
---

#  Relational Databases

Using the above command, we returned information from a relational database.

* A _relational database_ is a database that **organizes information into one or more tables**. Here, the relational database contains one table. 
* A _table_ is a **collection of data organized into rows and columns**. 
* Tables are sometimes referred to as relations. Here the table is celebs. 

* A _column_ is a set of data values of a particular type. Here, id, name, and age are the columns.

* A _row_ is a single record in a table. The first row in the celebs table has:
  * An id of 1
  * A name of Justin Bieber
  * An age of 22

# Types of Data Types

All data stored in a relational database is of a certain data type. Some of the most common data types are:

* INTEGER, a positive or negative whole number
* TEXT, a text string
* DATE, the date formatted as YYYY-MM-DD
* REAL, a decimal value

---

# Statements

``` sql 
CREATE TABLE table_name (
   column_1 data_type, 
   column_2 data_type, 
   column_3 data_type
);
```

The above is an example of a SQL statement. A _statement_ is text that the database recognizes as a **valid command**. 

* Statements always end in a semicolon ;. 

Let's break down the above statement

1. `CREATE TABLE` is a _clause_/_command_. Clauses/commands perform specific tasks in SQL. By convention, clauses are written in capital letters. 
> Note: Clauses can also be referred to as commands.  
2. `table_name` refers to the name of the table that the command will be applied to.
3.  (`column_1 data_type`, `column_2 data_type`, `column_3 data_type`) are _parameters_. A _parameter_ is a **list of columns, data types, or values** that are **passed to a clause as an argument**. Here, the parameter is a list of column names and the associated data type.

> Note: The number of lines used does not matter. A statement can be written all on one line, or split up across multiple lines if it makes it easier to read. In this course.

---

``` sql
SELECT * FROM Customers;
```

In the above statment:

1. `SELECT` and `FROM` are the clauses here.
2. We are applying the command to the `celebs` table.

---

# Create

The `CREATE` statement is used to create a new table in a database. 

> Note: you can use the `CREATE` statement anytime you want to create a new table from scratch.

The following statement will create a new table named `customers`

``` sql 
CREATE TABLE customers (
   id INTEGER, 
   name TEXT, 
   age INTEGER
);

```

1. `CREATE TABLE` is a clause/command that tells SQL you want to create a new table. 
2. `customers` is the name of the table we want to create 
3. (`id INTEGER`, `name TEXT`, `age INTEGER`) is a list of parameters defining each column, or attribute in the table and its data type:

  *  `id` is the first column in the table. It stores values of data type `INTEGER`
  *  `name` is the second column in the table. It stores values of data type `TEXT`
  *  `age` is the third column in the table. It stores values of data type `INTEGER`

---

![image](https://user-images.githubusercontent.com/107522496/205082639-462eb5d6-a494-4515-91ce-003245b80496.png)

The above is an example of creating an empty new table.

---

# Insert

The `INSERT` statement inserts a new row into a table.

We can use the `INSERT` statement when you want to add new records.

---

```sql
INSERT INTO celebs (id, name, age) 
VALUES (1, 'Justin Bieber', 22);
```

The above statement will enter a record for Justin Bieber into the celebs table

* `INSERT INTO` is a clause that adds the specified row or rows.
* `celebs` is the table the row is added to.
* (`id, name, age`) is a parameter identifying the columns that data will be inserted into.
* `VALUES` is a clause that indicates the data being inserted.
*  (`1, 'Justin Bieber', 22`) is a parameter identifying the values being inserted.
  1. `1`: an integer that will be added to id column
  2. `Justin Bieber`: text that will be added to name column
  3. `22`: an integer that will be added to age column


---

![image](https://user-images.githubusercontent.com/107522496/207060155-8bb704ec-8dc0-4b53-a38c-b1189e07966a.png)

Here, we have added four rows to the tableusing `INSERT INTO` statements. and finally, using a `SELECT` statement, have displayed data from the table.  


```sql
INSERT INTO celebs (id, name, age) 
VALUES (1, 'Justin Bieber', 22); 

INSERT INTO celebs (id, name, age) 
VALUES (2, 'Beyonce Knowles', 33); 
 
INSERT INTO celebs (id, name, age) 
VALUES (3, 'Jeremy Lin', 26); 
 
INSERT INTO celebs (id, name, age) 
VALUES (4, 'Taylor Swift', 26); 

SELECT * FROM celebs;
```

> Notice the single quotes around name. This is because text strings require quotes around them, while numbers don’t.

---

# `SELECT`

SELECT statements are used to fetch data from a database. In the statement below, SELECT returns all data in the name column of the celebs table.

```sql
SELECT name FROM celebs;
```

1. `SELECT` is a clause that indicates that the statement is a query. **You will use SELECT every time you query data from a database.**
2. `name` specifies the column to query/retreive data from.
3. `FROM celebs` specifies the name of the table to query/retreive data from. In this statement, data is queried/retreived from the celebs table. 

---

You can also retrieve data from all columns in a table with `SELECT *`.

```sql
SELECT * FROM celebs;
```

`*` is a special wildcard character that allows you to select every column in a table without having to name each one individually. Here, the result set contains every column in the celebs table.

**`SELECT` statements always return a new table called the result set.**

![image](https://user-images.githubusercontent.com/107522496/207063390-26003ce8-cbcd-4392-ac5c-45310c3e10fb.png)

---

# Alter

The `ALTER TABLE` statement adds a new column to a table. You can use this command when you want to add columns to a table. The statement below adds a new column `twitter_handle` to the celebs table.

```sql
ALTER TABLE celebs 
ADD COLUMN twitter_handle TEXT;
```
---

1. `ALTER TABLE` is a clause that lets you make the specified changes.
2. `celebs` is the name of the table that is being changed.
3. `ADD COLUMN` is a clause that lets you add a new column to a table:
 * `twitter_handle` is the name of the new column being added
 * `TEXT` is the data type for the new column

4. `NULL` is a special value in SQL that represents missing or unknown data. Here, the rows that existed before the column was added have NULL (∅) values for twitter_handle.

---

# Update

The `UPDATE` statement edits a row in a table. You can use the `UPDATE` statement when you want to change existing records. The statement below updates the record with an id value of 4 to have the twitter_handle @taylorswift13.

```sql
UPDATE celebs 
SET twitter_handle = '@taylorswift13' 
WHERE id = 4; 
```

1. ``UPDATE` is a clause that edits a row in the table.
2. `celebs` is the name of the table.
3. `SET` is a clause that indicates the column to edit.
 * `twitter_handle` is the name of the column that is going to be updated
 * `@taylorswift13` is the new value that is going to be inserted into the twitter_handle column.

4. `WHERE` is a clause that indicates which row(s) to update with the new column value. Here the row with a 4 in the id column is the row that will have the twitter_handle updated to @taylorswift13.

---

![image](https://user-images.githubusercontent.com/107522496/207067086-2d3cfd0f-313e-4e8b-95c9-3df5ff653652.png)

---

# Delete

The `DELETE FROM` statement **deletes one or more rows from a table**. You can use the statement when you want to delete existing records. The statement below deletes all records in the celebs table with no twitter_handle:

```sql
DELETE FROM celebs 
WHERE twitter_handle IS NULL;
```

1. `DELETE FROM` is a clause that lets you delete rows from a table.
2. `celebs` is the name of the table we want to delete rows from.
3. `WHERE` is a clause that lets you select which rows you want to delete. Here we want to delete all of the rows where the twitter_handle column IS NULL.
4. `IS NULL` is a condition in SQL that returns true when the value is NULL and false otherwise.


---

![image](https://user-images.githubusercontent.com/107522496/207067814-9c443c28-9f9c-41bd-8e4d-6edfaa32c9a8.png)












































