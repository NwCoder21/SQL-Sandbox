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

![image](https://user-images.githubusercontent.com/107522496/213216368-55a0831c-82be-4d6f-bcd1-1e5369905a30.png)

* 7 queries were ran, and the execution times were all very similar. This is because in order to answer each query, the database had to scan all 100 MILLION rows to check each record for a match.

* Our 7 scans of the entire table took a combined total of 29,921 milliseconds.

---

However, we can quicken our search times even more by building an `INDEX`.

When you create an index, the database will generate a method to rapidly find data based on one or more columns.

---

![image](https://user-images.githubusercontent.com/107522496/213217283-e2225dc0-a118-4aae-9491-6f5e0e62667c.png)

For our first example of an INDEX, let's create an INDEX on the `first_name` column of the `person table`

---

To create the INDEX name, we will use the below syntax

```yaml
CREATE INDEX <tableName>_<columnName>_idx
ON <tableName> (<columnName>);
```

So, in our example it becomes:

```yaml
CREATE INDEX person_first_name_idx
ON person (first_name);
```

![image](https://user-images.githubusercontent.com/107522496/213219390-acf6b242-5d90-4dc1-8e84-7ab714f22ca5.png)

To build this index, it took over 4 mins. This is because the database had to scan 100 MILLION rows and build a `first_name` INDEX from scratch

---

Now, Let’s test our new INDEX by repeating an earlier query where we `COUNT`ed the number of people named `Emma`...

![image](https://user-images.githubusercontent.com/107522496/213220308-b1696558-5811-407f-83da-2e3698ca4afc.png)

After having built the INDEX, the same query now took 508 ms.

---

![image](https://user-images.githubusercontent.com/107522496/213220622-18beb30b-3185-4c38-8b7e-ce8deeb7b2c1.png)

However, if we repeat the `COUNT` of people with last name `Smith`, it takes 4,415 milliseconds, which is the slightly more than it took before we created the INDEX. WHy is it taking even longer after we have built an INDEX? The answer to this is because our INDEX was built for the `first_name` column. The `last_name` was not indexed.

---

![image](https://user-images.githubusercontent.com/107522496/213221916-b07315d0-4f4a-4f11-aab5-8203389ea0dd.png)

Likewsie, if we search for people born on April 1, 1995, the query should not run any faster than last time.  This time it took 4011, which is very similar to the earlier search time.  

Our INDEX improved the speed of searches by `first_name`, but had no effect on queries by `last_name` or `birthday` columns.

---

However, if we combine multiple columns, and only one of those columns have been indexed, it still will improve search times. For example, let's `COUNT` the number of people named `Julie Andrews` ...

![image](https://user-images.githubusercontent.com/107522496/213223106-5e8a3d2f-27b8-46dd-aa09-bba6013cfec9.png)

This search took 514 ms. 

---

![image](https://user-images.githubusercontent.com/107522496/213223474-cc8aa876-90fb-449d-ad46-2cb048d09284.png)

By contrast, if you `COUNT` people with `last_name` of `Andrews` and born on June 12, 1992, it takes 4,274 milliseconds.

The reason why the 

```sql
SELECT COUNT(*)
FROM PERSON
WHERE first_name = 'Julie' AND last_name = 'Andrews';
```

is quicker is because the first_name column has been indexed.  

The full name query benefited from the `first_name` index, because the database was able to use it to quickly find all the `Julies`.

In the second query: 

```sql
SELECT COUNT(*)
FROM PERSON
WHERE last_name = 'Andrews' AND birthday = '1992-06-12';
```

had no index to help. It had to perform a full scan of the table to find all people with last name `Andrews`, and then find those with a matching birthday.

---

In the example below:

![image](https://user-images.githubusercontent.com/107522496/213225942-e428f8a2-0d47-48df-97a7-bfff9222aac7.png)

we would think that the database first scans all rows to find people with a matching birthday, and then filter by first name. But this does not happpen. Just because we wrote it in this order does not mean the database will do its work in that order. The database will consider all possible ways to execute your query, then chooses the optimal path.

![image](https://user-images.githubusercontent.com/107522496/213226595-952bd307-e6d1-48f3-85cf-7730d9d1c496.png)

We call each possibility a “query plan”, and the “query optimizer” picks what it thinks is best.

---

























































































