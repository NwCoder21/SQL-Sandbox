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


















