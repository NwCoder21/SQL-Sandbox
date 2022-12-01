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





































