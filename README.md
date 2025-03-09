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
---------------------------
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
---------------------------
### INSERT INTO Statement
Syntax
```
INSERT INTO table_name (column1, column2, column3,...)
VALUES (value1, value2, value3,...);

INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

The following SQL statement inserts a new record in the "Customers" table:
```
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

Multiple inserts
```
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES
('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'),
('Greasy Burger', 'Per Olsen', 'Gateveien 15', 'Sandnes', '4306', 'Norway'),
('Tasty Tee', 'Finn Egan', 'Streetroad 19B', 'Liverpool', 'L1 0AA', 'UK');
```
---------------------------
### NULL values
IS NULL Syntax
```
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```

IS NOT NULL Syntax
```
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

Example:
```
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;

SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```
# UPDATE Statement
The UPDATE statement is used to modify the existing records in a table

Syntax
```
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
The ```WHERE``` clause specifies which record(s) that should be updated. If you omit the ```WHERE``` clause, all records in the table will be updated!

The following SQL statement updates the first customer (CustomerID = 1) with a new contact person and a new city.
```
UPDATE Customers
Set ContactName = 'Michael Moser', City='Toronto'
WHERE CustomerID = 1;
```

Update all records
```
UPDATE Customers
SET ContactName='Juan';
```

# DELETE
DELETE Syntax
```DELETE FROM table_name WHERE condition;```

Delete the customer "Alfreds Futterkiste" from the "Customers" table
```
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
```

### Delete all records
```DELETE FROM table_name;```
delete all rows in the "Customers" table:
```
DELETE FROM Customers;
```

### Delete a table
``` DROP TABLE Customers;```

# SELECT TOP
- The ```SELECT TOP``` clause is used to specify the number of records to return
- Useful for large tables with thousands of records returning a large number of records can impact performance

SQL Server / MS Access Syntax:
```
SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;
```
MySQL Syntax:
```
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

## LIMIT
Select the first 3 records of the Customers table:
```
SELECT * FROM Customers
LIMIT 3;
```

## FETCH FIRST
Select the first 3 records of the Customers table
```
SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;
```
## TOP PERCENT
Select the first 50% of the records from the "Customers" table (for SQL Server/MS Access)
```
SELECT TOP 50 PERCENT * FROM Customers;
```

Adding a where clause
```
SELECT * FROM Customers
WHERE Country='Germany'
FETCH FIRST 3 ROWS ONLY;
```

Adding ORDER BY
Sort the result reverse alphabetically by CustomerName, and return the first 3 records:
```
SELECT TOP 3 * FROM Customers
ORDER BY CustomerName DESC;
```

```
SELECT * FROM Customers
ORDER BY CustomerName DESC
LIMIT 3;
```

# Aggregate Functions
- An aggregate function is a function that performs a calculation on a set of values, and returns a single value.
- Aggregate functions are often used with the ```GROUP BY``` clause of the ```SELECT``` statement. The ```GROUP BY``` clause splits the result-set into groups of values and the aggregate function can be used to return a single value for each group.

The most commonly used SQL aggregate functions are:
```MIN()``` - returns the smallest value within the selected column
```MAX()``` - returns the largest value within the selected column
```COUNT()``` - returns the number of rows in a set
```SUM()``` - returns the total sum of a numerical column
```AVG()``` - returns the average value of a numerical column

Aggregate functions ignore null values (except for ```COUNT()```).

# MIN() & MAX() Functions
Find the lowest price in the Price column:
```
SELECT MIN(Price)
FROM Products;
```

Find the highest price in the Price column:
```
SELECT MAX(Price)
FROM Products;
```

When you use ```MIN()``` or ```MAX()```, the returned column will not have a descriptive name. To give the column a descriptive name, use the ```AS``` keyword:
```
SELECT MIN(Price) AS SmallestPRICE
FROM Products;
```

Here we use the ```MIN()``` function and the ```GROUP BY``` clause, to return the smallest price for each category in the Products table:
```
SELECT MIN(Price) AS SmallestPrice, CategoryID
FROM Products
GROUP BY CategoryID;
```










