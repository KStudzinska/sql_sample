# SQL Portfolio

This is my sql portfolio.

## Database schema

![northwind-er-diagram](https://user-images.githubusercontent.com/113541814/194773708-e808c00f-db1d-4292-b6c7-dbd55fa74b48.png)


## Task 1
Select all orders from the "Orders" table, sorted ascending by the "OrderDate" column and descending by the "ShippedDate" column.

```sql
SELECT * 
FROM Orders
ORDER BY OrderDate ASC, ShippedDate DESC;
```

## Task 2
selects all products with a product name that have "k" in any position.

```sql
SELECT *
FROM Products
WHERE ProductName LIKE '%k%';
```

## Task 3
Selects all fields with "Customers" where the country is Madrid or London.

```sql
SELECT *
FROM Customers
WHERE City='Madrid' OR City='London';
```

## Task 4
Selection of products from a selected price range and selected products.

```sql
SELECT ProductName, UnitPrice 
FROM Products
WHERE UnitPrice BETWEEN 10 AND 25 OR ProductName='Pavlova';

// Another option

WHERE UnitPrice >= 10 AND UnitPrice <= 25 OR ProductName='Pavlova';
```

## Task 5
The average price of all products.

```sql
SELECT AVG(UnitPrice)
FROM Products;
```

## Task 6
View customers and their orders.

```sql
SELECT c.CompanyName, c.Country, o.OrderDate
FROM Customers c
INNER JOIN Orders o
ON c.CustomerID=o.CustomerID;
```

## Task 7
Combining columns and using alias, in the table "Suppliers".

```sql
SELECT CompanyName, Address + ',' + Region + ',' + PostalCode
+ ' ' + City + ',' + Country AS Address, Phone + ',' + Fax AS Contact information
FROM Suppliers;
```

## Task 8
Updates the first shipper (ShipperID = 1) with a new name.

```sql
UPDATE Shippers
SET CompanyName = 'Express'
WHERE ShipperID = 1;
```

## Task 9
Deletes the product named "Tofu" from the "Products" table.

```sql
DELETE FROM Products 
WHERE ProductName='Tofu';
```

## Task 10
Finds the price of the cheapest and the most expensive product.

```sql
SELECT MAX(Price) AS LargestPrice, MIN(Price) AS SmallestPrice
FROM Products;
```

## Task 11
Selects only the DISTINCT values from the "Country" column in the "Suppliers" table.

```sql
SELECT DISTINCT Country 
FROM Suppliers 
ORDER BY Country ASC;
```

## Task 12
Selects "ProductName" and "UnitPrice" from the "Products" table, where the price is greater than or equal to 100.

```sql
SELECT ProductName, UnitPrice
FROM Products
WHERE UnitPrice >= 100;
```

## Task 13
Selects all categories that have "Cheeses" in their description.

```sql
SELECT * 
FROM Categories
WHERE Description IN ('Cheeses');
