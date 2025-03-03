The ORDER BY keyword is used to sort the result-set in ascending or descending order.

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

```
SELECT * FROM Customers
WHERE CustomerID > 80;
```

### ODER BY
The ORDER BY keyword is used to sort the result-set in ascending or descending order.

Sort the products by price:
```
SELECT * FROM Products
ORDER BY Price;
```

### ODER BY DESC
The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

```
SELECT * FROM Products
ORDER BY Price DESC;
```


### Order Alphabetically
For string values the ORDER BY keyword will order alphabetically:

```
SELECT * FROM Products
ORDER BY ProductName;
```

### ORDER BY Several Columns
```
SELECT * FROM Customers
ORDER BY Country, CustomerName;
```

### Using Both ASC and DESC
```
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```


### SQL AND Operator
The WHERE clause can contain one or many AND operators

The AND operator is used to filter records based on more than 1 condition, like if you want to return all customers from Spain that start with the letter 'G':

Example: Select all customers from Spain that starts with the letter 'G':
```
SELECT *
FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
```

The following SQL statement selects all fields from Customers where Country is "Germany" AND City is "Berlin" AND PostalCode is higher than 12000:

```
SELECT * FROM Customers
WHERE Country = 'Germany'
AND City = 'Berlin'
AND PostalCode > 12000;
```

#### Combining AND and OR
```
SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```

### SQL OR Operator
Select all customers from Germany or Spain

```
SELECT *
FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';
```

```
SELECT * FROM Customers
WHERE City = 'Berlin' OR CustomerName LIKE 'G%' OR Country = 'Norway';
```

### The NOT Operator
The NOT operator is used in combination with other operators to give the opposite result, also called the negative result.

Select only the customers that are NOT from Spain:
```
SELECT * FROM Customers
WHERE NOT Country = 'Spain';
```

Syntax
```
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

#### NOT LIKE
Select customers that does not start with the letter 'A':
```
SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'A%';
```

#### NOT BETWEEN
Select customers with a customerID not between 10 and 60:
```
SELECT * FROM Customers
WHERE CustomerID NOT BETWEEN 10 AND 60;
```

#### NOT IN
Select customers that are not from Paris or London:
```
SELECT * FROM Customers
WHERE City NOT IN ('Paris', 'London');
```

#### NOT Greater Than
Select customers with a CustomerId not greater than 50:
```
SELECT * FROM Customers
WHERE NOT CustomerID > 50;
```

#### NOT Less Than
Select customers with a CustomerID not less than 50:
```
SELECT * FROM Customers
WHERE NOT CustomerId < 50;
```











