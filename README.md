# SQL

Statement used to select ALL records from a table named 'Customers'

```
SELECT * FROM Customers;
```
### What is SQL?
- SQL - Structured Query Language
- SQL lets you access and manipulate databases
- SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987

### Using SQL on a website
To build a website that shows data from a database, you will need:
- An RDBMS database program (i.e MS Access, SQL Server, MySQL)
- To use a server-side scripting language, like PHP or ASP
- To use SQL to get the data you want
- To use HTML / CSS to style the page

### RDBMS - Relational Datavase Management System
RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.

### Important SQL Commands
```SELECT``` - extracts data from a database
```UPDATE``` - updates data in a database
```DELETE``` - deletes data from a database
```INSERT INTO``` - inserts new data into a database
```CREATE DATABASE``` - creates a new database
```ALTER DATABASE``` - modifies a database
```CREATE TABLE``` - creates a new table
```ALTER TABLE``` - modifies a table
```DROP TABLE``` - deletes a table
```CREATE INDEX``` - creates an index (search key)
```DROP INDEX``` - deletes an index

Return data from the Customers table:
```SELECT CustomerName, City FROM Customers;```

#### Syntax
```
SELECT column1, column2, ...
FROM tableName;
```

If you want to return all columns, without specifying every column name, you can use the ```SELECT *``` syntax
```SELECT * FROM Customers;```

---------------------------

### SELECT DISTINCT 
- Used to return only distinct (different) values

```SELECT DISTINCT Country FROM Customers;```

#### Syntax
```
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

SELECT Without DISTINCT
```SELECT Country FROM Customers;```

---------------------------

### COUNT DISTINCT
- Using ```DISTINCT``` keyword in a function called ```COUNT```, we can return the number of different countries
```SELECT COUNT(DISTINCE Country) FROM Customers;```

workaround for MS Access:
```
SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```

---------------------------

### WHERE
- ```WHERE``` is used to filter records
- Used to extract records for a specified condition

Select all customers from Mexico
```
SELECT * FROM Customers;
WHERE Country='Mexico';
```

Select all customers with a CustomerID greater than 80

```SELECT * FROM Customers
WHERE CustomerID > 80;```

### ODER BY














