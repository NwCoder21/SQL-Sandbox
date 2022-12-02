# 3 - Creating Databases & Tables

In this section, some of the things we will be covering is:

* Looking at our first commands around data, so we'll be able to make a new database or delete a database.
* And will be looking inside of these databases. 
* We will start to work with tables, which are a fundamental structure in SQL and MySQL.

---

<!-- Lesson 14 - Showing Databases -->

# Showing Databases 


![image](https://user-images.githubusercontent.com/107522496/205101022-26a12298-b9cd-44d2-a751-5d532659e80f.png)

Within a Database Server, we can have multiple databases. They can be isolated and don't have to have anything to do with the other databases on the database server.  

---

Let's take a look at two of the databases on our database server. 

![image](https://user-images.githubusercontent.com/107522496/205093741-b16773e1-e706-440e-8fe0-e452615abc0e.png)

Both of these databases will have some data that is unique to them.

In the Dog Walker Database, we may have dog profile walkers, and in the Soap Shop Database, we may have a list of soaps 

But they also might both have users, they might both have payments, but we want them to be separate, so that each database's data is seperate from the other. For example, we would not want to charging people in the dog walker database, when someone buys a piece of soap.

> One more time: we have multiple databases within a MySQL database server.


---

# `show databases;`

First thing we need to do as far as code is take a look at what database is currently exist.

![image](https://user-images.githubusercontent.com/107522496/205100581-3e28f33b-9d94-437b-b7b1-7c6f5e1e82cb.png)

When we install MySQL, it comes with some default databases. Don’t need to worry about them. 

The

```sql
show databases;
```
Command will display the current databases on the MySQL Server. 

---

# How to Create a Database - `CREATE DATABASE <name_of_datbase>;`

Using

```sql
CREATE DATABASE <name_of_datbase>;
```

we can create an empty database whcih is named by the name the user provides, which we can then add data to. For example, if I wanted to create a table named `footballers`, I would type:

```sql
CREATE DATABASE footballers;
```

> Note: when naming the table, try to avoid using spaces as it can cause porblems down the line.


We can use snake case or camelcase to name the tables, such as:

* footballer_names
* footballerNames

---

Also, by convention, we capitalise all the SQL Keywords. However, if we did not capitalise them, the code will still work.

---

![image](https://user-images.githubusercontent.com/107522496/205104349-3a08f83e-78bd-4a59-bf74-032b978fb58b.png)

Here is an example of creating a `footballerNames` database and then displaying all the exisiting databases on the MySQL Server.

---

![image](https://user-images.githubusercontent.com/107522496/205105420-30eca121-329d-4b53-8ad1-e835f81c5ad2.png)

On the left side, it should show a list of databases on the server. If it does not, click on the refresh button.

![image](https://user-images.githubusercontent.com/107522496/205105633-a84af33f-7fe7-45d5-a76c-c3d91ff899ae.png)

---

<!-- Contine from Lesson 18 - Dropping and Using Databases -->

# Dropping and Using Databases

```sql
DROP DATABASE <name>;
``` 
This removes a database entirely and all of its contents. 

![image](https://user-images.githubusercontent.com/107522496/205276120-77286f9f-4f4f-45a2-a886-bf5533ff28c4.png)

In this example, I have deleted the `footballernames` database. 

---

# Using a Database - `USE <name_of_database>;`

To use a database, we use the below command :

```sql
USE <name_of_database>;
```

When it comes time to insert information or find information or delete information or create new tables, we have to tell my SQL where we are.

(NOTE: When using `CREATE DATABASE`, it creates the database but you are still not working in tht database. To work in that database, we need to use `USE` command.)

To do that, we use the `USE` command.

![image](https://user-images.githubusercontent.com/107522496/205278298-cdcafab9-74d3-46e1-ba3b-1349393aaef5.png)

We are now working in the fruits database.
 

---
# Checking the Database You Are In - `SELECT database();`

![image](https://user-images.githubusercontent.com/107522496/205278761-e2e62c3b-b9e5-40ef-85d5-0c5dd627fe51.png)

We can use 

```sql
SELECT database();
```

to check to database we are working in. 

---

Another way to use a database is by double clicking on it. We can then use the `SELECT database();` to confirm if we are nowin that database. 

---

<!-- Lesson 20 - Introducing tables) -->

# Introducing Tables

We need to put tables into databases so we can hold data. 

A relational database is a collection of tables.

A more formal definition of a table would be:

Table: a collection of related data held in a strcutured format within a database

For example if we had a fruits table, every fruit would have a

* Name
* Colour 
* Country grown in 

![image](https://user-images.githubusercontent.com/107522496/205284076-d95199b3-8924-4449-8325-fe68389cb761.png)

Columns: these are the headers for each table. The first step is t get the headers/columns set up in SQL.

![image](https://user-images.githubusercontent.com/107522496/205284235-14a60f02-132f-4298-a9b3-016521e648ca.png)

Rows: these are the entries of the data (the actual data). Once the columns have eben set up, we can then start to add data to the table. 

Databases in general consist of lots of tables. There's going to be lots of different entities and almost every entity will have its own table.

So there might be a customer's table, a order's table, an address table, etc. 

--- 

<!-- Lesson 21  - Data Types: The Basics -->  

# Data Types - The Basics

When we define the structure of a table, we're not only saying what column names we want, for example, `name`, `breed` and `age`, but we also specify the types, in other words, what type of information is permitted in each column.

---

![image](https://user-images.githubusercontent.com/107522496/205307486-0afba6e6-04b8-42d9-bee5-704dfed2ba5e.png)

For example, if we wanted to use the `age` column to calculate the age of a cat, we need to ensure the data inputted into that column is a number (integer) so that we can make the calculation, otherwise, if user enters a a number as a string,won't be able to calculate.

---

![image](https://user-images.githubusercontent.com/107522496/205308124-1f48b536-473c-4c47-8b41-582c33167d0b.png)

Many differnt types of data types. Don't have to learn all of them, jsut be aware that they exist. Will only mostly ever use some of the above data types. 

If need more information, click [here](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)

---

The two main data types we will be working with at the momment are, `INT` (this is an integer data type) and `VARCHAR` (this is a string data type).

---

# `INT`

![image](https://user-images.githubusercontent.com/107522496/205311702-38856a96-4a58-429a-b4bc-4f3ead07b4cd.png)

INT is a whole number and the maximum (signed) value an INT can have is from -2147483647 (negative) to 2147483647 (positive).

> An unsigned value could have a greater value but won't cover for time being. 

---

![image](https://user-images.githubusercontent.com/107522496/205312400-637a7ea8-7fc6-429f-98d8-4b4d6aabab05.png)

The above are examples of an INT.

---

# `varchar`

Stands for Variable-Length String. This means can store different length of characters into them, such as `apple`, `oranges` and `pineapples`. All of these have a different length of characters. varchar can also store sentences. 

![image](https://user-images.githubusercontent.com/107522496/205313380-2b869b3f-dc54-42ad-821d-73ac1e84e8f8.png)

Above are examplesof other strings. 

---

when we create a table and we assign the data types with `varchar`, we can actually specify a maximum number of characters allowed.

![image](https://user-images.githubusercontent.com/107522496/205315582-82f60141-c6a2-445f-b22c-33368887e9ba.png)

For example, we can say for the `Name` and `Breed` columns, a maximum of 100 characters aare allowed.

---

# Activity

![image](https://user-images.githubusercontent.com/107522496/205316299-bc974299-b8b5-4d46-b780-737a17092aab.png)

# Solution 

![image](https://user-images.githubusercontent.com/107522496/205317031-ea4ba431-ccc7-4606-ae44-7297afaa113b.png)

![image](https://user-images.githubusercontent.com/107522496/205317285-da0ad46d-9335-48df-bec3-4e7b68260ff2.png)

---






























