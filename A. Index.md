# Index

# SQL CREATE INDEX Statement

The `CREATE INDEX` statement is used to create indexes in tables.

Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.

> Note: Note: Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

---

# CREATE INDEX Syntax

Creates an index on a table. Duplicate values are allowed:

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...); 
```

---

# CREATE UNIQUE INDEX Syntax

Creates a unique index on a table. Duplicate values are not allowed:

```sql
CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...); 
```

> Note: The syntax for creating indexes varies among different databases. Therefore: Check the syntax for creating indexes in your database.

---

# CREATE INDEX Example

The SQL statement below creates an index named `idx_lastname` on the `LastName` column in the `Persons` table:

```sql
CREATE INDEX idx_lastname
ON Persons (LastName);
```

If you want to create an index on a combination of columns, you can list the column names within the parentheses, separated by commas:

```sql
CREATE INDEX idx_pname
ON Persons (LastName, FirstName); 
```


---

# DROP INDEX Statement

The `DROP INDEX` statement is used to delete an index in a table.

SQL Server:

```sql
DROP INDEX table_name.index_name;
```

DB2/Oracle:

```sql
DROP INDEX index_name;
```

MySQL:

```sql
ALTER TABLE table_name
DROP INDEX index_name; 
```

---


# Example of Difference When Using Indexes and When Not Using Them

![image](https://user-images.githubusercontent.com/107522496/213209129-e9c8a616-62f7-407b-b77c-6852e8675d94.png)

We have a table which contains the above columns. This table has 100 million rows/records 
To generate the random data in this table, the 1000 most popular female, male and last names in the USA were used. 


---

![image](https://user-images.githubusercontent.com/107522496/213210185-58eb7e88-44c3-476c-9557-2b8d4df66eed.png)

On the top right, we will maintain a list of queries and how many milliseconds each query took to complete.

First, we count every row to see how many rows in the table there are ...

![image](https://user-images.githubusercontent.com/107522496/213210609-00083f68-dc11-4029-bf64-81eb01774803.png)

We can see that there are 100 million rows/records in this table.

---

![image](https://user-images.githubusercontent.com/107522496/213210739-0edde985-f459-4803-a924-cfbfe491cd99.png)

We can see that it took 3562 ms to run this query.

---

![image](https://user-images.githubusercontent.com/107522496/213211099-71b4c402-9032-475b-a3a2-cde04243f390.png)

Let's put this query and the time required in our top right table.

---

![image](https://user-images.githubusercontent.com/107522496/213211450-b49f3087-8c10-48df-90f5-f0f8d2eb47d7.png)

Here, we can see that there are 10052 rows where the last name is `Smith`. This query took ...

![image](https://user-images.githubusercontent.com/107522496/213211768-61971b08-a62c-427e-9522-421346bb6416.png)

4262 ms.

---

![image](https://user-images.githubusercontent.com/107522496/213212038-0bed298e-2b0c-4bae-b9ee-96ee0b2d5987.png)

Here, we are counting the number of records where the first name is `Emma.` We can see there are 49767 rows. This query took ...

![image](https://user-images.githubusercontent.com/107522496/213212270-bccdeb7d-1b83-48a2-b20a-670abf68f21f.png)

4066 ms.

---

![image](https://user-images.githubusercontent.com/107522496/213212573-1986a648-6f22-4fb7-9355-d0bbb9c243ec.png)

Here, we are counting the nummber of people born in May. We can see that 166,384 people were born in May. This query took ...

![image](https://user-images.githubusercontent.com/107522496/213212851-3a4350eb-8e92-4b56-9baa-ff4878cd6244.png)

4480 ms

---

![image](https://user-images.githubusercontent.com/107522496/213213955-dcf5658f-d539-4e3d-b194-359d964edc95.png)

This shows us how many people there are whose first name is Michaels in the database? We can see there are 50,360 rows. This query took ...

![image](https://user-images.githubusercontent.com/107522496/213214211-67941429-3824-4972-8e9f-9efe2cb1b0ed.png)

4127 ms.

---

![image](https://user-images.githubusercontent.com/107522496/213214463-2f220c40-c05b-4406-b9d6-cf3fa8f2be6d.png)

This shows us how many people there are whose last name is either Hawkins or Snow in the database? We can see there are 200,738 people like this. This query took ...

![image](https://user-images.githubusercontent.com/107522496/213214697-a88ddf2b-ea02-4d6f-9e94-cae8958c33d5.png)

5316 ms.

---

![image](https://user-images.githubusercontent.com/107522496/213214976-b6640f14-c215-4d6a-933b-2b1c60682737.png)

This shows how many people were born on April 1, 1995. We can see there are 5374 people like this. This query took ...

![image](https://user-images.githubusercontent.com/107522496/213215218-3ef65815-e321-4d8a-8294-21a0025fb862.png)

4110 ms.

---













































































