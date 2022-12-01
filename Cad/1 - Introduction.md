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







